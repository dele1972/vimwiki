

# Step 1 – Prerequisites

sudo apt-get update

## Xvfb (X virtual framebuffer)

An in-memory display server for a UNIX-like operating system (e.g., Linux). It implements the X11 display server protocol without any display. This is helpful for CLI applications like CI service.

sudo apt-get install -y unzip xvfb libxi6 libgconf-2-4

## Java OpenJDK.

sudo apt-get install default-jdk 

# Step 2 – Install Google Chrome

## Install latest Google chrome package

sudo su
curl -sS -o - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add
echo "deb [arch=amd64]  http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list
apt-get -y update
apt-get -y install google-chrome-stable

exit

# Step 3 – Install ChromeDriver

ChromeDriver is a standalone server which implements WebDriver’s wire protocol for Chromium. The WebDriver is an open source tool for automated testing of web apps across multiple browsers.

wget https://chromedriver.storage.googleapis.com/2.41/chromedriver_linux64.zip
unzip chromedriver_linux64.zip

## configure ChromeDriver

sudo mv chromedriver /usr/bin/chromedriver
sudo chown root:root /usr/bin/chromedriver
sudo chmod +x /usr/bin/chromedriver

# Step 4 – Download Required Jar Files

The Selenium Server is required to run Remote Selenium WebDrivers.

wget https://selenium-release.storage.googleapis.com/3.13/selenium-server-standalone-3.13.0.jar

Also download the testng-6.8.7.jar file to your system.

wget http://www.java2s.com/Code/JarDownload/testng/testng-6.8.7.jar.zip
unzip testng-6.8.7.jar.zip


This is taken from the following page - interesting: you'll find further Steps with a short Java Example too!

https://tecadmin.net/setup-selenium-chromedriver-on-ubuntu/
