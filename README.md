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
                    <version>3.3.2</version>
                </plugin>
                <plugin>
                    <groupId>org.openrewrite.maven</groupId>
                    <artifactId>rewrite-maven-plugin</artifactId>
                    <version>6.3.2</version>
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
