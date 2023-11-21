# ConfUsersWithOrganization
How to Configure users using Organization and IAM Identify Center

<h1>How to Configure users using Organization and IAM Identity Center</h1>
<div><b>Creation Date:</b> November 21, 2023</div>
<div><b>Created By:</b> Yeison Giraldo</div>

<div style="height: 24px">&#8203;</div>
<hr />
<div style="height: 24px">&#8203;</div>


<div><h3>1. What you will accomplish</h3>
<p>you will learn how to:</p><ul><li><p>Sign in as the root user</p></li><li><p>Enable additional security for the root user</p></li><li><p>Set up additional AWS IAM Identity Center (successor to AWS SSO) users</p></li><li><p>Sign in to the AWS access portal</p></li><li><p>Set up MFA for the Identity Center user</p></li></ul>
</div>

<div><h3>2. Root User</h3>
<p>When you create an AWS account, a root user is created automatically for your account. The root user is a special entity that has full access to the account, and can perform all actions, including changing the payment methods or closing the account. When you sign-in using the root user you have complete access to all AWS service and resources in the account. Due to this level of permissions, we recommend that you:</p><ul><li><p>Enable additional security for the root user with multi-factor authentication</p></li><li><p>Set up additional users to perform daily tasks related to your account</p></li></ul>
</div>

<div><h3>3. Two Identity Services</h3>
<ul><li><p><a target="_blank" rel="noopener noreferrer nofollow" href="https://aws.amazon.com/iam/"><strong><u>AWS Identity and Access Management (IAM)</u></strong></a>. This service provides access control policies and manages long-term users like the root user. If you create users in IAM, those users have long-term access credentials. As a security best practice, it is recommended that you minimize the use of long-term credentials in AWS. In this tutorial you will not create an IAM user.</p></li><li><p><a target="_blank" rel="noopener noreferrer nofollow" href="https://aws.amazon.com/iam/identity-center/"><strong><u>AWS IAM Identity Center (successor to AWS Single Sign-On)</u></strong></a>. This service provides temporary credentials that are granted each time a user signs in for a session. It can integrate with any existing identity providers you might already have, like Microsoft Active Directory or Okta, so that your users can use the same sign on for AWS as they use for other services in your organization. If you don't have another identity provider, you can create users in IAM Identity Center. This is the recommended way to create additional users for your AWS account and is the method we will walk through in this tutorial.</p></li></ul>
</div>

<div><h3>4. Sign in as Root user</h3>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/b96b754e-cf56-428a-af71-bdfc574e624e/9ed5cf81-da75-4cb6-8afd-8ad92e8ce505.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Sign in as Root user" />
</div>

<div><h3>5. Make sure you setup MFA</h3>
</div>

<div><h3>6. Set up users in IAM Identity Center</h3>
<p>It is considered a security best practice to not use your root account for everyday tasks, but right now you only have a root user. In this tutorial, we will use IAM Identity Center to create an administrative user. We are using IAM Identity Center because it provides users with unique credentials for every session, also known as temporary credentials. Providing users these credentials results in enhanced security for your AWS account, because they are generated each time the user signs in. Once you have an administrative user, you can sign in with that user to create additional Identity Center users and assign them to groups with permissions to perform specific job functions. Another benefit to creating users in IAM Identity Center is that the users are automatically granted access to the the <a target="_blank" rel="noopener noreferrer nofollow" href="https://us-east-1.console.aws.amazon.com/billing/home?region=us-east-1#/"><u>AWS Billing and Cost Management console</u></a>.</p>
</div>

<div><h3>7. Click on IAM Identity Center</h3>
<p>In the <a target="_blank" rel="noopener noreferrer nofollow" href="https://us-east-1.console.aws.amazon.com/console/home?region=us-east-1#"><u>AWS Management Console</u></a> search bar, enter <em>IAM Identity Center</em>, and then select <strong>IAM Identity Center</strong>.</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/cba97d36-8965-4a26-be71-c0186c13ca7d/f49a59c5-4bca-423d-ad62-0041d1bc27ce.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.3556&fp-y=0.3255&fp-z=2.4588&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=443&mark-y=326&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0zMTUmaD00NyZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Click on IAM Identity Center" />
</div>

