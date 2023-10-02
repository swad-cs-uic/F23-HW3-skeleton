# Homework3 - Serverless GPT-484

## Must-read

### Installing required packages and setting up firebase.

- Creating and setting up firebase Project.

  1.  Go to firebase console and add a project.
  2.  While adding disable Google Analytics for the project.
  3.  On the project overview page, look-out for "Get started by adding Firebase to your app" and select Web.
  4.  Register your app by giving it a name. Once done you will be shown Step 2: Add Firebase SDK. Copy the firebase config from here and replace it accordingly in your .env file.
  5.  This is required for a client-interacting with Firebase service.
  6.  Next let's set-up the service/admin account that is responsible for managing Auth, writing to Firestore etc.
  7.  On the right of Project Overview button, click on Settings and select Project Settings. Go to service account, select Firebase Admin SDK.
  8.  Select Node.js and click generate new private key. The json file will be downloaded.
  9.  Once done, replace the keys from JSON file with the .env file accordingly.

- Make sure you have Java installed on your system. This is required for running Firebase emulator.
- Open the terminal window and type in `npm install`. This will install all the dependencies listed in the `package.json` file and will create a folder `node_modules` where all these dependencies will be installed.
- Next we install the firebase-tools and playwright chromium browser required for testing.
  1. `npm install -g firebase-tools`
  2. `npx playwright install chromium`
- If everything is set-up nice, you should be able to start by `npm run dev`
- The .env file provided in the template has a control switch called PUBLIC_EMULATOR and EMULATOR. Make sure these are set to 1 allowing you to use the emulator.
- `npm run dev` will run a local development server and open a web browser window for you that's pointed at your application.

## Skeleton code

The skeleton code of the application is designed to foster your knowledge on using serverless services and reactivity. This assignment can be considered as Assignment 2 on steroids. It uses [Astro](https://astro.build/) which allows you use components from different JS frameworks. Also provides flexibility of play between CSR and SSR. Firebase is being used to provide a serverless datastore that your application interacts with. Furthermore, the assignment also has a set emulator that allows you to develop and test your application connected with Firebase locally [including the Auth and Firestore], instead of affecting your Live Firebase account. With the end of this assignment you should have a good knowledge of how to convert a static-project to a dynamic project leveraging using one of the most in-demand serverless service. A fully application is a multi-user application for GPT-484.

## Navigating and starting project

Before running the project please make sure that you have installed all the dependencies mentioned in the step `Installing required packages`. Start the project by typing `npm run dev` in the terminal and open the URL in a browser.

When you browse the link, it should take you to the `Home` Page that will show you a Sign In and Create Account buttons. Explore the app by navigating to the various tabs to get a understanding about the features of the application.

To start navigating through the project start with the `index.astro` page inside src/pages. Being a Multi-paged application, every file in the pages directory corresponds to an URL endpoint.
By now you should able to see and locate the React-484 application. Yes, it's the same application that you created as part of Homework 2. You can now understand, how using Astro makes lives easier. And it's not just React. You can have different components coming from various frameworks and plug them inside your Astro App.

- Inside pages > there is an api directory. This is responsible for providing server-side interaction with the client. It has 2 sub-directories auth and chat, which are used by the client to maintain authenticity and interaction with Firebase.
- Inside src, the firebase directory sets up the client and server for you.
- Before jumping over any TODOs, I would highly encourage to understand the different parts of the application, and how they are interacting with each-other. How are layouts getting used, how are the APIs getting called. Understand what is SSR, what's the difference between CSR and SSR. How is this single application using a hybrid approach allowing SSR and CSR. It's always good to know what you're doing to make work exciting.

## Deliverables

Your code must function identically to the fully functional application.

1. There are TODOs and expected behaviors well commented for your reference.

2. As part of this assignment you are required to complete the Chat APIs that will enable storing and retrieval from Firestore.

3. You also need to complete the registration service for your application.

4. Once your APIs are set-up you then need to integrate the APIs in your landing component so that your data is now persisted across sessions and not just limited to a state.

5. This application will allow you to bring concepts from HW1 and HW2 to your HW3 as well.

6. A NOT DEFINED TODO that you must figure out on your own is how to enable Email based data fetch and store in the Landing component i.e the dashboard should only display the chats of the logged in user. The application allows multiple users to have their data stored in Firestore.

## Testing your code

Make sure you have a running local server before running the npm run test.

There are 2 ways to test ahead:

1. You can either do a `npm run test:integration` and this will spawn the firebase emulators for you and run the vitest. This is typically done in CI environments.
2. You can do a `firebase emulators:start` and this will spawn the interactive firebase emulators. You can browse the URL generated and view the emulator over your browser. Typically recommended while testing and checking the state of your Firestore and Auth service.

As with other assignments, any reasonable-quality test cases that you provide to the class (integration or unit, take your pick) will be eligible for extra credit.

**IMPORTANT**: Test cases are not a list of TODOs. Many students had difficulty getting started on the previous assignment because they took the grading criteria / test cases as an ordered list of TODOs. Please take stock of the full application and requirements before you start writing your code; it will probably be worth your time to stand in front of a whiteboard and build an understanding of the application structure before choosing where to add what.

## Points

| Task                               | Points |
| ---------------------------------- | ------ |
| Component Functionality            | 13     |
| Serverless functionality           | 17     |
| CI Tests (Lint, Format, Typecheck) | 3      |

## Due date

This assignment is due on Friday, October 20th, at 3:00PM. You are highly encouraged to get started early.
