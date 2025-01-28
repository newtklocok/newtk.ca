This will be the documentation of pretty much all the roadblocks i ran into while making this website, and how i figured out how to fix them


First issue was figuring out how this whole github pages thing works and how i can set my custom domain to be sent over to my github page where i’ll be hosting the html (or php? still under consideration)

Had to figure out all this DNS stuff

Now what does DNS (and by extension A and CNAME) actually mean? Great question i was thinking the exact same thing wow

- They’re important components of the internet’s addressing and naming system - pretty much allows us humans to use simple web addresses like website.com instead of crazy complicated and hard to remember IP addresses to access websites
- DNS: Domain Name System; translates the address into a machine-readable IP which your device will then use to locate and connect to the server 
- An A (Address) Record is a specific type of DNS record which maps your domain name to an IPv4 address (in the format of 123.456.789.123 i believe)
- CNAME (Canonical Name) pretty much forwards from a certain address to another domain name, which will then finally lead to an actual IP address. For me, it has to go from my specific custom domain (newtk.ca) to my github (newtklocok.github.io)

Turns out that Github has specific IP’s where it hosts its Github Pages? So i have to configure my DNS settings so that my CNAME goes from my custom domain to my github one, then add the A Records, which are the IP’s at which it hosts the pages

Purely for record-keeping, here are the A-records, found at https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#dns-records-for-your-custom-domain

185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153


Btw i found most of the help for this at https://www.geeksforgeeks.org/publish-websites-on-github-pages-with-a-custom-domain/ 



Ok now apparently reconfiguring DNS can take a while to figure itself out (up to 24 hours) so right now as i try it right after changing it it says ‘this site can’t be reached’, i’ll check back tomorrow for the final verdict of whether it worked or something is up. On github, it’s saying DNS check in progress for my custom domain so i can’t enforce HTTPS yet (01/28/25)


Now I have to choose between using HTML or PHP, or if they’re compatible with each other. I don’t know much about either so…


HTML (HyperText Markup Language)
- Backbone of website, markup language used to structure content on web page
- It’s STATIC, doesn’t handle any interactivity (which i would eventually want to implement)
- Client-side, so it runs in the user’s browser
- Pros: simple to learn, compatible with all browsers, lightweight (because static files load quickly), independent (client-side)
- Now a lot of the cons were already pretty much mentioned, it's static (no ability to interact with databases), and requires JavaScript or server-side scripting for anything advanced

PHP (Hypertext Preprocessor)
- Server-side scripting language; runs on server, then sends output, usually HTML, to browser
- Generates dynamic content; based on user interaction on website or data from database
- Pros: dynamic content, integration (works well with HTML & SQL), can handle complex stuff like authentication & file uploads
- Cons: dependent on server, making local development harder, security risks if it's poorly written, slower (server-side processing introduces latency), more complex for beginners


Ok perhaps the most important thing though is that Github Pages only supports static sites, so HTML; i'm going to start off with just that and use some sort of client-side JavaScript stuff if i need to add some more complex stuff

