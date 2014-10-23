<p align="center">
    <img src=".github/images/camunda.png" alt="camunda" title="camunda"/>
    <h1 align="center">Camunda BPM Standalone for ...</h1>
</p>

<p align="center">
    <a href="http://www.heroku.com" target="_blank">
        <img src=".github/images/heroku.png" alt="heroku" title="heroku"/></a>
    <a href="http://tomcat.apache.org" target="_blank">
        <img src=".github/images/tomcat.svg?" alt="tomcat" title="tomcat"/></a>
    <a href="http://www.postgresql.org" target="_blank">
        <img src=".github/images/postgresql.svg?" alt="postgresql" title="postgresql"/></a>
</p>

## How to deploy Camunda BPM Standalone on Heroku?

Either you just push that button... :-)

[![Deploy](.github/images/heroku-button.png)](https://heroku.com/deploy)

... and you will be asked to decide about the needed camunda BPM version on the next page.

Or if you prefer the command line:

```bash
git clone git@github.com:allanavelar/heroku-camunda-webapp.git
cd heroku-camunda-webapp
heroku create --region us
git push heroku master
heroku open
```

That's all there is to it. **Have fun!** Then **star** this repository :-), but also have even more fun and ...

## Deploy a different (than default) version

If you don't want to use the button above, just set the pom.xml property `camunda-bpm.version` - and you are done. Or, as a second possibility you can set an environment variable called CAMUNDA_BPM_VERSION:

```bash
heroku config:set CAMUNDA_BPM_VERSION=7.2.0-alpha5
```

The maven build creates a war overlay and uses a defensive xsl:stylesheet to add the postgres configuration required for Heroku to camunda's applicationContext. So everything *should* continue to work fine, even if that applicationContext changes in the future. If not, please report an issue here at GitHub!
