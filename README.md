## To reproduce issue https://github.com/forcedotcom/cli/issues/2002

- Clone repo
- Run `sfdx force:org:create -s -d 1 -f config/project-scratch-def.json`
- Confirm source deploy works as expected `sfdx force:source:deploy --checkonly -x package.xml --verbose`
    - Steps completed to repo setup (can skip):
        - Convert source to metadata format: `sfdx force source convert -d metadata -p force-app`
        - Update `metadata/package.xml` to match the `./package.xml` file 
- Run `sfdx force mdapi deploy -d metadata -w=-1 --checkonly --verbose`
- Note error `label_two Not in package.xml`