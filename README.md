## vsvleo_infra
### Домашнее задание 05
#### Сквозное пдключение к инстансу internalhost, в одну строку:
```ssh -i ~/.ssh/appuser -A appuser@104.155.51.79 -t ssh 10.154.0.2 # connect in the one line```
#### Для создания алиаса, в каталоге пользователя редактируем файл: ~/.ssh/config
* 1 выриант _(с созданием дополнительного алиаса, для доступа на сервер bastion)_ :
```
Host bastion
    User appuser
    HostName 104.155.51.79

Host internalhost
    User appuser
    HostName 10.154.0.2
    IdentityFile ~/.ssh/appuser
    ProxyCommand ssh -W %h:%p appuser@104.155.51.79
 ```
 
