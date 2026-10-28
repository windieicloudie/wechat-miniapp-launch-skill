# Registration, compliance, review, and release

## 1. Preparation inventory

Collect before starting:

- proposed Chinese/English name and alternatives;
- avatar/logo and concise introduction;
- administrator's WeChat, phone, email, and identity details;
- valid organization or individual-business documents when applicable;
- intended service category and qualification documents;
- actual feature/data/permission map;
- customer contact email;
- repository path, build command, formal AppID, and version description;
- test instructions/account only if login is required.

Do not collect or display AppSecret in chat. If the app has a backend, configure secrets server-side.

## 2. Choose the subject

Choose based on the intended operating model, not merely the cheapest registration path:

- **Personal:** suitable for a free validation tool when its category is open to personal subjects. Direct transaction and category capabilities are restricted.
- **Individual business/organization:** usually required for payment, broader commercial functions, and some categories/qualifications.

Verify current rules in the live console and official documentation. Subject migration directions are restricted and may require review, documents, fees, or a new account. Do not assume an organization can migrate to a personal subject. Do not use a dissolved or unauthorized organization merely to retain capabilities.

## 3. Formal AppID and upload

1. Obtain the formal AppID from the newly registered Mini Program.
2. Search the repository for old/test AppIDs and replace the project configuration intentionally.
3. Reopen/import the project in Developer Tools so it reloads project metadata.
4. Confirm the displayed AppID and logged-in developer authorization before upload.
5. Build the latest source and preview on a phone.
6. Upload with a semantic version and factual version description.

Upload is not publication. The normal chain is:

`local build → preview → upload → development version → experience version → review → approved version → publish`

After upload, create an experience version and run the physical-device regression against the formal AppID.

## 4. Service category and descriptions

Select the narrowest category that describes the dominant user-facing service. Avoid choosing a regulated or commercial category merely because some wording overlaps. Check whether the category is open to the selected subject and whether qualifications are required.

Keep the Mini Program introduction, operating/service description, version description, and review notes aligned. Describe observable features and explicitly state absent high-risk functions when useful: no login, no payment, no public user-generated content, no medical/financial advice, or no prediction/guaranteed outcome. Do not disguise an actual regulated function with softer wording; change the product or obtain the correct qualification.

## 5. Privacy and permissions

Derive declarations from the data/permission map and source scan.

- Information entered by a user and processed locally is still information processed by the Mini Program.
- Select “collects/processes user privacy” when the app accepts birth date, location text, contact details, profile data, or similar personal information, even if stored only on-device.
- Declare optionality, purpose, storage location, retention, sharing, edit/delete route, and contact method.
- Declare write-only album access accurately: saving a generated image does not mean reading the album.
- Do not declare GPS/location APIs if the app only accepts manual city input.
- Request permission in response to a user action and provide denial/recovery UX.

Suggested local-only wording pattern:

> The information entered by the user is used only to provide the stated feature, stored locally on the user's device, not uploaded to a server or shared with third parties, and can be edited or removed by the user.

Use the platform's generated privacy guide. An optional supplemental `.txt` document is unnecessary unless the default guide cannot accurately explain the processing.

## 6. Filing

New Mini Programs operating in mainland China generally require filing before publication. Use the console's current filing flow and official guidance.

For a typical non-commercial personal tool:

- filing type: new filing;
- subject: the registered individual;
- service nature: non-commercial internet information service;
- service description: factual description of the tool;
- pre-approval: only when the service actually falls into a regulated field.

Expect platform preliminary review, identity/face verification where requested, Ministry of Industry and Information Technology SMS verification, and communications-administration review. Tell the user to act within the deadline stated in the SMS and keep the registered phone reachable. Do not promise a fixed approval time.

## 7. Review and publication

Before submission confirm:

- experience version matches the uploaded version;
- service category is valid for the subject;
- privacy guide and collected-information setting are published;
- filing state permits release;
- all primary functions are reachable without hidden instructions;
- test account and steps are supplied if login is required;
- review notes explain permissions and optional information;
- there are no guaranteed-benefit, prohibited, or misleading claims.

Submit the stable version and avoid uploading unrelated changes during review. If rejected, preserve the exact rejection text and screenshot, map each reason to code/content/category/qualification, fix only verified causes, regression test, increment the version, and resubmit.

After approval, publication is still a deliberate action. Publish, then run a production smoke test from search/QR entry, verify permissions and core tasks, and record the production version and release time.
