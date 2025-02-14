Project Name-> E-Auction@IITB

Git Link-> https://github.com/debtanu97/FINAL_SW_LAB_WITH_DOC
	   https://github.com/debtanu97/SW_LAB_IITB (use this if you want to host from python anywhere and read the instructions below)

Team Members:
Debtanu Pal(193050043)- Frontend and Backend
Srijon Sarkar(193050038)- Backend and Auction Microservices
Gourab Dipta Ghosh(193050037)- Testing and Documentation

###################################################

Hosting:

The Following steps must be very carefully followed to host this project in a web server : 
	1) You must have the code pushed to github/gitlab before hosting on this platform(pythonanywhere.com)	
	
	2) Create an Beginner account at pythonanywhere.com
	
	3) Open a Bash console from the 'Dashboard' of the first page after you Login
	
	4) clone the github project :
		git clone https://github.com/debtanu97/SW_LAB_IITB.git
	
	5) Create a Virtual Environment for Django :
		mkvirtualenv --python=/usr/bin/python3.6 myenv
	
	6) Install Django :
		pip install django
	
	7) Install few dependencies not provided by the virtual environment but required for our Project :
		pip3 install docutils
		pip3 install Image
	
	8) Now, move back to Dashboard and on the top right corner navigate to 'Web' and click.
	
	9) Now, on Right side, an option called 'Add a new App' will be there, navigate there :
		Chose Python 3.6 as the development language
		Chose Manual Configuration option
	
	10) Now, in the page named 'Web' scroll down and add the virtual environment name that you created in the bash console.
	
	11) open the '/var/www/gourabdipta_pythonanywhere_com_wsgi.py'(WSGI Configuration file) and follow the things :
		a) Delete everything other than the part Commented on top by ++++++++Django+++++++++++
		b) Remove the comments from all the lines having a single comment.
		c) Remove the comments from:
			import os
			import sys
		d) Set the path variable in the WSGI config file to your working directory. Here:
			path = '/home/gourabdipta/CS699-E-Auction/auctionsonline'
		e) alter the line os.environ['DJANGO_SETTINGS_MODULE'] = 'mysite.settings'
		   to os.environ['DJANGO_SETTINGS_MODULE'] = 'auctionsonline.settings'	
			
	12) Now we need to add the name of our hosted site as an allowed host in the settings.py file in 
		/home/gourabdipta/CS699-E-Auction/auctionsonline/auctionsonline
		ALLOWED_HOSTS = ['gourabdipta.pythonanywhere.com']
 	
 	13) Now, we need to add the static files in the working directory from inside /auctionsonline/website/templates/
		a) In the settings.py file add the following line :
			STATIC_ROOT = '/home/gourabdipta/CS699-E-Auction/auctionsonline/static'
		b) In the Bash console, navigate to the directory containing manage.py (/home/gourabdipta/CS699-E-Auction/auctionsonline/)
			run :
				python3 manage.py collectstatic

	14) Reflect those changes in the webapp options as well.
		In the Static Files option in the page named 'Web' in Pythonanywhere chose :
		/static/ as the URL and
		/home/gourabdipta/CS699-E-Auction/auctionsonline/static/ as the directory

	15) Click on 'Reload gourabdipta.pythonanywhere.com' button and you are good to go.

	16) Type the URL : 'gourabdipta.pythonanywhere.com/website' and you should find the webpage in running condition.

#########################################################

Motivation:

Many times we wish to sell off goods that we don't need anymore. The way to go till now included popular websites like Facebook marketplace, Olx, eBay, etc. where one posts a product and the price he/she is looking for. Buyers see the product being sold and contacts the seller and they decide on a price to go ahead with the transaction. However, there is an opportunity missed. Sellers often fail to estimate the best price he can get and buyers often miss out on a product since someone else saw the post first and went ahead with the deal.

The solution to the above problem is pretty simple yet effective- AUCTIONS. Here we present an online auction portal where sellers post a product, sets a base price and a time period for which the auction will be live and visible. Buyers will fight it out for the product, placing their bids, hoping to get the product at the best price possible.


