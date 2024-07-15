# AmplifyGen2
Step A: Setup Github.com for keepdevops in antman profile.

Step B: Connect to AWS account keepdevops root account.
Sign in.

Step C: Set permissions of root and mfa.
Step D: Review instructions of Gen2 - SeeHowItWorks in AWS.
Step E: QuickStart Amplify then download outputs.json move to d:/A/Amplify/...
STEP  E: Setup user role. 
STEP F: Setup up AWS Cli for Amplify. 
STEP G: Setup in California region.
setup keys ssh -i keygen
Manual Installation Instructions Amplify Gen2:
npm create amplify@latest
Step 1: Manual Setup:
npm add --save-dev @aws-amplify/backend@latest @aws-amplify/backend-cli@latest typescript
Step 2: Create Entry point: Backend amplify/backend.ts
import { defineBackend } from '@aws-amplify/backend';

defineBackend({});

Step 3: Create a local file Amplify backend directory:
{
  "type": "module"
}
Step 4: define your resources. Ex. Authentication:
import { defineAuth } from '@aws-amplify/backend';

export const auth = defineAuth({
  loginWith: {
    email: true
  }
});
Step 5: Define your data resources: amplify/data/resource.ts
import { a, defineData, type ClientSchema } from '@aws-amplify/backend';

const schema = a.schema({});

export type Schema = ClientSchema<typeof schema>;
export const data = defineData({
  schema
});
Step 6: These new defined resources are imported and set to: amplify/backend.ts
import { defineBackend } from '@aws-amplify/backend';
import { auth } from './auth/resource';
import { data } from './data/resource';

defineBackend({
  auth,
  data
});
Step 7: Upgrade existing Projects using npm.
npm update @aws-amplify/backend@latest @aws-amplify/backend-cli@latest

Step 8: Next steps--Set up Amplify Auth, 






Step *: NodeJs.org Installation and check with node --verison
Node.jsv22.4.1 documentation link:
https://nodejs.org/api/esm.html


Installation: @aws-amplify/ui-react with npm
npm install @aws-amplify/ui-react aws-amplify
Styles: Amplify UI JS, CSS
import '@aws-amplify/ui-react/styles.css';
@import "@aws-amplify/ui-react/styles.css";
CSS Layers:
import '@aws-amplify/ui-react/styles/reset.layer.css' // global CSS reset
import '@aws-amplify/ui-react/styles/base.layer.css' // base styling needed for Amplify UI
import '@aws-amplify/ui-react/styles/button.layer.css' // component specific styles
Main CSS export:
You can also use this for the main CSS export, '@aws-amplify/ui-react/styles.layer.css'.
Fonts:
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
  href="https://fonts.googleapis.com/css2?family=Inter:slnt,wght@-10..0,100..900&display=swap"
  rel="stylesheet"
/>
or
@import url('https://fonts.googleapis.com/css2?family=Inter:slnt,wght@-10..0,100..900&display=swap');
NPM dependency: 
npm install @fontsource/inter
Import variable font for application
import '@fontsource/inter/variable.css';
Check out FontSource.org

UI - React installation commands
npm install @headlessui/react
UI - Vue installation commands
npm install @headlessui/react