<div><h3>8. Enable IAM Identity Center</h3>
<p>The <strong>IAM Identity Center service</strong> overview page opens. Review the information to learn about the features of the IAM Identity Center service, then under <strong>Enable IAM Identity Center</strong>, choose <strong>Enable</strong>.</p><ul><li><p>To use IAM Identity Center, you also need to enable AWS Organizations. AWS Organizations lets you organize multiple AWS accounts so that you can have separate AWS accounts for different use cases. AWS Organizations is a feature of your AWS account offered at no additional charge.</p></li></ul>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/0db1c767-6ac2-4fe1-ad44-f90d73f4d3ec/9e21500c-92e0-4454-a0f6-941fa1f6a355.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Enable IAM Identity Center" />
</div>

<div><h3>9. To continue choose Create AWS organization</h3>
<ul><li><p>The management account for the AWS Organization is now the root user</p></li><li><p>After enabling AWS Organizations, AWS will send a verification email to the root user. Verifying your root user account allows you to invite other accounts to become members of your organization. You don’t need to verify your account before continuing with this tutorial. For more information about account management, see the <a target="_blank" rel="noopener noreferrer nofollow" class="markup--anchor markup--li-anchor" href="https://docs.aws.amazon.com/organizations/latest/userguide/orgs_introduction.html">AWS Organizations</a> user guide.</p></li></ul>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/aa20391c-2559-49bf-9d0d-2d6fbee61145/2a119049-21f3-4f45-876d-6c83188cfddd.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="To continue choose Create AWS organization" />
</div>

<div><h3>10. Configure your Identity Source</h3>
<p>Set up your identity source to manage users and groups. Once configured, you can easily locate users or groups for providing single sign-on access to AWS accounts, cloud applications, or both.</p><p></p><p>Organizations can have only one identity source. Options include:</p><p></p><p><strong>Identity Center Directory:</strong><br>When you activate IAM Identity Center, it automatically establishes an Identity Center directory as the default identity source. This directory is where you’ll oversee user and group management.</p><p></p><p><strong>Active Directory:</strong><br>Users and groups can be administered in either the AWS Managed Microsoft AD directory through AWS Directory Service or your self-managed Active Directory (AD).</p><p></p><p><strong>External Identity Provider:</strong><br>Users and groups can be supervised through an external identity provider (IdP) such as Okta or Azure Active Directory. </p>
</div>

<div><h3>11. Step 2: Add users</h3>
<ol><li><p>Access the IAM Identity Center console and click on “Users.” From there, choose the option to add a new user.</p></li></ol>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/8bfb3a7e-f612-4620-a94c-222bb8b828b6/4aa15d8c-873b-4586-a00c-3b75cdb3d9cc.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Step 2: Add users" />
</div>

<div><h3>12. On the "Specify User Details" page, provide the following information:</h3>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/bc4bcfed-af18-4afc-840c-5a36c5ded40e/25ea85b2-fd55-484c-82ec-f27081f6d6be.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="On the &quot;Specify User Details&quot; page, provide the following information:" />
</div>

<div><h2># Step 3: Add user to groups</h2></div>

<div><h3>13. Step 3: Add user to groups</h3>
<p>Utilizing user groups allows you to define permissions for numerous users, simplifying the process of managing their respective permissions.</p><ul><li><p>Select <strong>Create Group</strong></p></li></ul>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/e99361f5-3197-414a-b610-51b476d00d07/d2dc41e4-6536-4a38-b46b-5d5a0b534947.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Step 3: Add user to groups" />
</div>

<div><h3>14. A new browser tab opens to display the Create group page.</h3>
<ul><li><p>Under <strong>Group details</strong>, in <strong>Group name</strong>, enter <em>Admins.</em></p></li></ul><ul><li><p>Select <strong>Create group</strong>.</p></li></ul>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/a5647b06-5381-40b0-9e7d-51efee5eda4a/84f9f937-b318-411c-896c-37ecac4541ae.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="A new browser tab opens to display the Create group page." />
</div>

<div><h3>15. Close or move away from the Groups browser tab and go back to the Add user browser tab.</h3>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/896c0268-e6d3-4317-a440-3dbbbcc5b8dd/5943bc95-8399-4948-9a2d-c5eab0390df8.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Close or move away from the Groups browser tab and go back to the Add user browser tab." />
</div>

