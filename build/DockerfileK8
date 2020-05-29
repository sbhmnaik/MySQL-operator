FROM quay.io/operator-framework/ansible-operator:v0.17.0

COPY requirements.yml ${HOME}/requirements.yml
RUN ansible-galaxy collection install -r ${HOME}/requirements.yml \
 && chmod -R ug+rwx ${HOME}/.ansible
RUN chgrp -R 0 directory && \ chomd -R g=u directory

COPY watches.yaml ${HOME}/watches.yaml

COPY roles/ ${HOME}/roles/
