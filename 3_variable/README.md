# Variable

#### Case 1 - vars

- vars 키워드를 이용하여 변수를 선언
- task에서 변수값을 참조하기

```
ansible-playbook -i hosts.ini pb_vars.yml
```

#### Case 2 - vars_files

- vars_files 키워드를 이용하여, 변수 파일을 읽어오기

```
ansible-playbook -i hosts.ini pb_vars_files.yml
```

#### Case 3 - extra_vars

- --extra_vars 옵션을 이용하여, CLI에서 playbook으로 변수 전달하기

```
ansible-playbook -i hosts.ini  pb_extra_vars.yml --extra-vars host=web1
ansible-playbook -i hosts.ini  pb_extra_vars.yml -e host=web
ansible-playbook -i hosts.ini  pb_extra_vars.yml -e host=all
```

#### Case 4 - set_fact

- set_fact 모듈을 사용하여, 변수 선언하기

```
ansible-playbook -i hosts.ini pb_set_fact.yml
```

#### Case 5 - register

- register 키워드를 이용하여, task의 실행 결과를 변수에 저장하기

```
ansible-playbook -i hosts.ini pb_register.yml
```

#### Case 6 - vars_prompt

- vars_prompt 키워드를 이용하여, CLI 실행 시 변수값 입력받기

```
ansible-playbook -i hosts.ini pb_vars_prompt.yml
```