<div><h3>16. Within the Groups section, click on the Refresh button.</h3>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/f71f45ae-bf9a-49df-8610-3838a5481794/064d929f-9e83-452f-852e-f27bc4e5e4cc.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Within the Groups section, click on the Refresh button." />
</div>

<div><h3>17. The new Admins group appears in the list.</h3>
<ul><li><p>Tick the checkbox adjacent to the Admins group, and subsequently click on “<strong>Next</strong>.”</p></li></ul>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/84f5e31a-7b3e-4f40-9bc4-ca458c0c3b6b/3fb3b75d-1ad1-49b8-88e0-40f537c199ea.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="The new Admins group appears in the list." />
</div>

<div><h3>18. On the "Review and Add User" page, ensure the following:</h3>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/a4f77b5f-afab-4467-96fd-1f004a332f82/7fedab52-7f3a-43a0-9d90-b7626fbe6373.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="On the &quot;Review and Add User&quot; page, ensure the following:" />
</div>

<div><h3>19. You will be directed back to the main IAM Identity Center > Users page, where a notification confirms the successful addition of the user.</h3>
<p>Congratulations! You have successfully added a user to your AWS Organization. Feel free to replicate these steps to include more users and groups as needed.</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/b27b67d3-c7a2-414f-a479-15c0a92bfd4f/f8f30976-c6c4-40d1-b619-86b4a958a8a6.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="You will be directed back to the main IAM Identity Center &gt; Users page, where a notification confirms the successful addition of the user." />
</div>

<div><h2># Administer access to your AWS account</h2><p>While your new user has been created, they currently lack access to any resources, services, or applications. As a result, the user cannot yet take over daily administrative tasks from your root user. To grant access, we will associate the user’s group with an account and then add a permission set outlining what group members can access.</p><p>For this process, continue using the root user credentials.</p>
</div>

<div><h2># Step 4: Create an administrative permission set</h2></div>

<div><h3>20. Manage access to multiple AWS accounts</h3>
<p>Go to the IAM Identity Center console, and within the Recommended setup steps, select “Manage access to multiple AWS accounts.”</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/c6340729-c0e3-4cd3-ba0f-b37c1ad2b901/4ea59deb-5147-4cde-b500-eefe6bf42ce9.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Manage access to multiple AWS accounts" />
</div>

<div><h3>21. Assign users or groups</h3>
<p>On the <strong>AWS accounts</strong> page within <strong>Organizational structure</strong>, your root account is presented with the test account listed below in the hierarchy. Check the box next to your test account, and then choose “<strong>Assign users or groups</strong>.”</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/2a285542-e4fe-43f5-86f5-45d71b86cdb9/2a6cae61-5085-4080-a998-829886384695.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Assign users or groups" />
</div>

<div><h3>22. Step 1: Select Users and Groups</h3>
<p>The Assign Users and Groups process appears, comprising the following stages:<br>In <strong>Step 1: Select Users and Groups,</strong> opt for the Admins group established earlier in this tutorial. Proceed by selecting “<strong>Next</strong>.”</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/a9730251-662b-4862-bb46-59ddc44ff94b/a654cb55-7548-441c-86d7-f2f92ba2b3b2.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Step 1: Select Users and Groups" />
</div>

<div><h3>23. Step 2: Choose Permission Sets</h3>
<p>In <strong>Step 2: Choose Permission Sets</strong>, click on <strong>“Create Permission Set”</strong> to open a new tab guiding you through the three sub-steps associated with creating the permission set.</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/a27a1601-84c6-4056-8ffa-5883386cc6fd/06333fef-d7ff-476c-96e3-1d0aa8888466.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Step 2: Choose Permission Sets" />
</div>

<div><h3>24. Step 1: Choose Permission Set Type</h3>
<p>A new browser tab will open, presenting <strong>Step 1: Choose Permission Set Type.</strong> Make the following selections:</p><ul><li><p>For <strong>Permission Set Type</strong>, choose <strong>“Predefined Permission Set.”</strong></p></li><li><p>For <strong>Policy for Predefined Permission Set</strong>, select “<strong>AdministratorAccess</strong>.”</p></li><li><p>Click “<strong>Next</strong>” to proceed.</p></li></ul>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/bdcc590f-4b1e-4fa0-8834-49bc19e13d38/8327dee9-c5df-45b4-9071-3c1028616d4c.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Step 1: Choose Permission Set Type" />
</div>

