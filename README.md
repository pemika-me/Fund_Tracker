# FUND TRACKER
#### Video Demo:  https://youtu.be/wsC7_PsZc78
#### Description:
>A web-based application using Python, SQL, HTML and CSS for tracking the invested funds which are related to tax benefit in Thailand. However, the investor can also use this website to keep record of all investment including other type of fund in one place. The investor will be able to get a big picture how much money they have invested so far, as well as the proportion of each type of fund visualized by a donut chart. This website supports both full desktop and mobile screens by implementing CSS grid and Bootstrap v5.3


#### Background:

>There are three types of mutual fund in Thailand which can be used for tax deduction

    1. RMF (Retirement Mutual Fund)
        - Holding period        : Not less than 5 calendar years from the date of purchase
        - Redemption period     : When the investor is 55 years of age
        - Continuous investment : Required, at least once every other year
        - Eligible period       : Ongoing

    2. SSF (Super Savings Fund)
        - Holding period        : Not less than 10 calendar years from the date of purchase
        - Redemption period     : At the end of ending period
        - Continuous investment : Not required
        - Eligible period       : Investment from the year 2020 – 2024

    3. LTF (Long Term Equity Fund)
        - Holding period        : Not less than 7 calendar years from the date of purchase
        - Redemption period     : At the end of ending period
        - Continuous investment : Not required
        - Eligible period       : Investment before January 1, 2020

