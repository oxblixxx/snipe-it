# ERRORS FACED

# SONARQUBE ISSUE FACED


![sonar](./assets/sonar.png)

To fix this error, [sonarqube-requirements](https://docs.sonarsource.com/sonarqube/9.9/requirements/prerequisites-and-overview/) and then this could be the issue:

```sh
sudo sysctl -w vm.max_map_count=262144
```
---

Indefinite loading of Sonarqube. This error was fixed by installing apache2. 

```sh
sudo apt install apache2
```
---

## Forgot password
I forgot the password to my sonarqube instance, spinned up docker-compose file. I logged into the postgres container with `psql -d mydb -U myuser` then I ran this command from the [documentation](https://docs.sonarsource.com/sonarqube/latest/instance-administration/security/)

```sh
update users set
crypted_password='100000$t2h8AtNs1AlCHuLobDjHQTn9XppwTIx88UjqUm4s8RsfTuXQHSd/fpFexAnewwPsO6jGFQUv/24DnO55hY6Xew==',
salt='k9x9eN127/3e/hf38iNiKwVfaVk=',
hash_method='PBKDF2',
reset_password='true',
user_local='true',
active='true'
where login='admin';
```

Refreshed browser then it works!!!.


## UPDATE CONF SONAR.PROPERTIES
I needed to update the configuration file, but then I don't have a text editor shipped and sudo priviledges. Then I find this helpful from [stackoverflow](https://stackoverflow.com/questions/30853247/how-do-i-edit-a-file-after-i-shell-to-a-docker-container)

```sh
docker cp <container>:/path/to/file.ext .
```

while done editing the file, do this to copy back to the running container to replace the old file

```sh
docker cp file.ext <container>:/path/to/file.ext
```