<div><h3>25. Step 2: Define Permission Set Details</h3>
<p>In <strong>Step 2: Define Permission Set Details</strong>, retain the default configurations and click “<strong>Next</strong>.” The default settings establish a permission set named <em>AdministratorAccess </em>with a session duration set to one hour.</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/e05a72ec-9755-4da9-bf27-06ccd5f9461b/0d9cab3c-3b54-492d-aa75-dd13495e7517.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Step 2: Define Permission Set Details" />
</div>

<div><h3>26. Step 3: Review and Create</h3>
<p>In <strong>Step 3: Review and Create</strong>, confirm that the<strong> Permission Set Type</strong> utilizes the AWS managed policy <strong>AdministratorAccess</strong>. Click on “<strong>Create</strong>.”</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/388cf58c-62c6-4db7-af85-ee9357a1bb9c/f7c941e9-70e7-464b-a93e-8cd61014900a.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Step 3: Review and Create" />
</div>

<div><h3>27. You are redirected to the Permission Sets page</h3>
<p>You are redirected to the <strong>Permission Sets</strong> page, where a notification at the top confirms the successful creation of the permission set. Click on ‘<strong>X</strong>’ to close the tab.</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/4f37171c-dd87-41ce-9110-4ba1ff5bfc7a/a1eb850a-79f0-401d-8e66-0fcd88b25dd9.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="You are redirected to the Permission Sets page" />
</div>

<div><h3>28. In the Assign Users and Groups browser tab</h3>
<p>In the <strong>Assign Users and Groups browser</strong> tab, within<strong> Step 2: Choose Permission Sets</strong>, navigate to the <strong>Permission Sets</strong> section, and click on <strong>Refresh</strong>. The AdministratorAccess permission set, which you previously created, will now be visible in the list. Select the checkbox next to that permission set and then click on <strong>Next</strong>.</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/6304688e-603b-4acb-a1d9-a1c396fe3174/bcb38ff9-e8d9-4a96-afe8-1132aa0230ba.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="In the Assign Users and Groups browser tab" />
</div>

<div><h3>29. In Step 3: Review and Submit</h3>
<p>In<strong> Step 3: Review and Submit</strong>, examine the chosen users, groups, and permission set, and then click on <strong>Submit</strong>.</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/2ecf220d-13a2-4796-9aef-8afe4a6a295c/89b65fca-4d8f-4bc6-9d68-afc063003747.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="In Step 3: Review and Submit" />
</div>

<div><h3>30. Congratulations! Your user can now log in to the AWS access portal and access resources within your AWS account.</h3>
<p>The page will refresh with a message indicating that your AWS account is undergoing configuration. Please wait until the process is complete.</p><p></p><p>Upon completion, you will be redirected to the AWS accounts page in IAM Identity Center. A notification message will confirm the successful reprovisioning of your AWS account with the updated permission set.</p><p></p><p>In the Organization Structure section, observe that your AWS account is now designated as the management account under the root of the AWS organization. Note that in this tutorial, a placeholder AWS account name, “Test-acct,” is used; you will see the name of <strong>your AWS account</strong> instead.</p><p></p><p>Congratulations! Your user can now log in to the AWS access portal and access resources within your AWS account.</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/15310f29-b8de-4ec0-a386-f0d8e3b36bb8/5f177b87-8873-44c7-8cd0-05004c8d5c99.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Congratulations! Your user can now log in to the AWS access portal and access resources within your AWS account." />
</div>

<div><h2># Log in to the AWS access portal using your administrative credentials.</h2></div>

<div><h3>31. Accept Invitation</h3>
<p>Now that you’ve set up your new administrative user, it’s time to sign in. If you attempted to sign in earlier, you would have only been able to create your password and enable multi-factor authentication (MFA) for your user, as no other permissions were granted at that time. However, your user now has full permissions to access your AWS resources. Nevertheless, they still need to configure a password and set up MFA. Let’s go through these steps.</p><p></p><p>An email for the new user has been sent to the specified email address during user creation. This email includes three crucial items:</p><ul><li><p>A link to accept the invitation to join.</p></li><li><p>The URL of your AWS access portal.</p></li><li><p>Your username for signing in.</p><p></p></li></ul><p>Open the email, note the URL of the AWS access portal and the username for future reference, and then click on the “Accept Invitation” link.</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/c3e554b9-7ac2-41ed-8077-555617204732/5a1ec3f9-644a-4b64-ba90-5905786aba35.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Accept Invitation" />
</div>

