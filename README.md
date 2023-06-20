# Cockblock (WIP)
Cockblock is a website blocking application that limits/restricts user access to certain websites. This may be used for productivity.

## Requirements
- Python 3.x
- `tldextract` library

## Installation
1. Clone repository:
   - `git clone https://github.com/luckyx314/website-blocker`
2. Install `tldextract` library:
   - `pip install tldextract`
   -  For validating url and domain names

## Usage

### Adding a website to the list
The user can add a website by adding it to the **website_list.txt** file.
Each website should be separated by a new line.
A website can be as simple as **facebook.com**, **instagram.com**, **twitter.com**, etc.
It can also be a link, such as: https://github.com/luckyx314/website-blocker


**IMPORTANT NOTE: If only a domain is provided, e.g., facebook.com, all associated subdomains and links will also be blocked. If a link is specified, however, only that link is blocked.**


### Sample reference file
An included **sample_website_list.txt** file may serve as your reference for adding a website. This is not included in the program execution, just for reference.


### Blocking, Unblocking, and Blocked Period
- **Terms:**
  - **Blocking**: To deny access to specific websites that were added on the list.
  - **Blocked Period**: Refers to the duration of when the website will be blocked or unblocked.

### Blocking
**All websites** that were included in the **website_list.txt** file will be automatically blocked **indefinetely** when the program is run, unless set otherwise.

1. **Specifying if domain inclusive/exclusive**
   - As previously stated, if only the domain name of the website is added to the list, all its subdomain and links will be blocked as well. To change this, go to the **config.ini** file, search for the website, and set `is_subdomain_inclusive = false`.
2. **Setting the Blocked Period**
   - You can also set the duration of the blocked period in the **config.ini** file like so:
   - **From Default**
      - `start_time = None`
      - `end_time = None`
   - **To Custom**
      - `start_time = 6:30 AM`
      - `end_time = "6:30 PM"`
    - The custom configuration above tells us that the website will be blocked from 6:30 in the morning and will be unblocked by 6:30 in the evening.


**IMPORTANT NOTE: `start_time` should be greater than `end_time`.**

### Unblocking
There are 2 main ways to unblock your added sites:
1. Unblock
   - Simply by removing the website from the list and rerunning the program will unblock the website. Consequently, removing everything will unblock all previously added sites.
2. Duration-based unblocking
   - Websites are automatically unblocked when the `end_time` set equals the current time.


### Knowing what websites were blocked
A **res_blocked_websites.txt** file will be automatically generated by the program for the user to know which websites were blocked and their respective blocked period and other details.

### Backup files and logcat


## License
MIT