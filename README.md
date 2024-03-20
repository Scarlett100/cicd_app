
# <center> CI/CD <center/>


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


# Next to do:

* CD
*   

#  <center>  Jenkins  <center/>


Everything we do on Jenkins is called a job.

to create a jenkins build we must select *new item* and then *name* our project and select *freestyle*. 

![alt text](<../Screenshot 2024-03-20 at 11.52.37.png>)
![alt text](<../images/Screenshot 2024-03-20 at 11.19.40.png>)

<br>

Next choose **discard old jobs** and as a **maximum number of builds to keep** select 3. 

At present we are skipping the other options so scroll down to **add build step** or you can navigate across the top to **build** and choose the 3rd option: **execute shell**
![alt text](<../Screenshot 2024-03-20 at 11.55.28.png>)


Just as a test this is the data I entered:
``` 
whoami
hostname
uname -a
``` 
<br>
Once job is saved click **build now**:
<br>


![alt text](<../Screenshot 2024-03-20 at 11.38.10.png>)

As you can see below we have a **succesful build**:
<br>
![alt text](<../images/Screenshot 2024-03-20 at 11.31.41.png>)


## Link the first job to second:


Now that both jobs have been succesful:

one first job hover over in homepages and choose configure

![alt text](<../Screenshot 2024-03-20 at 12.02.53.png>)

![alt text](<../Screenshot 2024-03-20 at 11.44.04.png>)

Then save and click **build now** you will then see the app history.
![alt text](<../Screenshot 2024-03-20 at 11.49.39.png>)


Can check console outlook and you can see it has triggered the second job.

![alt text](<../Screenshot 2024-03-20 at 11.48.10.png>)


# References

https://medium.com/@ahshahkhan/devops-culture-and-cicd-3761cfc62450
https://aws.amazon.com/devops/continuous-integration/\https://scaledagileframework.com/continuous-integration/
https://scaledagileframework.com/continuous-integration/#:~:text=Continuous%20integration%20is%20a%20critical,potentially%20deployable%2C%20even%20during%20development.
