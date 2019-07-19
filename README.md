# wakala-android-deployment-steps
Deployment guide for production build and deployment.

### Git Project Workflow
1. Create a new branch from the current working branch possibly ( feature-[name] / bug-fix-[bugId] / hotfix-[bugId] )
2. Name the new branch with **release-[versionName]**
3. Switch to newly created branch and continue with 
[Release Config](https://github.com/karlptrck/wakala-android-deployment-steps#release-config)
and
[APK Packaging](https://github.com/karlptrck/wakala-android-deployment-steps#apk-packaging)
4. **Once build was deployed successfully to the App Store**, 
merge the **release branch** back to **dev and master branch** and delete it afterwards.

### Release Config
- Go to app/build.gradle
- increment the **versionCode** ( versionCode + 1 )
- increment the **versionName** base on the changes Major.Minor.Patch ex. (1.0.9)
- commit and push

### APK Packaging
- Go to Build -> Generate Signed APK -> Select APK
- Update the keystore path
- Enter keystore password
- Enter key alias
- Enter key password
- Flavors List will be shown as follows:
  - devDebug
  - devRelease
  - prodDebug
  - **prodRelease** <-- select this
- Tick both signature versions (V1 Jar Signature) (V2 Full APK Signature)
- Click Finish
- Locate the APK file at this path ( <project_path>/app/prod/release/app-prod-release.apk )

### Google Play AppStore Upload
To be continue...
