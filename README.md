# Гайд по Git и Github
Если вы читаете это, то можем вас поздравить, вы сделали первый шаг к освоению систем контроля версий! Вы уже сталкивались с ними на одной из лабораторных прошлого семестра, но настало время познакомиться с этой темой поближе. Все домашние работы в этом семестре вы будете сдавать, делая коммиты и отправляя их в удалённый репозиторий. 

Вы можете обращаться к этому гайду, когда забыли синтаксис чего-либо, либо же хотите вспомнить, как создавать репозиторий. 

> [!TIP]
> Вы можете посмотреть содержание данной статьи, кликнув на иконку <img width="14" alt="image" src="https://github.com/MMCS-FIIT/GithubGuide/assets/28728097/0ecdfffd-9d43-4569-9f4d-9add9fa6af2c"> слева от _README.MD_

## Работа с Github
Уточнение: Git != Github. Простыми словами, Git - это сама программа, которая осуществляет контроль версий, а Github - это ресурс, где можно удалённо хранить созданные гитом репозитории. Если вы ещё не заегистрированы на этом ресурсе, сделайте это, перейдя на [главную страницу](https://github.com/). Процесс регистрации не должен вызвать затруднений. Главное правило: _используйте почту, к которой у вас есть доступ_.

### Получение Personal Access Token
С недавнего времени в целях безопасности GitHub разрешает вносить изменения в удалённые репозитории через командную строку только с использованием **Personal access token**. Поэтому, прежде чем начать работу, нам нужно его получить.
1. Авторизуйтесь в GitHub. Вы попадёте на главную страницу. Щёлкните по своей аватарке в правом верхнем углу и в выпадающем меню выберите пункт **Settings**.
  ![image](https://github.com/MMCS-FIIT/GithubGuide/assets/28728097/12752f58-bf9a-41a9-82ba-b8c94cfb380b)
2. Прокрутите открывшееся окно настроек в самый низ до пункта меню **Developer settings**.
   ![image](https://github.com/MMCS-FIIT/GithubGuide/assets/28728097/d8c83c09-86a8-4b81-9ab5-676120e6dbb6)
3. В настройках разработчика выберите пункт меню **Personal access tokens** -> **Tokens (classic)**. В этом разделе выберите пункт **Generate new token (classic)**.
   ![image](https://github.com/MMCS-FIIT/GithubGuide/assets/28728097/d8d503f5-17f9-43a6-b6e3-b9ee05b953fe)
4. В открывшемся меню необходимо дать токену пояснение, для чего он создаётся (например, _mmcs-hw_). В разделе **Select scopes** нужно отметить только одну галочку - **repo**. Также можно изменить срок действия токена в разделе **Expiration** на **No expiration**, если вы не хотите создавать новый токен каждый месяц (бессрочные токены не рекомендуются к использованию самим Github, но это всё-таки удобнее, чем постоянное их обновление).
   ![image](https://github.com/MMCS-FIIT/GithubGuide/assets/28728097/44b1ebfe-304b-4ad0-a5b2-17d27c74b765)
5. После того, как вы проверили все настройки, нажмите на кнопку Generate Token. На странице будет показан сгенерированный токен. Его нужно скопировать и сохранить там где его легко найдёте вы, и не сможет найти никто другой.
> [!WARNING]
> Как только вы закроете эту страницу, посмотреть токен уже будет нельзя, и придётся генерировать новый. Позже мы рассмотрим, как сохранить его в Git на вашем компьютере, не потеряйте его до тех пор!

Теперь, когда у вас есть токен, вы сможете авторизоваться во время работы с репозиторием. Когда возникает эта необходимость, мы рассмотрим ниже.

### Создание удалённого репозитория
> [!IMPORTANT]
> Этот раздел не актуален для большинства домашних, т.к. в домашних используется Github Classroom. Но он может быть полезен для создания личных репозиториев, или для случаев, когда в задании явно указано, что необходимо создать репозиторий с нуля.

Создание удалённого репозитория это достаточно простая процедура. Для начала авторизуйтесь на GitHub, после чего нажмите на + в правом верхнем углу, и выберите там **New repository**.
![image](https://github.com/MMCS-FIIT/GithubGuide/assets/28728097/c6b4ed46-9ae6-4edd-af77-daef39225dd3)
В открывшемся окне вам необходимо ввести название вашего репозитория (называйте свои репозитории ёмко и кратко!). По желанию можете добавить описание. Тип репозитория выбирайте в зависимости от требований задания или своих целей. **Public** репозитории может просматривать, скачивать и т.д. любой человек, а **Private**, в свою очередь, только тот, кого вы добавите в коллабораторов. Вы можете создать readme файл, в котором можно описать важную информацию о данном репозитории (но будьте осторожны, в этом случае репозиторий будет не пустой при создании!). .gitignore и лицензию в большестве случаев можно не генерировать. Не забудьте нажать на кнопку **Create repository**.

Удалённый репозиторий создан! Теперь, чтобы начать его использовать, нужно связать его с локальным.