<div><h3>32. Clicking the link opens a new browser window,</h3>
<p>Clicking the link opens a new browser window, presenting the <strong>New User Sign Up page</strong>.</p><p></p><p>Enter a new password adhering to the following criteria:</p><ul><li><p>Length between 8 and 64 characters</p></li><li><p>Combination of uppercase and lowercase letters, numbers, and non-alphanumeric characters.</p></li></ul><p>Confirm the password and then click on “<strong>Set New Password.</strong>”</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/244a9709-294b-40cb-83a5-7a97a07bce25/51b925d5-985f-4b21-adf7-9453b810b2db.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Clicking the link opens a new browser window," />
</div>

<div><h3>33. The AWS console opens.</h3>
<p>Along the top bar, next to the <strong>User name</strong>, select <strong>MFA devices</strong> to set up MFA.</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/7c55a3a6-e50b-45df-9a61-e29a9f13cb46/3104a11f-8392-4b00-893c-4f54732195ac.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="The AWS console opens." />
</div>

<div><h3>34. Setup MFA</h3>
<p>Within the access portal, choose the AWS account you wish to administer. The permissions configured for your account are displayed, along with two connection options.</p><p></p><ul><li><p>Select <strong>“Management console”</strong> to access the AWS Management Console and oversee your AWS resources through the service console dashboards.</p></li><li><p>Alternatively, choose “<strong>Command line or programmatic access”</strong> to obtain credentials for programmatic access to AWS resources or usage with the AWS CLI. For detailed information on obtaining these credentials, refer to the guide on <a target="_blank" rel="noopener noreferrer nofollow" class="markup--anchor markup--li-anchor" href="https://docs.aws.amazon.com/singlesignon/latest/userguide/howtogetcredentials.html">Getting IAM Identity Center user credentials for the AWS CLI or AWS SDKs</a>.</p></li></ul><p>For the purpose of this tutorial, opt for <strong>“Management console.”</strong></p><p></p><p>Upon selecting this option, the AWS Management Console opens. As an administrative user, you can now add services, include additional users, and configure policies and permissions without the necessity of using your root user for these tasks.</p>
<img src="https://images.tango.us/workflows/a25a6de8-be26-4905-9e13-32aa6ebbb3be/steps/b8e017ee-d121-4255-86e8-528b0dca4928/422c2de9-7b30-4529-92fb-a8a2cd9abfca.png?fm=png&crop=focalpoint&fit=crop&fp-x=0.5000&fp-y=0.5000&w=1200&border=2%2CF4F2F7&border-radius=8%2C8%2C8%2C8&border-radius-inner=8%2C8%2C8%2C8&blend-align=bottom&blend-mode=normal&blend-x=0&blend-w=1200&blend64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL21hZGUtd2l0aC10YW5nby13YXRlcm1hcmstdjIucG5n&mark-x=555&mark-y=425&m64=aHR0cHM6Ly9pbWFnZXMudGFuZ28udXMvc3RhdGljL2JsYW5rLnBuZz9tYXNrPWNvcm5lcnMmYm9yZGVyPTQlMkNGRjc0NDImdz0yMDUmaD0zNyZmaXQ9Y3JvcCZjb3JuZXItcmFkaXVzPTEw" style="border-radius: 8px; border: 1px solid #F4F2F7;" width="600" alt="Setup MFA" />
</div>

<div><h2># Well done! You have successfully concluded the sign-in process</h2><p>Well done! You have successfully concluded the sign-in process, established an administrative user in IAM Identity Center, implemented enhanced security measures for both your root user and administrative user, and are now prepared to engage with AWS services and applications. Please note that when signing in with your Identity Center administrative user, use the access portal URL provided in your invitation email.</p><p><strong>Remember</strong>: Each AWS Organization possesses a distinct access portal URL. Ensure to keep a record of it along with your user sign-in details.</p>
</div>

<br/>
<hr/>
<div>
<span>Created with </span><a href="https://tango.us?utm_source=magicCopy&utm_medium=magicCopy&utm_campaign=workflow%20export%20links" target='_blank' style='color: #256EFF'>Tango.us
    </a>
</div>
