While in the top-level directory, compile SampleAcn.java, SampleLoginModule.java, and SamplePrincipal.java:

`javac sample/SampleAcn.java sample/module/SampleLoginModule.java sample/principal/SamplePrincipal.java`

Execute the SampleAcn application

`java -Djava.security.auth.login.config==sample_jaas.config sample.SampleAcn`

You will be prompted for your user name and password, and the SampleLoginModule specified in the login configuration file will check to ensure these are correct. The SampleLoginModule expects "testUser" for the user name and "testPassword" for the password.

You will see some messages output by SampleLoginModule as a result of the debug option being set to true in the login configuration file. Then, if your login is successful, you will see the following message output by SampleAcn:

Authentication succeeded!
If the login is not successful (for example, if you misspell the password), you will see
Authentication failed:
followed by a reason for the failure. For example, if you mistype the password, you may see a message like the following:
Authentication failed:
  Password Incorrect
SampleAcn gives you three chances to successfully log in.