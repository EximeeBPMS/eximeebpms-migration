# eximeebpms-migration - How to use it in your project


## Pom File

add this snippet to your maven pom.xml:
```xml
    <build>
        <pluginManagement>
            <plugins>
                <plugin>
                    <groupId>org.apache.maven.plugins</groupId>
                    <artifactId>maven-war-plugin</artifactId>
                    <version>3.5.1</version>
                </plugin>
                <plugin>
                    <groupId>org.openrewrite.maven</groupId>
                    <artifactId>rewrite-maven-plugin</artifactId>
                    <version>6.46.1</version>
                    <configuration>
                        <configLocation>
                            ${maven.multiModuleProjectDirectory}/replace-camunda-with-eximeebpms.yml
                        </configLocation>
                        <activeRecipes>
                            <recipe>org.eximeebpms.ReplaceCamundaWithEximeeBPMS</recipe>
                        </activeRecipes>
                    </configuration>
                </plugin>
            </plugins>
        </pluginManagement>
    </build>
```

## Rewrite configuration file
Download [replace-camunda-with-eximeebpms.yml](replace-camunda-with-eximeebpms.yml) into root dir of your project

## Run 
```bash
mvn rewrite:run
```

## Clean up

After the migration you can delete the configuration file and code snippet from your pom.xml

## README view analytics

This public README includes a [Scarf tracking image](https://docs.scarf.sh/web-traffic/)
to estimate interest in this repository. GitHub's image proxy and caching limit
counts and company attribution; these are not unique-reader or installation statistics.

<img alt="" width="1" height="1" referrerpolicy="no-referrer"
     src="https://static.scarf.sh/a.png?x-pxid=b3145a92-ad3c-4f20-bdbf-ae403eb3eb8c&amp;page=https%3A%2F%2Fgithub.com%2FEximeeBPMS%2Feximeebpms-migration" />
