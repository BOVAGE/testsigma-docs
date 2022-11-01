# **Introduction**

With the massive [rise of API-first companies in fintech and](https://techcrunch.com/2022/06/18/the-rise-of-api-first-companies-in-fintech-and-beyond/) beyond, the API-first model of software development is now the trending or the most sought-after model in software development, especially if you will be offering services. This can be confirmed as [most of the biggest companies in tech](https://www.apifirst.tech/p/how-far-api-first-companies-have) are API-driven companies, e.g. [Amazon](https://www.amazon.com/), [GCP,](https://cloud.google.com/) etc.

It’s not a mistake to say that most applications and technologies we use today are typically calling one or more APIs or another behind the scenes. As a result, it’s important to automate and thoroughly test your API call sequences to match the intended application workflow and prevent encountering unexpected errors.

However, due to the rise in the demand for API services, it might be a difficult task to set up tests for multiple API endpoints you have for your services. In this guide, we will be exploring how to use [Testsigma](https://testsigma.com/) to automate testing APIs.

## What is Testsigma?

[Testsigma](https://testsigma.com/) is a customizable, open-source test automation platform that allows users to create automated tests for any scenario in minutes by either:

- Recording user actions.
- Writing tests in simple English statements (i.e. without writing any code!).

Testsigma can be used for the following types of testing:

- Testing a Web Application
- Mobile App Testing
- APIs Testing

This guide focuses on using Testsigma to automate the testing of APIs. By following this guide, you are going to learn the following:

- How to create automated tests for APIs
- How to automate your API call sequence to simulate your application's workflow
- How to save and reuse API response data automatically

## Pre-requisites

The following are needed to follow this guide:

1. Testsigma account (you can create one [here](https://testsigma.com/signup)).
2. Restful API endpoint Here is [the documentation of the Restful API](https://documenter.getpostman.com/view/20059082/) that will be used in this guide.
3. Link to the API repo: [https://github.com/bovage/quizBank/](https://github.com/bovage/quizBank/)

# Getting Started with API testing with Testsigma

1. Head over to the [Testsigma](https://testsigma.com/) website and sign up if you don’t have an account.
2. Click the logo icon highlighted in the image below or the [Testsigma dashboard](https://app.testsigma.com/ui/dashboard) to access your dashboard.
3. Click on the Plus ( `+`) icon on the left-hand pane on your dashboard to create a new project.
![image](https://user-images.githubusercontent.com/37651620/199046629-93e269b9-3851-4392-994f-d682b53b875b.png)
4. Click on "Project" in the new menu that appears. A new window will show up.
![image](https://user-images.githubusercontent.com/37651620/199046644-3969e201-5e61-4d56-b619-d1029eb01645.png)
5. In the new window, type in the project’s name and a project description (optional). Also, select the project type and specify the version. Since this guide is based on Rest API testing, pick Rest API as the project type.
6. Click on the `Create` button at the top of the page.
7. Once the project is successfully created, you will get a notification at the bottom left corner of the page to indicate the project has been created.
8. A new window shows up similar to the one in the image below.
![image](https://user-images.githubusercontent.com/37651620/199046660-b7b221f5-2ed6-4d5d-9081-7319380c65a5.png)

> Read on to know about how to create test cases.

## Creating Test Cases for API with Testsigma

Let's create a test case now that you have set up your project in Testsigma.

1. On the dashboard page, click on the pencil icon to open your editor, located on the left-hand pane.
![image](https://user-images.githubusercontent.com/37651620/199046681-96530dce-cf4e-4cff-ab55-8c246254dacc.png)
2. Click on `Test development` on the options menu that appears.
3. Click on the `Create Test Case` button at the center of the new page.
4. Enter the name into the input field (required). The name entered will serve as the title for the test case you are about to create.
![image](https://user-images.githubusercontent.com/37651620/199046701-0ae6469c-e9e8-4aad-b823-771a3479b807.png)
5. After entering the name, click on the `Write Test Manually` button.
6. A new window showing the newly created test case is displayed.
![image](https://user-images.githubusercontent.com/37651620/199046767-e22b6eb3-0381-41f4-a83f-d139a23d4892.png)
7. Click on a test case on the list to get to its details page where you can start writing test steps in a simple English statement.
8. Click on the input field that has a placeholder of `Enter your title here`. The API Test Step page will open, as shown below:
![image](https://user-images.githubusercontent.com/37651620/199046796-e6b0aa4a-e92b-470f-be8f-2d0debde4ea4.png)

> Note: Since the Application type is REST API Testing, All test steps are by default REST API steps.
> 

When hovering over the symbol beside the input field, you can see that type of REST API is defined. See below image
![image](https://user-images.githubusercontent.com/37651620/199046813-9925d561-aa2f-46f7-9930-af47257e1fee.png)

9. Enter the request details. The following are the request details required:
    - **Title**: Enter a title for the test step.
    - **URL**: The web address endpoint of the RESTful Web Service to perform testing on
    - **HTTP Methods**: Select from one of the `HTTP` request types to perform: `GET`, `POST`, `PUT`, `PATCH`, `DELETE`.
    - **Header**: Add headers that are expected for this REST API.
    - **Authorization**: Choose the appropriate `Authorization` type and provide the required data.
    - **Payload**: Enter the Request Body to be sent for POST, PUT, and DELETE request types.
    - **Response Preview**: You can preview the response by sending the above REST API details to make sure the provided details are proper.

> As earlier mentioned, in this guide, you can use this RESTful API endpoint:

10. After adding the URL, setting the HTTP method to post (since we want to create a question), bearer token, and payload, click on the `Send` button. The response preview will contain the response from the API.
![image](https://user-images.githubusercontent.com/37651620/199046837-4136ee26-c92c-4325-a207-8a1605b7ef83.png)
11. Click on the `Verify Response` on the breadcrumb above the form.

Listed below are the details you will need to fill

- **Expected Status Code**: The expected status code from the given REST API
    > Since we are creating a question, the expected status code is                                     201.
    > 
- **Expected Header Content**: If you want to verify the response headers, add them here.
- **Body Compare Type**: Here you choose an appropriate data comparison type to be used to verify the response body. The following are the data comparison types you can choose from:
    - ***Strict***: Not extensible and strict array ordering.
    - ***Lenient***: extensible and non-strict array ordering.
    - ***Non-extensible***: not extensible and does not adhere to strict array ordering.
    - ***Strict order***: extensible and strict array ordering.
    - ***JSON Schema***: validates the JSON schema of the response body.
    - ***JSON PATH***: validates data using JSON Path.
- **Expected Body Content**: Expected response body. The comparison type you selected in the Body Compare Type field will be used to perform the validation.
![image](https://user-images.githubusercontent.com/37651620/199046906-95608c32-d894-42c8-82fd-0bee25e12bd4.png)

12. After entering all these details, click on `Store Response` on the breadcrumb above the form if you are interested in storing API responses.
![image](https://user-images.githubusercontent.com/37651620/199046926-6cefa684-67a1-46e4-b292-6b637ab2448d.png)
13. You can store the API response data in runtime variables for further use in any test cases that are part of this run. There are different categories of Store API Responses available for you to choose from.
    - **Store Response as Metadata**: Check this option to store the response as metadata for debugging purposes. The response will be displayed as part of the test step result.
    - **Header Runtime Data**: You can store the response headers in runtime variables for further use.
    - **Body Runtime Data**: You can store the response body in runtime variables for further use. You can use JSON Path to identify the node that has to be stored.
14. After entering these details, click on the `Create` button at the bottom of the form to create the test step.

## Executing Test Case in Testsigma

Now that you’ve defined your test case structure, let’s look at how to execute the cases.

1. Click on the `dry run` tab.
![image](https://user-images.githubusercontent.com/37651620/199046945-e7fdc383-8462-4c07-9f08-2d981cfcea71.png)

2. Click on the `Run Test Case` button highlighted in the image above.

> Note: The above page only shows up if you have not run any tests previously. If you have run some tests previously, you should see some results. In order to then run a test, click on the Run button on the top right corner of the page. See the below image.
> 

![image](https://user-images.githubusercontent.com/37651620/199046956-ba70b9ab-c8bb-426d-8e0e-450cf1ff50c4.png)


3. After clicking the Run or Run Test Case button, you will get a form on the right side of the page. The form prompts you to select the lab where you want the test to run. You could choose:
- **Testsigma Lab**: You can run tests on Testsigma's own cloud infrastructure.
- **Local Devices**: This option allows you to run tests on your local machine.
![image](https://user-images.githubusercontent.com/37651620/199046995-331e6acb-9a3b-459d-b42f-a467a46dd721.png)
- Select Testsigma Lab and click on the Run button in the bottom right corner of the form.
- If you have the test set up correctly, the test run should pass, and if it does not, you will get detailed information about what is wrong.

> Note: You should be careful when testing an API response body that includes an id or content that can’t be determined until a request is made. You must know what the id response or the content will be when the API request is being made so the test can run correctly and pass.
> 

# Conclusion

You have just finished reading a guide to Test Automation with Testsigma. You now know why and how you can test APIs intuitively—without writing any code!

Go and have some fun testing, validating, and troubleshooting APIs—you'll probably find a bug while you're at it.