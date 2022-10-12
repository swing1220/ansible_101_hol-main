# Inventory

#### Case 1

- 모든 호스트에 접속 가능 확인

```
ansible -i hosts.ini all -m ping
```

#### Case 2

- 패턴을 이용하여 특정 호스트/그룹을 선택적으로 작업 수행 

```
ansible -i hosts.ini all -a hostname
ansible -i hosts.ini web -a hostname
ansible -i hosts.ini web,was -a hostname
ansible -i hosts.ini "*2" -a hostname
```

#### Case 3

- root 권한을 획득하여 작업 수행

```
ansible -i hosts.ini all -a id
ansible -i hosts.ini all -a id -b -u root
```