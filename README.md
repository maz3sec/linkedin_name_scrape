LinkedIn Name Scrape
====================
> Manual method to scrape employee names from a company's LinkedIn page to use for password spraying attacks
<br>

1) Visit People Section of Company's LinkedIn as an Authenticated LI User

    `https://www.linkedin.com/company/$COMPANY/people/`


2) Scroll to Bottom of Page to Collect Names of all Users on Webpage


3) Open a Web console in the Browser
    
    `CMD + Opt + J`     (Chrome)
    
    `CMD + Opt + K`     (Firefox)


4) Clear Console
    
    `CMD  + K`          (Chrome)
    
    `CTRL + L`          (Chrome)

5) Run Command below to Capture all the Elements that Contain Names and Save it to a Variable Named els (or elements or anything you like) 
    
    ` > let els = document.getElementsByClassName("org-people-profile-card__profile-title");Array.prototype.forEach.call(els, function(el) {console.log(el.innerText);});`

![linkedin_name_scrape_PoC](https://user-images.githubusercontent.com/52467325/166062515-594a9dfc-2a12-4e24-96ce-c024512058af.png)

6) Copy Names and Format According to Company's Email Address Naming Schema



## TLDR - web console command:

` > let els = document.getElementsByClassName("org-people-profile-card__profile-title");Array.prototype.forEach.call(els, function(el) {console.log(el.innerText);});`

### Updated - 1/10/25

` > const names = Array.from(document.querySelectorAll('.lt-line-clamp--single-line')).map(element => element.textContent.trim());
names.forEach(name => console.log(name));`

### Updated - 2/4/25

` > document.querySelectorAll('.lt-line-clamp--single-line').forEach(el => console.log(el.textContent.trim()));`
