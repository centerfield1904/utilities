# UI

## Install nvm
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
```

## Install nvm, node, yarn
```bash
nvm install node --lts
nvm use --lts
npm install yarn
```

# DB
```
 brew install postgresql
 brew services start postgresql
```

To connect to the local postgres:
```
psql postgres
```

To search for different versions:
```
brew search postgres
```

# Scala

## Version Compatibility
Java11 (LTS) -> Scala versions: 3.0.0, 2.13.0, 2.12.4, 2.11.12
Play: 2.8.20

## Set Java version

1. Browse the java versions:
 ```bash
 ls /usr/local/opt/openjdk*
 ```

2. Set JDK version to 11:
 ```bash
 export JAVA_HOME=/usr/local/opt/openjdk@11
 ```

## Getting started with Play Framework

Setting up a Play Framework application using SBT involves several steps. Here, I'll guide you through the process of setting up a Play service from scratch.

1. **Install SBT:**
   Use homebrew:
   ```bash
    brew install sbt
    ```
   OR  
   You can download and install it from the [official SBT website](https://www.scala-sbt.org/download.html).

2. **Create a Play Framework Application:**
   Open a terminal and run the following command to create a new Play Framework application:
   ```bash
   sbt new playframework/play-scala-seed.g8
   ```
   Follow the prompts to provide a name for your application and other details.

3. **Navigate to the Project Directory:**
   Change to the project directory that was created by SBT:
   ```bash
   cd your_project_name
   ```

4. **Run the Application:**
   Start the Play application using SBT:
   ```bash
   sbt run
   ```
   This will start the Play development server. By default, the application will be accessible at `http://localhost:9000`.

5. **Access the Application:**
   Open a web browser and visit `http://localhost:9000`. You should see the default Play welcome page.

Now you have a Play Framework application up and running!

You can start building your application by adding controllers, models, views, and routes according to your project requirements. For more details on building Play applications, you can refer to the [official Play Framework documentation](https://www.playframework.com/documentation/latest/Home).


## Heroku Commands

Create a new Heroku App
```
 cd scala-getting-started
 heroku create
 git remote -v
```

Instructions to set port etc on heroku using Procfile
```
 vi Procfile
```

### Heroku Addons
Postgres Setup

```
 heroku addons:create heroku-postgresql:mini
 heroku addons

```

Postgres DB access
``` 
 heroku pg
 heroku open /database
 heroku pg:psql
 heroku open /database
 heroku pg:psql
```

Logging aggregator
```
 heroku addons:create papertrail
 heroku open
 heroku addons:open papertrail
 heroku addons
```

### Heroku Manage Webapp
Deploy changes
```
 git push heroku main
```

Scale up-down

```
 git push heroku main
 heroku ps
 heroku open
 heroku ps:scale web=0


 heroku ps
 heroku ps:scale web=1
 heroku logs --tail
```

Run Command on remote
```
 heroku config
 heroku run echo \$JDBC_DATABASE_URL
```



Run locally
```
 sbt stage
 vi .env
 vi .env
 psql
 psql postgres
 heroku local --port 5001
```

### Development

#### Contollerers
