Пример [workflow](.github/workflows/main.yml), который пишет в [другой репозиторий](https://github.com/GitHubExperiments/target).

Предварительно изучите пример [github.token](https://github.com/GitHubExperiments/github.token). Текущий пример отличается тем, что вместо токена `secrets.GITHUB_TOKEN` используется Personal Access Token, который вы создаёте сами. Недостатком этого метода является то, что PAT позволяет изменять любой репозиторий, к которому имеет доступ ваш аккаунт.

Для запуска:
1) Форкните этот репозиторий
2) В настройках своего профиля [создайте токен](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token) (нужна только галочка `public_repo`)
3) Обязательно скопируйте сгенерированный токен: в веб-интерфейсе он отображаться больше не будет
4) В настройках форка [создайте секрет](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository) с именем `MY_TOKEN`. В поле `Value` вставьте сгенерированный токен
5) Поменяйте целевой репозиторий в [workflow](.github/workflows/main.yml)
6) Включите Actions
7) Нажмите "Run workflow" на [данной страничке](../../actions/workflows/main.yml)

P.S. Обратите внимание, что авторизация с использованием PAT отличается от авторизации с использованием `secrets.GITHUB_TOKEN`.

---------

Обновление:

Теперь GitHub позволяет создавать токены, имеющие доступ только к конкретным репозиториям: <https://github.blog/2022-10-18-introducing-fine-grained-personal-access-tokens-for-github>
