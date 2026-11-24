# Public Health Survey Platform

A responsive front-end prototype for an administrator-managed public health survey website.

## Run locally
Open `index.html` in a modern browser. No installation is required.

## Administrator workflow
1. Create the administrator account on first use.
2. Sign in.
3. Create a survey in Survey Builder.
4. Set its status to **Publish and accept responses** and save.
5. In **My surveys**, use **Share link** on the published survey.

## Anonymous respondent workflow (prototype)
- Respondents open the survey URL without creating an account or signing in.
- They complete the questions and consent checkbox, then submit.
- The prototype stores answers in the browser's localStorage.
- It prevents a second submission from the same survey in the same browser profile using a local browser flag.
- The administrator can view the stored answers in Responses and export them as CSV **only when those responses are stored in the same browser profile**.

## Important limitations before public use
This is a static front-end demonstration, not a hosted multi-user survey service. Browser localStorage is separate on each device/browser. Therefore:
- A respondent using another device/browser does not receive the administrator's saved survey data from this static prototype.
- A response submitted on another device does not sync to the administrator's dashboard.
- The one-submission check is only per browser profile and can be bypassed by clearing browser data or using another browser/device. It does not prove one response per real person.
- A `file://` link is local to the device and cannot be shared publicly.

For actual public distribution, deploy the site over HTTPS and connect a shared backend/database. The backend must serve published survey definitions, store submissions centrally, and enforce duplicate-submission policy. True one-response-per-person enforcement while preserving anonymity needs a carefully designed privacy-preserving mechanism (for example, a one-time invitation token or independent eligibility verification); a simple anonymous public link cannot identify a person and guarantee this by itself.

Do not collect real or sensitive health information with this prototype. Before production use, add server-side authentication and authorization, HTTPS, secure storage, backups, audit logging, consent and retention workflows, abuse protection, and appropriate legal / ethics review.
