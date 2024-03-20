
# <center> CI/CD <center/>

![alt text](diagram.png)
## What is CI?


The DevOps practice of automating build and running tests after a group of devs have frequently merged there code into a central place (repository) is called Continuous Integration or CI. The goal of CI is to reduce the time taken to find and fix bugs, release software and improve general software quality

## Where is CI?

With continuous integration, it is always possibly deployment ready, even during development as  the system always runs.


## Why do we use CI?

Previously developers would work in isolation and not push code frequently, only when work was completed. The effects of this were that bugs would go unnoticed for a long time, and therefore take longer to fix. In the longterm, quickly delivering updates to customers became very difficult. CI solves this issue. The quick feedback is necessary for quick deployment

## How do we use CI?

As aforementioned, developers commit code to their shared repository frequently with Version Control systems like Git. Devs will normally run theor own unit tests to provide an additional check before merging with other devs code. Then a CI service such as Jenkins will automatically build and run tests on new code.

An example of CI within agile development:
<br>
*   Develop: Develop describes the practices necessary to implement stories and commit the code and components to version control 
*   Build: techniques needed to create files & merge development branches into main.
*   Test: Test end-to-end describes the testing to ensure we have reached our solution.
*   Stage describes the steps required to host and validate solutions in a staging environment before production

![alt text](<../images/Screenshot 2024-03-20 at 10.18.46.png>)


## When do we use CI?

Ideally before you build it is best to start your pipeline build plan.



#  <center>  Jenkins  <center/>

Jenkins is a self-contained, open-source automation server used to assist in automating a variety of tasks in regards to building, testing, delivering, and deploying software. It allows us to help the process of continuos integration and continuos delivery

Jenkins can be installed through native system packages, container tools such as Docker, or simply ran standalone by a machine with the Java Runtime Environment (JRE) installed.
Everything we do on Jenkins is called a job.

To create a jenkins build we must select **new item**, **name** our project and select **freestyle**. 
<br>

![alt text](<Screenshot 2024-03-20 at 11.52.37.png>)

![alt text](<../images/Screenshot 2024-03-20 at 11.19.40.png>)

<br>

Next choose **discard old jobs** and as a **maximum number of builds to keep** select 3. 

At present we are skipping the other options so scroll down to **add build step** or you can navigate across the top to **build** and choose the 3rd option: **execute shell**
![alt text](<Screenshot 2024-03-20 at 11.55.28.png>)


Just as a test this is the data I entered:
``` 
whoami
hostname
uname -a
``` 
<br>

Once job is saved click **build now** :

<br>

![alt text](<Screenshot 2024-03-20 at 11.38.10.png>)


As you can see below we have a **succesful build**:
<br>
![alt text](<../images/Screenshot 2024-03-20 at 11.31.41.png>)


## Link the first job to second:


Now that both jobs have been succesful:

In the homepages on our first job hover in homepages and choose configure

![alt text](<../Screenshot 2024-03-20 at 12.02.53.png>)


Now within **Post-build Actions** choose to **trigger only if build is stable**.
<be>

![alt text](<Screenshot 2024-03-20 at 11.44.04.png>)

Then save and click **build now** you will then see the build history click on the build you want.

![alt text](<Screenshot 2024-03-20 at 11.38.10.png>)
![alt text](<Screenshot 2024-03-20 at 11.49.39.png>)

You can then check **console outlook** and you can see it has triggered the second job.

![alt text](<Screenshot 2024-03-20 at 11.48.10.png>)


#  Build with github:


## Github
First you must make sure the repo is linked to a specific key. so create a key in your terminal then go to **settings** within repo, **deploy keys** and input your private key, avoiding whitespaces. Next allow write acces so we can pull as well as push.

## Jenkins
Next we go over to Jenkins and select **new build**

* First:we used the **HTTPS** link to repo and inputted that. 

![alt text](<Screenshot 2024-03-20 at 13.33.09.png>)

* Next we chose our label expression:
  
![alt text](<Screenshot 2024-03-20 at 13.34.10.png>)

* After this, we used the ssh of our git repo link:
![alt text](<Screenshot 2024-03-20 at 13.35.40.png>)

* There after we linked our key. by choosing the options below and inputting our **Private key* including the 
  * -----BEGIN OPENSSH PRIVATE KEY-----
  * -----END OPENSSH PRIVATE KEY-----
  * All the whitespace after the end private key

![alt text](<Screenshot 2024-03-20 at 12.22.58.png>)

I had a few blockers and so had to choose make the same one 3 times.
when I choose my key it is the 3rd one called: **ci_cd_spartaa** .It was beacuse I was not copying the whitespace, but i should have been from top to bottom as below. The reason I didn't rename it is I was unsure if it needed to match the username on github

![alt text](<Screenshot 2024-03-20 at 12.38.04.png>)

![alt text](<Screenshot 2024-03-20 at 12.35.47.png>)

# References

https://medium.com/@ahshahkhan/devops-culture-and-cicd-3761cfc62450
https://aws.amazon.com/devops/continuous-integration/\https://scaledagileframework.com/continuous-integration/
https://scaledagileframework.com/continuous-integration/#:~:text=Continuous%20integration%20is%20a%20critical,potentially%20deployable%2C%20even%20during%20development.