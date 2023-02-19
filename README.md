# Backend of the zestol ATS

The Zestol ATS backend requires users to login using a username and password. Once an account is created, the user is categorized as either an `Applicant` or an `AgentUser`

### Applicant
The applicant will have several fields as shown below

  -  `user` = authenticated user
  - `first_name` = first name of the applicant
  -  `last_name` = last name of the applicant
  -  `phone_number` = phone number of the applicant
  -  `sex` = sex of the applicant
  -  `email` = email of the applicant
  -  `about` = description of the applicant
  -  `country` = the country of the applicant
  -  `city` = the city of the applicant
  -  `birth_date` = the birth date of the applicant

  -  `current_role` = if the current status of the applicant is employed, the `current_role` will show the role
  -  `availabiliy` = the availability is used when the applican is employed somewhere
  -  `avatar` = avatar of the applicant

  -  `language` = A list of all `Language`
  -  `skills` = A list of `Skill`
  -  `education` = A list of all `Education` details
  -  `work` = A list of all `Work` experience
  -  `social_media` = A list of all `SocialMedia`
  -  `reference` = A list of all `reference`

##### Skills
Each skill in the list of skills of the applicant will have the following fields
  -  `skill` = Skill name
  -  `competence` = proficiency of the skill

##### languages
Each language in the list of languages will have the following fields
   - `my_language` = language name
   - `competence` = competence of the skill

##### Educations
Each skill in the list of the Education will have the folowing fields
   - `level` = level of education
   - `degree` = degree of such education
   - `college` = name of the collage
   - `location` = location of the collage
   - `document` = List of documents if available
   - `start_date` = starting date
   - `end_date` = ending date

##### Work Experiences
Each work experience in the `Work` will have the following fields
   - `position` = Position
   - `company` = Name of the company
   - `employment` = Type of the employment opportunities
   - `description` = Description
   - `start_date` = Starting date 
   - `end_date` = Ending date
   
##### Social media
Each social media has the following fields
   - `name` = name of the media
   - `link` = link of the media


### Agents
When creating account for agents (ATS) the `AgentProfile` and `AgentUser` are created,

`AgentProfile` is the profile of the whole recruiting agents while the `AgentUser` is the profile of singe agent in the organization. When creating agents for ATS the agent who create the organization become the super admin of the organization, while the agents that will be added later will become normal users of the organizations

##### AgentUser 
The agent user has the following fields
   - `user` = authenticated user
   - `first_name` = first name of the agent
   - `last_name` = last name of the agent
   - `phone_number` = phone number of the agent
   - `role` = role of the agent
   - `email` = email of the agent
   - `avatar` = avatar of the agent

##### AgentProfile
   - `admin` = the admin of the organization
   - `users` = list of the other users of the organization
   - `name` = name of the organization
   - `location` = location
   - `phone_number` = phone number
   - `email` = email
   - `career_page_url` = career page url
   - `description` = description
   - `account_type` = type of the account
   - `logo` = logo of the organization

#### Relation between AgentProfile, AgentUser amd Applicant
`AgentUser` is the user of `AgentProfile`. the `AgentProfile` can post jobs using `JobOpening` where by applicant can apply such job, the details of application are stored in `JobApplicant`

