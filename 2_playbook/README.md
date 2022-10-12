# Playbook

#### Case 1 - play hosts

- ansible-playbook CLI를 이용하여 playbook 실행
- localhost에서 작업 실행
- 모든 호스트에서 작업 실행

```
ansible-playbook -i hosts.ini pb.yml
```

#### Case 2 - Ansible Facts

- Ansible Facts를 이용하여 호스트의 정보 수집
- Ansible Facts를 이용하여 호스트의 특정 정보 확인하기

```
ansible-playbook -i hosts.ini pb_gather_facts.yml
```

#### Case 3 - become, delegate_to

- become 키워드를 사용하여, root 권한으로 작업 수행
- delegate_to 키워드를 사용하여, play에 지정된 호스트가 아닌 다른 호스트에서 task를 실행

```
ansible-playbook -i hosts.ini pb_become.yml
```

#### Case 4 - include_tasks

- Task를 별도의 파일로 분리하고, play에서 task 파일 읽어오기

```
ansible-playbook -i hosts.ini pb_include_tasks.yml
```

#### Case 5 - run once

- run_once 키워드를 이용하여 호스트 수에 상관없이 한번만 task 실행하기

```
ansible-playbook -i hosts.ini pb_run_once.yml
```

#### Case 6 - tags, start-at-task

- tags 키워드를 이용하여, 특정 task만 실행하기
- start-at-task 키워드를 사용하여 특정 task부터 실행하기

```
ansible-playbook -i hosts.ini pb_tags.yml
ansible-playbook -i hosts.ini pb_tags.yml --tags foo
ansible-playbook -i hosts.ini pb_tags.yml --tags bar
ansible-playbook -i hosts.ini pb_tags.yml --tags never
ansible-playbook -i hosts.ini pb_tags.yml --tags omg
ansible-playbook -i hosts.ini pb_tags.yml --start-at-task "foo,bar"

ansible-playbook -i hosts.ini pb_tags2.yml --tags foo
```