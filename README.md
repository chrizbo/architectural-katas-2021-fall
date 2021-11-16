# Architectural Katas 2021 Fall – Architects++

1.
# Table of Contents

_**[2.](#_Toc87898082)**__ **Introduction 2** _

_**[3.](#_Toc87898083)**__ **Background 2** _

**[3.1.](#_Toc87898084)****Overall strategy 2**

**[3.2.](#_Toc87898085)****The problem 2**

**[3.3.](#_Toc87898086)****Vision 3**

**[3.4.](#_Toc87898087)****Goals 3**

**[3.5.](#_Toc87898088)****Principles 3**

**[3.6.](#_Toc87898089)****Personas 3**

**[3.7.](#_Toc87898090)****Partners 4**

[Platform partners 4](#_Toc87898091)

[Location partners 4](#_Toc87898092)

**[3.8.](#_Toc87898093)****Experiences 4**

_**[4.](#_Toc87898094)**__ **Key Architecture considerations 6** _

**[4.1.](#_Toc87898095)****Architecture Principles 6**

**[4.2.](#_Toc87898096)****General 6**

**[4.3.](#_Toc87898097)****Data Resilience 6**

**[4.4.](#_Toc87898098)****Availability 6**

**[4.5.](#_Toc87898099)****Performance 6**

**[4.6.](#_Toc87898100)****AI/ML &amp; Data Management 7**

**[4.7.](#_Toc87898101)****Workflows &amp; &quot;common feature set&quot; 7**

**[4.8.](#_Toc87898102)****Regulatory 7**

**[4.9.](#_Toc87898103)****Security Considerations 7**

**[4.10.](#_Toc87898104)****Security Design aspects (decisions) 7**

_**[5.](#_Toc87898105)**__ **Summary View of Solution Domains 10** _

**[5.1.](#_Toc87898106)****Reference Architectures for Web-site modules 11**

**[5.2.](#_Toc87898107)****Reference Architecture for &quot;Backend&quot; components 11**

**[5.3.](#_Toc87898108)****Reference Architecture for Recommendation Engine 12**

**[5.4.](#_Toc87898109)****Migration plan 13**

# 2.Introduction

We are called Architects++ since we are a group from [Cognizant](https://www.cognizant.com/) of architects aided by a product manager.

The team includes the following people:

- Udaybhaskar Seetamraju (architect)
- Rakesh Rai (architect)
- [Chris Butler](https://www.linkedin.com/in/chrisbu/) (product manager)

# 3.Background

## 3.1.Overall strategy

Turn [food deserts](https://www.aecf.org/blog/exploring-americas-food-deserts) into fresh and healthy food oases for everyone. Everyone feels like they are part of a community that helps them make the right choices for their circumstance.

## 3.2.The problem

Food deserts are an issue that effects 39.5 million people (or 12.8% of the population) in the United States.

![](RackMultipart20211116-4-n51k62_html_86f41c190b3a74e.png)

_Figure 1 Source: Low-Income and Low-Supermarket-Access Census Tracts, 2010-2015_

The top reason why there are food deserts is the overabundance of &quot;convenience food&quot; rather than healthy food. From the report:

Low-income families are more likely to live in communities populated by smaller corner stores, convenience markets and fast-food vendors with limited healthy food options.

Farmacy Food is working to solve this key problem around food deserts in many places around the US. However, they have found that due to the extremely transactional nature of their current model people are not converting to long term customers, engaging with other customers of the same community, and getting recommendations based on medical need.

## 3.3.Vision

Imagine a future where people can get heavily subsidized or free food where they go to take care of other errands. In low-income neighborhoods this could be your local health clinic, school, food bank/pantry, library, senior centers, and subsidized housing.

People can easily swipe identification or payment (including food assistance programs like SNAP and food stamps) to get access to fresh, healthy, and diet-appropriate foods when they are hungry.

Neighborhoods originally identified as in a food desert are now in food oases because of Farmacy Food&#39;s distribution.

Members of dietary communities that are underrepresented do not feel alone. They know where to go to get exactly the food they want and what is most important to live fulfilling and healthy lives.

## 3.4.Goals

From the original description of the kata, we pulled the following goals:

- Develop relationships between engaged customers and nurture those relationships.
- Convert transactional customers to engaged customers.
- Generate analytical data from medical information to demonstrate the benefits of Farmacy Foods.
- Connect, gather, analyze, and communicate.

We would add the following goals that are the reasons for community driven features:

- Empower customers to improve their diets
- Meet people where they are and where they go regularly to get other services

## 3.5.Principles

Poised as &#39;this over that&#39; since we will want to prioritize certain aspects but must always consider if we need to make a different decision.

Here are the key principles we are using to make decisions:

1. **Partnership over &quot;rolling our own&quot;** – we will try to utilize other group&#39;s work rather than making sure it is built from scratch on our own to save on resources
2. **Seamlessness over silos** – we want to preset Farmacy Foods/Family as a single entity rather than different groups
3. **Direct connections between people over intermediation by experts** – we want to prioritize the community of &quot;people like me&quot; to give advice rather than prioritizing professionals but will attempt to mix both

## 3.6.Personas

In the original kata documentation, there is a discussion of different personas that

- Low-income families
- Elderly
- First responders
- Community Service
- Dietitian, clinicians, and other medical professionals – not included in the kata personas but referenced later

## 3.7.Partners

There are two types of partners we are considering for Farmacy Family: 1) platforms for functionality and 2) locations where our customers will be.

### Platform partners

As part of the functionality (and reference to one of our principles) we will not plan on building everything from scratch. We will try to use any partner&#39;s services for platforms like discussions, event management, and more.

### Location partners

Our main customers/personas will interact with a lot of different physical locations to get services that we will use as places for our food fridges. This will include the following:

- Free and low-cost community medical clinics
- Food banks and pantries
- Senior centers and homes
- Schools
- Libraries
- Affordable housing

Location partners will have a special interface for helping people sign up if they are not able to themselves.

## 3.8.Experiences

Some of these experiences are already covered by Family Foods and will be extended by Farmacy Family:

- Get food – when people are out, they can get the right food for their needs.
- Restock food – Farmacy Food employees can restock the right food and avoid any waste.

The following new experiences will be supported by Farmacy Family:

- Join community – after purchasing food people can join the community to get further advice.
  - A sub-experience will be for location partners to sign other people if they need help.
- Get community advice – people get advice on specifics of eating that is right for their needs. This could be to a specific question or general research on a topic.
- Get recommendations – based on their usage we will update their profiles to get recommendations for content and food.
- Give community advice – people can provide advice to people with similar needs.
- Get professional advice – doctors, dietitians, and nutritionists can provide advice to people so they get the right food for their needs.
- Give professional advice – practitioners can give specific advice to individuals that they are currently treating (in accordance with HIPAA).
- Schedule events/classes – organizers can create events and classes either online or in person.
- Attend events/classes - members of the community can join scheduled events and classes.

There are multiple channels we plan on making this content available (or not available):

- Desktop web – for both community members and practitioners
- Email and SMS – notifications
- Mobile web
- Mobile apps – out of scope
- Fitness devices integration

On-boarding with Farmacy Family will take place across multiple channels:

- Farmacy Foods and Family site desktop/mobile website
- Email receipt from purchase of food – links to Farmacy Family website
- QR codes – on locations, flyers, and vending machines that redirect to sign up on the Farmacy Family website

# 4.Key Architecture considerations

## 4.1.Architecture Principles

We will be referring to the following:

[https://docs.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/architectural-principles](https://docs.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/architectural-principles)

[https://pubs.opengroup.org/architecture/togaf8-doc/arch/chap29.html](https://pubs.opengroup.org/architecture/togaf8-doc/arch/chap29.html)

Augmented by: [https://docs.aws.amazon.com/wellarchitected/latest/framework/oe-design-principles.html](https://docs.aws.amazon.com/wellarchitected/latest/framework/oe-design-principles.html)

## 4.2.General

- &quot;Support Community&quot;
  - Support physical gatherings
  - Enable virtual gatherings
  - Different clusters of customers frequently consolidate around similar dietary requirements

## 4.3.Data Resilience

- Orders and Fulfilment are already addressed in previous Kata.
- If social connection history is lost, there&#39;s potential to lose a customer not seeing the value-benefit, but an engaged customer will attempt to re-connect/re-engage
- If purchase, engagement, or preference information is lost, the recommendation-engine&#39;s recommendations will be of lower quality but not fatal.
- That said, all &quot;disks/EBS&quot; and data-stores (for Videos, PDFs) should be replicated to another zone on a quarterly basis (to avoid significant network + replication charges)

## 4.4.Availability

- Expectation that social media has top-notch availability.
- Expectation that website has top-notch availability.
- Email and Text communication can be delayed by up to a day, as no time-sensitive communications noted in requirements.
- Recommendation-engine is utilized in &quot;batch&quot; mode, and not in live-response mode.

## 4.5.Performance

- Total # of Users: 100s currently
  - Separated by distinct geographic zones
- Approximate peak traffic:
  - 100s at 6pm daily.
- Social-media and website needs to be highly responsive performance-wise.
 These two should demonstrate elasticity for any peak loads (these peak-loads should be very much predictable:- given that the human need for food has a daily-schedule, as well as traffic due to pre-communicated events/engagements)
- None of the other functionalities/capabilities require high performance nor real-time behavior

## 4.6.AI/ML &amp; Data Management

- No Data Curation needed
- No Data preparation needed
- No data-integrity requirements noted: there are no &quot;Critical&quot; relationships between the various data (whether chat, engagement history, order history, medical communications, recommendations, etc..)
- Recommendation-engine is utilized in &quot;batch&quot; mode, and not in live-response mode. AI/ML is expensive, so low-cost approaches should be chosen to implement the recommendation models and associated learning.
- No IoT data streams expected from Fridges or other sources (to feed recommendation-engine);
 Alternatively, such IoT data streams do Not contain data useful for recommendation-engine
- No current plans to offer &quot;AI-driven voice mode interactions&quot;, given our assumptions on the mobile devices used by customer base.

## 4.7.Workflows &amp; &quot;common feature set&quot;

- Any workflows would be internal (regarding tracking conversion of a transactional customer to an engaged customer)
- Medical conversations are just that (a.k.a. History), Not workflows.
- No &quot;live customer service&quot; features requirement noted (yet)

## 4.8.Regulatory

See ADR #1 titled &quot;HIPAA specific isolation&quot; for full analysis and considerations.

## 4.9.Security Considerations

- HIPAA
- Not be in the news
- Avoid sophisticated access-control mechanisms at all costs.
- # of use-cases that have access-implications / changes should be \&lt; 5 (ideally) - to ensure end-users (customers) do not make mistakes.

## 4.10.Security Design aspects (decisions)

- User experience single-handedly drives the Authentication model.
 Plain use of OpenIDConnect only, with just email-address &amp; Full name as the information revealed by OIDC Provider.
- Whether or not HIPAA compliance is implemented technically and operationally maintained, it will be a public disaster if one customer&#39;s medical and personal details are inadvertently leaked to another (or to a hacker);
 So, access controls should be based on a simple model for Roles, with 4 clean Roles – either an Engaged-Customer, a Transactional-Customer(No login), a Clinician/Dietician/Gymster.. and Finally, the internal-employee Role.
  - Internal users will have chicken-n-egg challenge: the ability to mark themselves as internal-user (a &quot;standard&quot; problem typically seen with &quot;Admin&quot; roles)
  - Manual review/approval by Internal users for onboarding someone as a Clinician/Dietician/Gym role or user.
 For initial rollout, there is no &quot;self-service&quot; UI for anyone to register themselves as Clinician/Dietician/Gymster. Too many security vulnerabilities if such a feature was to be ever implemented.
- Access Control Lists should be associated with all Medical artifacts/uploads and all Medical chats with Clinicians/Dieticians.
  - Based on previous bullet, this ACL should have following SIMPLE model:
    - Model 1: HIPAA-ACL
      - Who&#39;s the Engaged-Customer (single, and cannot be changed/updated)
      - Who&#39;s the Clinician/Dietician/Gymster (single. Can initially be NULL and cannot be changed/updated once set)
      - What are the Date time stamps, etc.. (read-only as per best practice)
    - Model 2: Engagement groups
      - An owner: Who can be anyone with any one of the 4 roles.
      - A simple list of Engaged-Customers.
      - This list can be updated by the owner only
  - ACLs are automatically created by the solution - most of the time WITHOUT the Clinician/Dietician association.
 Solution should allow Customer to initiate engagement with a Clinician/Dietician, at which point, a new ACL is created that will contain the Clinician/Dietician information.
- Requirement: Farmacy Family customers can customize how much profile information they want to allow the community to see, at a fine- grained level;
  - This will be implemented using a UI that is almost identical to what&#39;s well-known within social media.
  - If not / otherwise, we will only offer a single &quot;toggle-button&quot; -- to hide/show Medical-information (distinguishing it from non-medical profile information).
- All data flows between Farmacy Foods and Farmacy Family should be based on IP-Allowed lists only (which is expected to be uni-directional, for feeding the Recommendation-engine)
- Recommendation-Engine is most effective, if data is Not masked.
 This is being allowed, only as long as the information that is in the recommendation (a.k.a. any output of recommendation-engine) has no personal or HIPAA governed information.
  - This recommendation engine should be well hidden from any mode of access.
  - Farmacy Foods and Family is not in a position to enable connectivity like AWS Direct Connect. Based on need, AWS VPN will be considered if &quot;some kind of direct access&quot; to recommendation engine environment is needed for developers.

# 5.Summary View of Solution Domains

![](RackMultipart20211116-4-n51k62_html_1462f540230e6ebf.png)

The domains marked as &quot;Green&quot; indicating new solution-components to be developed.

Detailed view of the above, in a Hexagonal Architecture is available as an readable-attachment.

A thumbnail of the larger diagram is below.

![](RackMultipart20211116-4-n51k62_html_9087880a0a01dddc.png)

## 5.1.Reference Architectures for Web-site modules

The following reference architecture applies, whether the web-sites are custom built or a simple deployment of FOSS GitHub projects like &quot;&quot;.

![](RackMultipart20211116-4-n51k62_html_9cbc1a49d1ca93c5.png)

## 5.2.Reference Architecture for &quot;Backend&quot; components

All the DDD-defined Services are implemented per the following.

Any functionality that is internal to a DDD-Domain, no matter whether &quot;Reactive design&quot; or traditional-batch, can potentially be addressed in a single model (in diagram below) using AWS Batch.

If there are _ **Non-functional requirements** _ that require a better performant design than AWS-Batch for the &quot;Reactive-design&quot; portions of the solution, we will revisit. _Assumption_: The Farmacy user-base is not a fickle batch that is typical of fashion-oriented or attention-based solutions.

![](RackMultipart20211116-4-n51k62_html_f49c20c43749ca54.png)

## 5.3.Reference Architecture for Recommendation Engine

![](RackMultipart20211116-4-n51k62_html_daf34f406b635f35.gif)

## 5.4.Migration plan

At this point in time, there is _ **no major** _ data-set expected to be migrated into the new Farmacy-Family solution, _ **except the initial load** _ of data from Farmacy-Foods into the Recommendation-Engine&#39;s repository of Training-data.

Since the Farmacy Foods solution is retained as-is, Farmacy Family will leverage bi-directional integrations, rather than copy data over.

Any caching of the data received from Farmacy Foods into Farmacy Family, will be implemented transparently, to meet any specific NFRs. This includes Order-history and Customer order-profiles.
