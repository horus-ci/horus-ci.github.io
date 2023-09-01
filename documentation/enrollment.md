---
layout: default
title : Enrolling
tagline: Joining a HORUS Virtual Organization
header : Enrolling in HORUS
group: documentation
subnavgroup: documentation
---
{% include JB/setup %}

[Placeholder - more to come]

HORUS is an addon to OSiRIS providing users with easy access to large compute resources that are backed with storage infrastructure to meet the needs of research universities in the state of Michigan.  Users of HORUS belong to virtual organizations which are called 'COU' within HORUS.  


<h3>Getting started</h3>

You can enroll at this URL:  <a href="https://comanage.osris.org/enroll">https://comanage.osris.org/enroll</a>

Your institutional identity will be used to login. The beginning screen prompts users to choose an organization, for example, the University of Michigan. 

<img style="width: 60%" src="{{IMAGE_PATH}}/documentation/enrollment/Comanage-institution-selector.png" alt="COmanage institution selection screen"/>

If this is your first time logging into HORUS from your organization you may be asked to agree to release information to us.  The information released includes email, affiliation, and full name.  This is required to login and use HORUS.  

<img style="width: 60%" src="{{IMAGE_PATH}}/documentation/enrollment/Login-information-consent.png" alt="Example of information consent"/>

Generally you'll want to just send it automatically in the future (though the choice is up to you if you prefer to be asked every time).

You'll be asked to enter some basic information about yourself.  Make sure to enter a valid email, this will be used to verify your enrollment.  You should choose your virtual organization, or "COU" on this enrollment information page.  

<img style="width: 80%" src="{{IMAGE_PATH}}/documentation/enrollment/Comanage-user-signup.png" alt="COmanage enrollment information screen"/>

After submitting the form you'll see a confirmation page.  The instructions there are similar to what is written here.  Check your email at this point and look for a message from Comanage with subject "Invitation to Join HORUS/OSiRIS" containing a link to verify your enrollment request.  

<img style="width: 80%" src="{{IMAGE_PATH}}/documentation/enrollment/confirmationEmail.png" alt="COmanage confirmation email"/>

After you have verified your email, a HORUS administrator or your virtual organization administrator will approve your enrollment.  Another email will be sent.  Once approved you can <a href="https://comanage.osris.org/registry/auth/login" target="_new">login to COmanage</a>.  Depending on how you plan to use HORUS there may be no further need for you to interact with COManage.   

When you login to COManage there will be a screen to select collaboration.  Please click on 'HORUS/OSiRIS'.

<img style="width: 70%" src="{{IMAGE_PATH}}/documentation/enrollment/Comanage-collaborations.png" alt="COmanage collaboration screen"/>

<h3>What Next?</h3>

To access your storage space on HORUS with ssh/scp/sftp you need to <a href="sshkey.html">upload an SSH key</a>. 

To access Open OnDemand please see the <a href="ondemand.html">OnDemand instructions</a>.  

<a href="/documentation">Full list of HORUS documentation</a>

<h3>Who needs to enroll</h3>

Depending on how you share data you may not need to enroll every person you collaborate with.  

For ssh/scp/sftp access:  Every user needing to login and read data must enroll and upload an ssh key.

For Globus access:  A single user can configure Globus shares accessible by Globus users or groups.  The other users do not need to enroll in OSiRIS, they only need to be able to login to Globus with CIlogon and be allowed to access your share.  Please have a look at the <a href="https://docs.globus.org/how-to/share-files/">Globus.org documentation</a> for information.
 

<h3>What is my COU?</h3>

If unsure what your COU name is please look under the 'person menu' on the upper-right of COmanage and click 'My Profile'.  Under 'Role Attributes' you can see the COU you are in.  You may be in several.  

<img style="width: 100%" src="{{IMAGE_PATH}}/documentation/Comanage-role-attr.png" alt="COmanage role attributes"/>