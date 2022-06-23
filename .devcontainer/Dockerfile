# does user setup and gives 'install-packages' script, see https://github.com/gitpod-io/workspace-images
FROM gitpod/workspace-base@sha256:5fcdb99366114646be6a82559aedb498b0f8b500192195782546664514ed166d as development

USER gitpod

# setup asdf-vm: https://asdf-vm.com/guide/getting-started.html
RUN git clone --depth 1 https://github.com/asdf-vm/asdf.git $HOME/.asdf --branch v0.10.0 \
    && echo '. $HOME/.asdf/asdf.sh' >> $HOME/.bashrc \
    && echo '. $HOME/.asdf/completions/asdf.bash' >> $HOME/.bashrc

# in the following 'bash -i -c' is used to have asdf available as '-i' reads from .bashrc

# install and pin asdf erlang plugin: https://github.com/asdf-vm/asdf-ruby
RUN bash -i -c 'asdf plugin add ruby https://github.com/asdf-vm/asdf-ruby.git && asdf plugin update ruby 36117f50f16b0ba675dccfa824b9ba21c7cad297'

# install and pin asdf direnv plugin: https://github.com/asdf-community/asdf-direnv
# RUN bash -i -c 'asdf plugin-add direnv https://github.com/asdf-community/asdf-direnv.git && asdf plugin update direnv a5aefdf8c7df2898053bc6db1f5936de28c45aef'

# get .tool-versions from repo
COPY .tool-versions $HOME/

# install versions specified in .tool-versions
RUN bash -i -c 'asdf install'

# run direnv setup
# RUN bash -i -c "asdf direnv setup --shell bash --version $(cat ~/.tool-versions | grep direnv | awk '{print $2}')"

USER root

# install common utilities
RUN install-packages \
    curl

USER gitpod
