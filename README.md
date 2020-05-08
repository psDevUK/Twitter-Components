# Please Read
I cannot stress this enough, if you are only using the community version of Powershell UniversalDashboard please do yourself a
massive favour. Go buy a copy of the Enterprise edition of UniversalDashboard.  Not only does this help the amazing developer
of this product keep making this product even better, you also get a lot more features in the Enterprise edition. So go get your 
Enterprise copy today!

# Twitter-Components
6 different Twitter components for UniversalDashboard based on https://www.npmjs.com/package/react-twitter-widgets

# Welcome I decided to host all 6 Powershell modules in this one repository

So here you can find all the twitter components I rustled up in one evening. I saw a fellow dashboard user was creating a 
dedicated Twitter page, and I thought there is currently any dedicated twitter components for Twitter, I really like using Twitter
so thought why not build some components for UniversalDashboard that directly interact with Twitter.
  As mentioned there are 6 different mini-components for Twitter in this repository, they all do slightly different things, there 
are 4 different button components and 2 window components Timeline and Tweet. 

# Demo

```
Import-Module -Name UniversalDashboard
Import-Module -Name UniversalDashboard.UDTwitterTimeline
Import-Module -Name UniversalDashboard.UDTwitterFollow
Import-Module -Name UniversalDashboard.UDTwitterHashtag
Import-Module -Name UniversalDashboard.UDTwitterMention
Import-Module -Name UniversalDashboard.UDTwitterShare
Import-Module -Name UniversalDashboard.UDTwitterTweet
Get-UDDashboard | Stop-UDDashboard

Start-UDDashboard -Port 10005 -Dashboard (
    New-UDDashboard -Title "Powershell UniversalDashboard" -Content {
        New-UDRow -Columns {
            New-UDColumn -Size 6 -Content {
                New-UDTwitterTimeline -id 'twittertimeline' -ScreenName 'psdevuk' -UserName 'psdevuk' -Height 400 -Theme 'light'
                New-UDTwitterFollow -id 'twitterfollow' -Username 'psdevuk' -Size 'large'
                New-UDTwitterHashtag -Hashtag 'UniversalDashboard'
            }
            New-UDColumn -Size 6 -Content {
                New-UDTwitterTweet -TweetID "1257471587273576450" -Theme 'light'
                New-UDTwitterMention -Username 'psdevuk' -Size 'large'
                New-UDTwitterShare -URL "https://github.com/psDevUK/Twitter-Components" -Size 'large'
            }

        }
    }
)

```
