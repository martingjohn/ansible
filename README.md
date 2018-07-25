# ansible
ansible docker container

Automatically runs ansible-playbook unless overwritten with entrypoint

I use like so - where ${PWD}/ansible/complete has my playbooks and ${PWD}/ansible/hosts has my host setup and ${PWD}/ssh has ssh keys and known hosts

    docker run \
       --rm \
       -e ANSIBLE_FORCE_COLOR=1 \
       -v ${PWD}/ansible/hosts:/etc/ansible/hosts:ro \
       -v ${PWD}/ansible/complete:/src \
       -v ${PWD}/ssh:/root/.ssh \
       martinjohn/ansible \
       apt-upgrade.yaml