> Each broker (or asset management company) is providing service on their own platform. In case that the investor invests in multiple mutual funds from different broker, it is not convenient to keep checking all different platforms throughout the holding period which is quite long. Fund Tracker web-application is initiated to help facilitate Thai investor to keep track of their all-own funds as one page summary. This is especially beneficial for RMF type which required the investor to continuously invest to maintain the tax deduction benefit until retirement. (visit https://www.uobam.co.th/en/tax-benefit/rmf for more detail)


### **++++ Notice**: This project was developed with misconception of RMF rebuying.  ++++
##### **I found out while writing this document that the investor does not need to continue buying the same fund. Buying different fund on the other year does not against investment condition for tax benefit as long as it's RMF type. But this web application was developed on the understanding that the same RMF fund needs to be continuously rebought until the investor becomes 55 years old and has held that fund for at least 5 calendar years before redemption to not against the condition for tax benefit. **


#### Component Files:

1. "/static"- Folder which contain all icons, image, and CSS files which are used in this project.

    1. blue-legend.ico ![Image](https://user-images.githubusercontent.com/69309354/210038237-58183f36-05d6-4922-81b5-2665a9930c73.png) / green-legend.ico ![Image](https://user-images.githubusercontent.com/69309354/210038231-1a939967-24d4-4b8e-ad1b-3efa4b947ba3.png) / pink-legend.ico ![Image](https://user-images.githubusercontent.com/69309354/210038210-cf33d423-cc9c-4a8b-ab94-ad60d95c11f6.png) / purple-legend.ico ![Image](https://user-images.githubusercontent.com/69309354/210038221-b1a54d4f-f184-48f6-8f7a-79ccf093d25a.png)
        > For circle chart legends at the homepage. Created by favicon.io

     2.  F-goldbg.ico ![Image](https://user-images.githubusercontent.com/69309354/210038388-77f1c561-72cc-4728-a883-1c353e4567ae.png)
         > Used as the logo on the browser tab. Created on favicon.io

     3.  F-whitebg.ico ![Image](https://user-images.githubusercontent.com/69309354/210038369-e6589315-a486-4d53-99a8-dc10250e1cdc.png)
         > Used as the logo on the navigation bar. Created on favicon.io

     4.  navbar.css
         > Styles in CSS format only for the navigation bar

     5.  pink-pig.jpg
         > Used as webpage's background image

     6.  styles.css
         > Styles in CSS format for all parts of the webpage

2. "/templates"- Folder which contain HTML files which are used in this project.

    1. add-fund.html
        > A template where user input fund information. Accessible via `+ fund` button on the nav bar, or via the `+ fund` button at the top-right of the fund summary table on the home page. Then the template will be rendered at `/add-fund` route.
        >
        > ![Image](https://user-images.githubusercontent.com/69309354/210037852-e94206e1-4727-488b-a3a4-433bc7f14875.png)

     2.  confirm-delete-account.html
         > In case that user click to delete their accounts from `/profile`, password input required for delete confirmation. This template will be rendered at `/delete-account` route for the user to input password with caution that their information will not be able retrieved after account deletion completed.
         >
         > ![Image](https://user-images.githubusercontent.com/69309354/210049531-ddddc8fa-1841-4296-bd5b-28bdaa1b03b8.png)

     3.  definition.html
         > Overview of each type of mutual funds which can be used for tax deduction in Thailand. Accessible via `Introduction` button on the nav bar, then the template will be rendered at `/definition` route. The user is able to see more information by clicking at the abbreviation name `RMF` `SSF` `LTF`, and a new browser tab will be created and redirect the user to each specific fund type page.
         >
         > ![Image](https://user-images.githubusercontent.com/69309354/210049018-0189b28d-0b7e-498f-8550-83db4477fdae.png)

     4.  edit-fund.html
         > A form filled with existing data of selected fund for user to update/edit their transaction information. Accessible via a `pencil` button from the `/history` route. The user can also send a request delete the selected transaction from here by clicking the `delete` button at the bottom-left.
         >
         > ![Image](https://user-images.githubusercontent.com/69309354/210050664-2d24c126-8ce2-4600-935f-ecc405791f0b.png)

     5.  goodbye.html
         > A template which is rendered after account deletion confirmed.
         >
         > ![Image](https://user-images.githubusercontent.com/69309354/210077653-898ce2a2-1c4c-4f56-a604-0141e803c238.png)



     6. history.html
        > A template which shows the transaction list of all added funds, ordered by (1) descending transaction date (or _purchase-date_) then ascending alphabetic of the fund name. Accessible via `History` button on the nav bar, then the template will be rendered at `/history` route.
         > - **Grey highlighted** row is the fund name which was dismissed by user (dismiss option is the checkbox on the edit-fund page). This affects all rows with the same fund name on the history page, as well as the row of that specific fund in the fund summary table on the home page.
         >
         > ![Image](https://user-images.githubusercontent.com/69309354/210056800-d15f708f-0ac7-4a1b-b2f6-606cfaf4265b.png)

     7.  index.html
         > A template for main page or home. Accessible via the **logo** on the left side of the nav bar, then the template will be rendered at `/` route. This page shows the summary of funds in term of donut chart at the top part, fund summary table at the bottom. This table aggregates data from the `history` page, grouped by fund name and ordered by the condition as below:
         > - **Red highlighted-row**- determines the fund that exceeds rebuying period. The user is going to lose benefit on tax exemption for this fund and need to pay back all the tax exemption in the past.
         > - **Yellow highlighted-row**: determines the fund that needs to rebuy this year
         > - **Green highlighted-row**: determines the fund which can be redeemed based on condition of each fund type (other fund which is not in tax benefit category will never be listed in this green row.)
         > - **No highlighted-row**: no action/intention required for this fund
         > - **Grey highlighted-row**: is the fund which was dismissed by the user (since the `/edit-fund` route). The user might dismiss any fund which they do not want to pay much attention by moving it to the bottom of the summary and grey it out; e.g. the fund which already passed the holding period (green highlight) since the past few years, or free small fund distributed by the asset management company.
         > .
         > _For End-Year and Rebuy-Year which is the current year will be emphasized with red letter_
         >
         > ![Image](https://user-images.githubusercontent.com/69309354/210057979-b93c2937-2a5e-4b8a-ac10-4fd8f2589f6d.png)

     8.  layout.html
         > To contain the common HTML code using throughout the whole web application. Navigation bar and flash message are implemented here as well.
         >
         > ![Image](https://user-images.githubusercontent.com/69309354/210076258-3a70b027-f60c-4d38-97af-99b3c17f7aa1.png)

     9.  login.html
         > A template for login form. Accessible via `Login` button on the nav bar or the link at the end of sign up form, then the template will be rendered at `/login` route. When the user who visit the website without logging in will automatically be redirected to this form.
         >
         > ![Image](https://user-images.githubusercontent.com/69309354/210074076-178c2449-f5df-4e29-9cc5-df42b1c84fc2.png)

    10. profile.html
        > Displaying user's profile with a link for delete their own account request at the bottom. Accessible via `Profile` button on the nav bar, then the template will be rendered at `/profile` route.
        >
        > ![Image](https://user-images.githubusercontent.com/69309354/210047431-2e0e8bfd-dd20-4eb5-8896-72b3dc773f7e.png)

    11. signup.html
        > A template for sign up form. Accessible via `Sign up` button on the nav bar or the link at the end of login form, then the template will be rendered at `/signup` route.
        >
        > ![Image](https://user-images.githubusercontent.com/69309354/210074649-f6b40774-f897-4cad-a514-b98d548e8595.png)

3. app.py
   > Contains main python code which makes each route works.

4. helpers.py
   > Contains other python code for login support and other calculation

5. project.db
   > SQLITE database for this project. There are two tables in this schema:
   > - users - store user information
   > - funds - store all fund transaction data added by user each time
   > ![Image](https://user-images.githubusercontent.com/69309354/210080014-6fd7bb7b-74ac-46f0-9c7c-4583e440465a.png)




6. sqlcode.txt
   > Note of SQL code used for data table creation.


#### Features Overview and Design Explanation:
> Refer to my understanding (which is misconception for `RMF` type declared at the top of this document), the design is based on the inspiration to see the big picture of all funds an investor has held so far. Also aiming to remind the user to keep their investment to not against the tac benefit condition. That's why the `Home` page was designed in this way.
>
> ![Image](https://user-images.githubusercontent.com/69309354/210080992-3b993191-4da8-4ca7-bd80-b8af9f0147b7.png)
>
> In order to know which fund, how much, and when they have invested - the user needs to add information by themself as it is confidential data. `Add Fund` form was developed for this purpose.
>
> For `Introduction` page, the purpose here is used for overview the concept of all type of funds for tax benefit for a beginner. Also embed links for more detail and examples.
>
> `History` page is where the user can come to manage their added transactions. As the `Home` page is showing the aggregated data for each fund, it is not reasonable to make any change there.
> `Profile` page for this phase of development is for deleting account request. In the further development, email and birthdate should be able to edit as well. Please read _Room of Improvement_ topic below for more detail.


#### Room of Improvement:

> - Grey out multiple funds and put them at the bottom at once on the home page by using checkbox and send a command by confirmation button
>
> ![Image](https://user-images.githubusercontent.com/69309354/209996159-685e0a85-1c6e-4c76-aec2-b1a16f2f87df.png)
>
> - Notification subscription - to get an email notification when the end-year and/or rebuy-year comes for subscribed item. Planned to include toggle button beside the checkbox for grey-out option above.
>
> - Forgot password option - to get a password reset link sent to user registered email via login page
> - Ability to update an email to support forgot password option and/or email notification in the future
> - Integrate with [Thai Fund Factsheet API](https://api-portal.sec.or.th/api-details#api=5a28f6df2b3a6d1788d2025c&operation=03-%E0%B8%84%E0%B9%89%E0%B8%99%E0%B8%AB%E0%B8%B2%E0%B8%8A%E0%B8%B7%E0%B9%88%E0%B8%AD%E0%B8%81%E0%B8%AD%E0%B8%87%E0%B8%97%E0%B8%B8%E0%B8%99%E0%B8%94%E0%B9%89%E0%B8%A7%E0%B8%A2%E0%B8%8A%E0%B8%B7%E0%B9%88%E0%B8%AD%E0%B8%A2%E0%B9%88%E0%B8%AD%E0%B8%AB%E0%B8%A3%E0%B8%B7%E0%B8%AD%E0%B8%8A%E0%B8%B7%E0%B9%88%E0%B8%AD%E0%B8%81%E0%B8%AD%E0%B8%87%E0%B8%97%E0%B8%B8%E0%B8%99%E0%B8%9A%E0%B8%B2%E0%B8%87%E0%B8%AA%E0%B9%88%E0%B8%A7%E0%B8%99) for real-time fund name suggestion while typing on the `/add-fund` page.
>
> - Apply modal for forms e.g. `+ Fund `, `Edit Fund` and for any `confirmation request`.
> - Backend improvement to speed up home page composing
>
