{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "# Project B\n",
    "\n",
    "My objective for this project is to sort a list of upcoming performances in to a dataframe. \n",
    "The data is based on Stanford's Bing Concert Hall events that feature great performers every year. "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 330,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "import requests\n",
    "from bs4 import BeautifulSoup\n",
    "import pandas as pd\n",
    "import seaborn as sns"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 293,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "url = 'https://live.stanford.edu/calendar/all/all/all/all/all'"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 294,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "page = requests.get(url)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 295,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<Response [200]>"
      ]
     },
     "execution_count": 295,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "page"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 296,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "soup = BeautifulSoup(page.text, 'html.parser')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 297,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "'Stanford Live & Bing Concert Hall Events | Stanford Live'"
      ]
     },
     "execution_count": 297,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "soup.title.text"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 298,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "'Stanford Live & Bing Concert Hall Events | Stanford Live'"
      ]
     },
     "execution_count": 298,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "soup.title.string"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 299,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<li class=\"first expanded active-trail\"><a class=\"active-trail\" href=\"/calendar\">Calendar</a></li>"
      ]
     },
     "execution_count": 299,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "soup.li"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 300,
   "metadata": {},
   "outputs": [],
   "source": [
    "soup.href"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 301,
   "metadata": {},
   "outputs": [],
   "source": [
    "event_title =soup.find_all('h2')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 302,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "date =soup.find_all('ul')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 303,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "21"
      ]
     },
     "execution_count": 303,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "len(event_title)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 304,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "36"
      ]
     },
     "execution_count": 304,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "len(date)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 305,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<h2 class=\"element-invisible\">Search form</h2>"
      ]
     },
     "execution_count": 305,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "event_title[0]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 306,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<ul class=\"menu nav\"><li class=\"first expanded active-trail\"><a class=\"active-trail\" href=\"/calendar\">Calendar</a></li>\n",
       "<li class=\"collapsed\"><a href=\"/ticket-information\">Ticket Info</a></li>\n",
       "<li class=\"collapsed\"><a href=\"/plan-your-visit\">Plan Your Visit</a></li>\n",
       "<li class=\"collapsed\"><a href=\"/content/stanford-students\" title=\"Exclusive deals, opportunities for you, and student voices\">Stanford Students</a></li>\n",
       "<li class=\"collapsed\"><a href=\"/education-engagement\">Campus &amp; Community</a></li>\n",
       "<li class=\"collapsed\"><a href=\"/give\">Give</a></li>\n",
       "<li class=\"last collapsed\"><a href=\"/blog\">Blog</a></li>\n",
       "</ul>"
      ]
     },
     "execution_count": 306,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "date[0]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 307,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "'Bill Charlap Trio'"
      ]
     },
     "execution_count": 307,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "event_title[3].text"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 308,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "'\\nFriday, Feb 9, 7:30 pm '"
      ]
     },
     "execution_count": 308,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "date[3].text"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 309,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "[<ul class=\"unstyled\">\n",
       " <li>Saturday, Feb 10, 7:30 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Sunday, Feb 11, 2:30 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Wednesday, Feb 14, 8:00 pm</li><li>Thursday, Feb 15, 8:00 pm</li><li>Friday, Feb 16, 7:00 pm</li><li>Friday, Feb 16, 9:00 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Friday, Feb 23, 7:30 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Friday, Feb 23, 9:00 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Saturday, Feb 24, 7:30 pm</li><li>Sunday, Feb 25, 2:30 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Saturday, Feb 24, 8:00 pm</li><li>Saturday, Feb 24, 10:00 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Monday, Feb 26, 6:00 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Wednesday, Feb 28, 7:30 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Wednesday, Feb 28, 8:00 pm</li> </ul>, <ul class=\"media-list\"> <li class=\"media\">\n",
       " <article about=\"/calendar/march-2018/emanuel-ax-leonidas-kavakos-and-yo-yo-ma\" class=\"node node-event node-teaser clearfix\" id=\"node-999\" typeof=\"sioc:Item foaf:Document\">\n",
       " <div class=\"row-fluid\">\n",
       " <div class=\"span4\"> <div class=\"thumbnail\">\n",
       " <a class=\"thumbnail\" href=\"/calendar/march-2018/emanuel-ax-leonidas-kavakos-and-yo-yo-ma\"><img src=\"https://live.stanford.edu/sites/default/files/events/MaAx%20Kav_Brahms_Shane%20McCauley_color_0398.jpg\"/></a> </div>\n",
       " </div>\n",
       " <div class=\"media-body span8 span8\">\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/emanuel-ax-leonidas-kavakos-and-yo-yo-ma\">Emanuel Ax, Leonidas Kavakos, and Yo-Yo Ma</a></h2>\n",
       " <ul class=\"unstyled\">\n",
       " <li>Thursday, Mar 1, 7:30 pm</li> </ul>\n",
       " <div class=\"event-actions\">\n",
       " <a class=\"btn btn-primary disabled\" href=\"/calendar/march-2018/emanuel-ax-leonidas-kavakos-and-yo-yo-ma\">Learn More</a> </div>\n",
       " </div>\n",
       " </div>\n",
       " </article> <!-- /.node --> </li>\n",
       " <li class=\"media\">\n",
       " <article about=\"/calendar/march-2018/kd-lang\" class=\"node node-event node-teaser clearfix\" id=\"node-1138\" typeof=\"sioc:Item foaf:Document\">\n",
       " <div class=\"row-fluid\">\n",
       " <div class=\"span4\"> <div class=\"thumbnail\">\n",
       " <a class=\"thumbnail\" href=\"/calendar/march-2018/kd-lang\"><img src=\"https://live.stanford.edu/sites/default/files/events/kdlang_620x437_new.jpg\"/></a> </div>\n",
       " </div>\n",
       " <div class=\"media-body span8 span8\">\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/kd-lang\">k.d. lang</a></h2>\n",
       " <h3 class=\"media-heading event-subtitle\">\n",
       " \t\t\t\tIngénue redux 25th Anniversary Tour   \t\t\t</h3>\n",
       " <ul class=\"unstyled\">\n",
       " <li>Friday, Mar 2, 7:30 pm</li> </ul>\n",
       " <div class=\"event-actions\">\n",
       " <a class=\"btn btn-primary disabled\" href=\"/calendar/march-2018/kd-lang\">Learn More</a> </div>\n",
       " </div>\n",
       " </div>\n",
       " </article> <!-- /.node --> </li>\n",
       " <li class=\"media\">\n",
       " <article about=\"/calendar/march-2018/stanford-wind-symphony-winter-concert\" class=\"node node-event node-teaser clearfix\" id=\"node-1192\" typeof=\"sioc:Item foaf:Document\">\n",
       " <div class=\"row-fluid\">\n",
       " <div class=\"span4\"> <div class=\"thumbnail\">\n",
       " <a class=\"thumbnail\" href=\"/calendar/march-2018/stanford-wind-symphony-winter-concert\"><img src=\"https://live.stanford.edu/sites/default/files/events/wind%20ensemble_0_0_0_0_1.jpeg\"/></a> </div>\n",
       " </div>\n",
       " <div class=\"media-body span8 span8\">\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/stanford-wind-symphony-winter-concert\"> Stanford Wind Symphony: Winter Concert</a></h2>\n",
       " <ul class=\"unstyled\">\n",
       " <li>Saturday, Mar 3, 7:30 pm</li> </ul>\n",
       " <div class=\"event-actions\">\n",
       " <a class=\"btn btn-primary\" href=\"/calendar/march-2018/stanford-wind-symphony-winter-concert\">Info &amp; Tickets</a><div aria-hidden=\"true\" aria-labelledby=\"myModalLabel\" class=\"modal hide fade\" id=\"externalModal2075\" role=\"dialog\" tabindex=\"-1\"><div class=\"modal-header\"><button aria-hidden=\"true\" class=\"close\" data-dismiss=\"modal\" type=\"button\">×</button><h3 id=\"myModalLabel\">This event is not ticketed by Stanford Live</h3></div><div class=\"modal-body\"><p>By clicking \"confirm\" you will be transferred to an external ticketing website where Stanford Live's ticket purchase, exchange, and donation policies will not apply. Any ticketing questions should be directed to the contact information on the following external website.</p></div><div class=\"modal-footer\"><button aria-hidden=\"true\" class=\"btn\" data-dismiss=\"modal\">Cancel</button><a class=\"btn btn-primary\" href=\"http://sto.stanfordtickets.org/single/SelectSeating.aspx?p=8142#link\" target=\"_blank\">Confirm</a></div></div> <p style=\"margin-top: 10px; color: #999;\">Presented by Stanford Department of Music</p>\n",
       " </div>\n",
       " </div>\n",
       " </div>\n",
       " </article> <!-- /.node --> </li>\n",
       " <li class=\"media\">\n",
       " <article about=\"/calendar/march-2018/ssingssing\" class=\"node node-event node-teaser clearfix\" id=\"node-1112\" typeof=\"sioc:Item foaf:Document\">\n",
       " <div class=\"row-fluid\">\n",
       " <div class=\"span4\"> <div class=\"thumbnail\">\n",
       " <a class=\"thumbnail\" href=\"/calendar/march-2018/ssingssing\"><img src=\"https://live.stanford.edu/sites/default/files/events/SsingSsing.jpeg\"/></a> </div>\n",
       " </div>\n",
       " <div class=\"media-body span8 span8\">\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/ssingssing\">SsingSsing</a></h2>\n",
       " <ul class=\"unstyled\">\n",
       " <li>Saturday, Mar 3, 8:00 pm</li> </ul>\n",
       " <div class=\"event-actions\">\n",
       " <a class=\"btn btn-primary disabled\" href=\"/calendar/march-2018/ssingssing\">Canceled</a> </div>\n",
       " </div>\n",
       " </div>\n",
       " </article> <!-- /.node --> </li>\n",
       " <li class=\"media\">\n",
       " <article about=\"/calendar/march-2018/american-sound\" class=\"node node-event node-teaser clearfix\" id=\"node-981\" typeof=\"sioc:Item foaf:Document\">\n",
       " <div class=\"row-fluid\">\n",
       " <div class=\"span4\"> <div class=\"thumbnail\">\n",
       " <a class=\"thumbnail\" href=\"/calendar/march-2018/american-sound\"><img src=\"https://live.stanford.edu/sites/default/files/events/Curtis-on-tour.jpg\"/></a> </div>\n",
       " </div>\n",
       " <div class=\"media-body span8 span8\">\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/american-sound\">The American Sound</a></h2>\n",
       " <h3 class=\"media-heading event-subtitle\">\n",
       " \t\t\t\tCurtis on Tour with a tribute to Leonard Bernstein \t\t\t</h3>\n",
       " <ul class=\"unstyled\">\n",
       " <li>Sunday, Mar 4, 4:00 pm</li> </ul>\n",
       " <div class=\"event-actions\">\n",
       " <a class=\"btn btn-primary\" href=\"/calendar/march-2018/american-sound\">Info &amp; Tickets</a> </div>\n",
       " </div>\n",
       " </div>\n",
       " </article> <!-- /.node --> </li>\n",
       " <li class=\"media\">\n",
       " <article about=\"/calendar/march-2018/philharmonia-baroque-orchestra-and-chorale\" class=\"node node-event node-teaser clearfix\" id=\"node-955\" typeof=\"sioc:Item foaf:Document\">\n",
       " <div class=\"row-fluid\">\n",
       " <div class=\"span4\"> <div class=\"thumbnail\">\n",
       " <a class=\"thumbnail\" href=\"/calendar/march-2018/philharmonia-baroque-orchestra-and-chorale\"><img src=\"https://live.stanford.edu/sites/default/files/events/PBO_0.png\"/></a> </div>\n",
       " </div>\n",
       " <div class=\"media-body span8 span8\">\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/philharmonia-baroque-orchestra-and-chorale\">Philharmonia Baroque Orchestra and Chorale</a></h2>\n",
       " <h3 class=\"media-heading event-subtitle\">\n",
       " \t\t\t\tCorelli the Godfather \t\t\t</h3>\n",
       " <ul class=\"unstyled\">\n",
       " <li>Friday, Mar 9, 7:30 pm</li> </ul>\n",
       " <div class=\"event-actions\">\n",
       " <a class=\"btn btn-primary\" href=\"/calendar/march-2018/philharmonia-baroque-orchestra-and-chorale\">Learn More</a> </div>\n",
       " </div>\n",
       " </div>\n",
       " </article> <!-- /.node --> </li>\n",
       " <li class=\"media\">\n",
       " <article about=\"/calendar/march-2018/stanford-symphony-orchestra-stanford-symphonic-chorus-stanford-university\" class=\"node node-event node-teaser clearfix\" id=\"node-1146\" typeof=\"sioc:Item foaf:Document\">\n",
       " <div class=\"row-fluid\">\n",
       " <div class=\"span4\"> <div class=\"thumbnail\">\n",
       " <a class=\"thumbnail\" href=\"/calendar/march-2018/stanford-symphony-orchestra-stanford-symphonic-chorus-stanford-university\"><img src=\"https://live.stanford.edu/sites/default/files/events/danny%20elfman%20-%20vyber-26.jpg\"/></a> </div>\n",
       " </div>\n",
       " <div class=\"media-body span8 span8\">\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/stanford-symphony-orchestra-stanford-symphonic-chorus-stanford-university\">Stanford Symphony Orchestra, Stanford Symphonic Chorus, &amp; Stanford University Singers</a></h2>\n",
       " <h3 class=\"media-heading event-subtitle\">\n",
       " \t\t\t\tDanny Elfman violin concerto, US debut \t\t\t</h3>\n",
       " <ul class=\"unstyled\">\n",
       " <li>Saturday, Mar 10, 7:30 pm</li><li>Sunday, Mar 11, 2:30 pm</li> </ul>\n",
       " <div class=\"event-actions\">\n",
       " <a class=\"btn btn-primary\" href=\"/calendar/march-2018/stanford-symphony-orchestra-stanford-symphonic-chorus-stanford-university\">Info &amp; Tickets</a> </div>\n",
       " </div>\n",
       " </div>\n",
       " </article> <!-- /.node --> </li>\n",
       " <li class=\"media\">\n",
       " <article about=\"/calendar/march-2018/machine-de-cirque\" class=\"node node-event node-teaser clearfix\" id=\"node-994\" typeof=\"sioc:Item foaf:Document\">\n",
       " <div class=\"row-fluid\">\n",
       " <div class=\"span4\"> <div class=\"thumbnail\">\n",
       " <a class=\"thumbnail\" href=\"/calendar/march-2018/machine-de-cirque\"><img src=\"https://live.stanford.edu/sites/default/files/events/MachinedeCirque.png\"/></a> </div>\n",
       " </div>\n",
       " <div class=\"media-body span8 span8\">\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/machine-de-cirque\">Machine de Cirque</a></h2>\n",
       " <ul class=\"unstyled\">\n",
       " <li>Friday, Mar 16, 7:30 pm</li><li>Saturday, Mar 17, 2:30 pm</li> </ul>\n",
       " <div class=\"event-actions\">\n",
       " <a class=\"btn btn-primary\" href=\"/calendar/march-2018/machine-de-cirque\">Info &amp; Tickets</a> </div>\n",
       " </div>\n",
       " </div>\n",
       " </article> <!-- /.node --> </li>\n",
       " </ul>, <ul class=\"unstyled\">\n",
       " <li>Thursday, Mar 1, 7:30 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Friday, Mar 2, 7:30 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Saturday, Mar 3, 7:30 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Saturday, Mar 3, 8:00 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Sunday, Mar 4, 4:00 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Friday, Mar 9, 7:30 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Saturday, Mar 10, 7:30 pm</li><li>Sunday, Mar 11, 2:30 pm</li> </ul>, <ul class=\"unstyled\">\n",
       " <li>Friday, Mar 16, 7:30 pm</li><li>Saturday, Mar 17, 2:30 pm</li> </ul>, <ul><li class=\"active first\"><a href=\"#\">1</a></li>\n",
       " <li><a href=\"/calendar/all/all/all/all/all?_ga=2.202796817.1840815671.1518198391-762372524.1408548074&amp;page=1\" title=\"Go to page 2\">2</a></li>\n",
       " <li><a href=\"/calendar/all/all/all/all/all?_ga=2.202796817.1840815671.1518198391-762372524.1408548074&amp;page=2\" title=\"Go to page 3\">3</a></li>\n",
       " <li class=\"next last\"><a href=\"/calendar/all/all/all/all/all?_ga=2.202796817.1840815671.1518198391-762372524.1408548074&amp;page=1\" title=\"Go to next page\">next ›</a></li>\n",
       " </ul>, <ul class=\"nav nav-list\"><li><a href=\"/calendar/February-2018/all/all/all/all\">February</a><li><a href=\"/calendar/March-2018/all/all/all/all\">March</a><li><a href=\"/calendar/April-2018/all/all/all/all\">April</a><li><a href=\"/calendar/May-2018/all/all/all/all\">May</a><li><a href=\"/calendar/June-2018/all/all/all/all\">June</a><li class=\"active\"><a href=\"/calendar/all/all/all/all/all\">All Events</a></li></li></li></li></li></li></ul>, <ul class=\"nav nav-list\"><li><a href=\"/calendar/all/all/5/all/all\">Bing Concert Hall</a></li><li><a href=\"/calendar/all/all/1126/all/all\">Bing Studio</a></li><li><a href=\"/calendar/all/all/34/all/all\">Frost Amphitheater</a></li><li><a href=\"/calendar/all/all/6/all/all\">Memorial Auditorium</a></li><li><a href=\"/calendar/all/all/35/all/all\">Memorial Church</a></li><li class=\"active\"><a href=\"/calendar/all/all/all/all/all\">All Venues</a></li></ul>, <ul class=\"nav nav-list\"><li class=\"\"><a href=\"/calendar/all/all/all/Cabaret/all\">Cabaret</a></li><li class=\"\"><a href=\"/calendar/all/all/all/Free Event/all\">Free Event</a></li><li class=\"\"><a href=\"/calendar/all/all/all/Stanford Live 16-17 Season/all\">Stanford Live 16-17 Season</a></li><li class=\"\"><a href=\"/calendar/all/all/all/Stanford Live 17-18 Season/all\">Stanford Live 17-18 Season</a></li><li class=\"active\"><a href=\"/calendar/all/all/all/all/all\">All Series</a></li></ul>, <ul class=\"nav nav-list\"><li class=\"\"><a href=\"/calendar/all/all/all/all/Classical\">Classical</a></li><li class=\"\"><a href=\"/calendar/all/all/all/all/Dance\">Dance</a></li><li class=\"\"><a href=\"/calendar/all/all/all/all/Discussion\">Discussion</a></li><li class=\"\"><a href=\"/calendar/all/all/all/all/Family\">Family</a></li><li class=\"\"><a href=\"/calendar/all/all/all/all/Jazz\">Jazz</a></li><li class=\"\"><a href=\"/calendar/all/all/all/all/New Music\">New Music</a></li><li class=\"\"><a href=\"/calendar/all/all/all/all/Pop\">Pop</a></li><li class=\"\"><a href=\"/calendar/all/all/all/all/Screening\">Screening</a></li><li class=\"\"><a href=\"/calendar/all/all/all/all/Spoken Word\">Spoken Word</a></li><li class=\"\"><a href=\"/calendar/all/all/all/all/Theater\">Theater</a></li><li class=\"\"><a href=\"/calendar/all/all/all/all/World\">World</a></li><li class=\"active\"><a href=\"/calendar/all/all/all/all/all\">All Genres</a></li></ul>, <ul class=\"media-list\">\n",
       " <li class=\"media\">\n",
       " <a class=\"pull-left thumbnail\" href=\"https://issuu.com/stanfordlive/docs/sl18_subbrochure_03_pages?e=26856993/47778049\">\n",
       " <img src=\"//live.stanford.edu/sites/default/files/styles/no_style/public/page-thumbs/Brochure_Teaser_r2_620x437.jpg\"/>\n",
       " </a>\n",
       " <div class=\"media-body\">\n",
       " <a href=\"https://issuu.com/stanfordlive/docs/sl18_subbrochure_03_pages?e=26856993/47778049\">2017-18 Subscription Brochure</a>\n",
       " </div>\n",
       " </li>\n",
       " </ul>, <ul class=\"media-list\">\n",
       " <li class=\"media\">\n",
       " <a class=\"pull-left thumbnail\" href=\"http://live.stanford.edu/sites/default/files/BCH_SeatMap_2017.jpeg\">\n",
       " <img src=\"//live.stanford.edu/sites/default/files/BCH_SeatMap_2017.jpeg\"/>\n",
       " </a>\n",
       " <div class=\"media-body\">\n",
       " <a href=\"http://live.stanford.edu/sites/default/files/BCH_SeatMap_2017.jpeg\">Bing Concert Hall Seating Map</a><br/><br/>\n",
       " </div>\n",
       " </li>\n",
       " </ul>, <ul class=\"nav nav-list\"><li><a href=\"//live.stanford.edu/about\">About</a></li><li><a href=\"//live.stanford.edu/contact\">Contact</a></li><li><a href=\"//live.stanford.edu/staff\">Staff</a></li><li><a href=\"//live.stanford.edu/press\">Press</a></li><li><a href=\"//live.stanford.edu/jobs-internships\">Jobs &amp; Internships</a></li></ul>, <ul class=\"nav nav-list\">\n",
       " <li><a href=\"//www.stanfordlivetickets.org/account/login.aspx?ReturnUrl=account.aspx\">Manage My Account</a></li>\n",
       " <li><a href=\"//www.stanfordlivetickets.org/cart/cart.aspx\">View Cart</a></li>\n",
       " <li><a href=\"//live.stanford.edu/content/privacy-policy\">Privacy Policy</a></li>\n",
       " </ul>, <ul class=\"nav inline\"><li><a href=\"http://arts.stanford.edu/\" target=\"_blank\">Stanford Arts</a></li><li><a href=\"http://music.stanford.edu/\" target=\"_blank\">Department of Music</a></li><li><a href=\"http://www.stanford.edu/dept/taps/\" target=\"_blank\">Theater &amp; Performance Studies</a></li></ul>, <ul class=\"nav nav-pills\">\n",
       " <li><a class=\"ficon-facebook\" href=\"http://www.facebook.com/stanfordlive\"><img alt=\"Link to Facebook\" src=\"//live.stanford.edu/sites/all/themes/stanfordlive/img/facebook-32-dark.png\"/></a></li>\n",
       " <li><a class=\"ficon-youtube\" href=\"https://www.instagram.com/stanfordlive/\"><img src=\"//live.stanford.edu/sites/all/themes/stanfordlive/img/instagram-32-dark.png\"/></a></li>\n",
       " <li><a class=\"ficon-twitter\" href=\"http://twitter.com/stanfordlive\"><img alt=\"Link to Twitter\" src=\"//live.stanford.edu/sites/all/themes/stanfordlive/img/twitter-32-dark.png\"/></a></li>\n",
       " <!--<li><a class=\"ficon-youtube\" href=\"http://www.youtube.com/user/stanfordlivelyarts\"><img src=\"//live.stanford.edu/sites/all/themes/stanfordlive/img/youtube-32-dark.png\" alt=\"Link to YouTube\"></a></li>\n",
       " <li><a class=\"ficon-twitter\" href=\"http://www.flickr.com/photos/livelyarts/\"><img src=\"//live.stanford.edu/sites/all/themes/stanfordlive/img/flickr-32-dark.png\"  alt=\"Link to Flickr\"></a></li>-->\n",
       " <!--<li><a class=\"ficon-youtube\" href=\"http://vimeo.com/stanfordlive\"><img src=\"//live.stanford.edu/sites/all/themes/stanfordlive/img/vimeo-32-dark.png\" alt=\"Link to Vimeo\"></a></li>-->\n",
       " </ul>, <ul><li><a href=\"http://www.stanford.edu\">SU Home</a></li><li><a href=\"http://visit.stanford.edu/plan/maps.html\">Maps &amp; Directions</a></li><li><a href=\"http://www.stanford.edu/search/\">Search Stanford</a></li><li><a href=\"http://www.stanford.edu/site/terms.html\">Terms of Use</a></li><li><a href=\"http://www.stanford.edu/site/copyright.html\">Copyright Complaints</a></li></ul>]"
      ]
     },
     "execution_count": 309,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "date[5:36]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 310,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "[<h2 class=\"media-heading\"><a href=\"/calendar/february-2018/darlene-love\">Darlene Love</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/february-2018/counting-sheep-guerrilla-folk-opera\">Counting Sheep: A Guerrilla Folk Opera</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/february-2018/bill-charlap-trio\">Bill Charlap Trio</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/february-2018/sundays-st-lawrence\">Sundays with the St. Lawrence</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/february-2018/fever\">The Fever</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/february-2018/tak%C3%A1cs-quartet\">Takács Quartet</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/february-2018/kweku-collins\">Kweku Collins</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/february-2018/stanford-philharmonia\">Stanford Philharmonia</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/february-2018/bumper-jacksons\">Bumper Jacksons</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/february-2018/search-american-sound-alex-ross\">The Search for the American Sound with Alex Ross</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/february-2018/%C3%A7udamani-gamelan-and-dance-bali\">Çudamani: Gamelan and Dance of Bali</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/february-2018/monchichi\">Monchichi</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/emanuel-ax-leonidas-kavakos-and-yo-yo-ma\">Emanuel Ax, Leonidas Kavakos, and Yo-Yo Ma</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/kd-lang\">k.d. lang</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/stanford-wind-symphony-winter-concert\"> Stanford Wind Symphony: Winter Concert</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/ssingssing\">SsingSsing</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/american-sound\">The American Sound</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/philharmonia-baroque-orchestra-and-chorale\">Philharmonia Baroque Orchestra and Chorale</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/stanford-symphony-orchestra-stanford-symphonic-chorus-stanford-university\">Stanford Symphony Orchestra, Stanford Symphonic Chorus, &amp; Stanford University Singers</a></h2>,\n",
       " <h2 class=\"media-heading\"><a href=\"/calendar/march-2018/machine-de-cirque\">Machine de Cirque</a></h2>]"
      ]
     },
     "execution_count": 310,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "event_title[1:21]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 325,
   "metadata": {},
   "outputs": [],
   "source": [
    "num1 = event_title[3:53]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 326,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "num2 = date[3:36]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 327,
   "metadata": {},
   "outputs": [],
   "source": [
    "event_2018 = []\n",
    "for i in event_title:\n",
    "    num1 = i.text\n",
    "    event_2018.append(num1)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 315,
   "metadata": {},
   "outputs": [],
   "source": [
    "df = pd.DataFrame(event_2018, columns=['Performer'])"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 316,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style>\n",
       "    .dataframe thead tr:only-child th {\n",
       "        text-align: right;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: left;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Performer</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>Search form</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>Darlene Love</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>Counting Sheep: A Guerrilla Folk Opera</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>Bill Charlap Trio</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>Sundays with the St. Lawrence</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5</th>\n",
       "      <td>The Fever</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>6</th>\n",
       "      <td>Takács Quartet</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>7</th>\n",
       "      <td>Kweku Collins</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>8</th>\n",
       "      <td>Stanford Philharmonia</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>9</th>\n",
       "      <td>Bumper Jacksons</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>10</th>\n",
       "      <td>The Search for the American Sound with Alex Ross</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>11</th>\n",
       "      <td>Çudamani: Gamelan and Dance of Bali</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>12</th>\n",
       "      <td>Monchichi</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>13</th>\n",
       "      <td>Emanuel Ax, Leonidas Kavakos, and Yo-Yo Ma</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>14</th>\n",
       "      <td>k.d. lang</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>15</th>\n",
       "      <td>Stanford Wind Symphony: Winter Concert</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>16</th>\n",
       "      <td>SsingSsing</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>17</th>\n",
       "      <td>The American Sound</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>18</th>\n",
       "      <td>Philharmonia Baroque Orchestra and Chorale</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>19</th>\n",
       "      <td>Stanford Symphony Orchestra, Stanford Symphoni...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>20</th>\n",
       "      <td>Machine de Cirque</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                                            Performer\n",
       "0                                         Search form\n",
       "1                                        Darlene Love\n",
       "2              Counting Sheep: A Guerrilla Folk Opera\n",
       "3                                   Bill Charlap Trio\n",
       "4                       Sundays with the St. Lawrence\n",
       "5                                           The Fever\n",
       "6                                      Takács Quartet\n",
       "7                                       Kweku Collins\n",
       "8                               Stanford Philharmonia\n",
       "9                                     Bumper Jacksons\n",
       "10   The Search for the American Sound with Alex Ross\n",
       "11                Çudamani: Gamelan and Dance of Bali\n",
       "12                                          Monchichi\n",
       "13         Emanuel Ax, Leonidas Kavakos, and Yo-Yo Ma\n",
       "14                                          k.d. lang\n",
       "15             Stanford Wind Symphony: Winter Concert\n",
       "16                                         SsingSsing\n",
       "17                                 The American Sound\n",
       "18         Philharmonia Baroque Orchestra and Chorale\n",
       "19  Stanford Symphony Orchestra, Stanford Symphoni...\n",
       "20                                  Machine de Cirque"
      ]
     },
     "execution_count": 316,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.head(21)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 338,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style>\n",
       "    .dataframe thead tr:only-child th {\n",
       "        text-align: right;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: left;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Date</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>Calendar\\nTicket Info\\nPlan Your Visit\\nStanfo...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>Cart\\neNews\\nDonate\\n</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>\\n\\n\\n \\n \\n\\n\\nDarlene Love\\n\\n\\t\\t\\t\\tFeatu...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>\\nFriday, Feb 9, 7:30 pm</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>\\nFriday, Feb 9, 8:00 pmSaturday, Feb 10, 8:00...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5</th>\n",
       "      <td>\\nSaturday, Feb 10, 7:30 pm</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>6</th>\n",
       "      <td>\\nSunday, Feb 11, 2:30 pm</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>7</th>\n",
       "      <td>\\nWednesday, Feb 14, 8:00 pmThursday, Feb 15, ...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>8</th>\n",
       "      <td>\\nFriday, Feb 23, 7:30 pm</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>9</th>\n",
       "      <td>\\nFriday, Feb 23, 9:00 pm</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>10</th>\n",
       "      <td>\\nSaturday, Feb 24, 7:30 pmSunday, Feb 25, 2:3...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>11</th>\n",
       "      <td>\\nSaturday, Feb 24, 8:00 pmSaturday, Feb 24, 1...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>12</th>\n",
       "      <td>\\nMonday, Feb 26, 6:00 pm</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>13</th>\n",
       "      <td>\\nWednesday, Feb 28, 7:30 pm</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>14</th>\n",
       "      <td>\\nWednesday, Feb 28, 8:00 pm</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>15</th>\n",
       "      <td>\\n\\n\\n \\n \\n\\n\\nEmanuel Ax, Leonidas Kavakos,...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>16</th>\n",
       "      <td>\\nThursday, Mar 1, 7:30 pm</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>17</th>\n",
       "      <td>\\nFriday, Mar 2, 7:30 pm</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>18</th>\n",
       "      <td>\\nSaturday, Mar 3, 7:30 pm</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>19</th>\n",
       "      <td>\\nSaturday, Mar 3, 8:00 pm</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                                                 Date\n",
       "0   Calendar\\nTicket Info\\nPlan Your Visit\\nStanfo...\n",
       "1                               Cart\\neNews\\nDonate\\n\n",
       "2    \\n\\n\\n \\n \\n\\n\\nDarlene Love\\n\\n\\t\\t\\t\\tFeatu...\n",
       "3                           \\nFriday, Feb 9, 7:30 pm \n",
       "4   \\nFriday, Feb 9, 8:00 pmSaturday, Feb 10, 8:00...\n",
       "5                        \\nSaturday, Feb 10, 7:30 pm \n",
       "6                          \\nSunday, Feb 11, 2:30 pm \n",
       "7   \\nWednesday, Feb 14, 8:00 pmThursday, Feb 15, ...\n",
       "8                          \\nFriday, Feb 23, 7:30 pm \n",
       "9                          \\nFriday, Feb 23, 9:00 pm \n",
       "10  \\nSaturday, Feb 24, 7:30 pmSunday, Feb 25, 2:3...\n",
       "11  \\nSaturday, Feb 24, 8:00 pmSaturday, Feb 24, 1...\n",
       "12                         \\nMonday, Feb 26, 6:00 pm \n",
       "13                      \\nWednesday, Feb 28, 7:30 pm \n",
       "14                      \\nWednesday, Feb 28, 8:00 pm \n",
       "15   \\n\\n\\n \\n \\n\\n\\nEmanuel Ax, Leonidas Kavakos,...\n",
       "16                        \\nThursday, Mar 1, 7:30 pm \n",
       "17                          \\nFriday, Mar 2, 7:30 pm \n",
       "18                        \\nSaturday, Mar 3, 7:30 pm \n",
       "19                        \\nSaturday, Mar 3, 8:00 pm "
      ]
     },
     "execution_count": 338,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "dd = pd.DataFrame(Date, columns=['Date'])\n",
    "dd.head(20)##semi failed attempt"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "---------------------"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Failed attempts"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 333,
   "metadata": {},
   "outputs": [
    {
     "ename": "AttributeError",
     "evalue": "'str' object has no attribute 'text'",
     "output_type": "error",
     "traceback": [
      "\u001b[0;31m---------------------------------------------------------------------------\u001b[0m",
      "\u001b[0;31mAttributeError\u001b[0m                            Traceback (most recent call last)",
      "\u001b[0;32m<ipython-input-333-db656e1c28d5>\u001b[0m in \u001b[0;36m<module>\u001b[0;34m()\u001b[0m\n\u001b[1;32m      1\u001b[0m \u001b[0mDate\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0;34m[\u001b[0m\u001b[0;34m]\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m      2\u001b[0m \u001b[0;32mfor\u001b[0m \u001b[0mi\u001b[0m \u001b[0;32min\u001b[0m \u001b[0mdate\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0;32m----> 3\u001b[0;31m     \u001b[0mnum1\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0mi\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mtext\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m      4\u001b[0m     \u001b[0mDate\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mappend\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0mnum1\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
      "\u001b[0;31mAttributeError\u001b[0m: 'str' object has no attribute 'text'"
     ]
    }
   ],
   "source": [
    "Date = []\n",
    "for i in date:\n",
    "    num1 = i.text\n",
    "    Date.append(num1)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 339,
   "metadata": {},
   "outputs": [
    {
     "ename": "AttributeError",
     "evalue": "'str' object has no attribute 'text'",
     "output_type": "error",
     "traceback": [
      "\u001b[0;31m---------------------------------------------------------------------------\u001b[0m",
      "\u001b[0;31mAttributeError\u001b[0m                            Traceback (most recent call last)",
      "\u001b[0;32m<ipython-input-339-ee6c7564c5cf>\u001b[0m in \u001b[0;36m<module>\u001b[0;34m()\u001b[0m\n\u001b[1;32m      4\u001b[0m     \u001b[0mevent_2018\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mappend\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0mnum1\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m      5\u001b[0m \u001b[0;32mfor\u001b[0m \u001b[0mj\u001b[0m \u001b[0;32min\u001b[0m \u001b[0mdate\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0;32m----> 6\u001b[0;31m     \u001b[0mnum2\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0mj\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mtext\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m      7\u001b[0m     \u001b[0mdate\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mappend\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0mnum2\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
      "\u001b[0;31mAttributeError\u001b[0m: 'str' object has no attribute 'text'"
     ]
    }
   ],
   "source": [
    "event_2018 = []\n",
    "for i in event_title:\n",
    "    num1 = i.text\n",
    "    event_2018.append(num1)\n",
    "for j in date:\n",
    "    num2 = j.text\n",
    "    date.append(num2)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 319,
   "metadata": {},
   "outputs": [
    {
     "ename": "ValueError",
     "evalue": "Shape of passed values is (1, 21), indices imply (2, 21)",
     "output_type": "error",
     "traceback": [
      "\u001b[0;31m---------------------------------------------------------------------------\u001b[0m",
      "\u001b[0;31mValueError\u001b[0m                                Traceback (most recent call last)",
      "\u001b[0;32m/Users/yikoli/anaconda/lib/python3.6/site-packages/pandas/core/internals.py\u001b[0m in \u001b[0;36mcreate_block_manager_from_blocks\u001b[0;34m(blocks, axes)\u001b[0m\n\u001b[1;32m   4293\u001b[0m                 blocks = [make_block(values=blocks[0],\n\u001b[0;32m-> 4294\u001b[0;31m                                      placement=slice(0, len(axes[0])))]\n\u001b[0m\u001b[1;32m   4295\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n",
      "\u001b[0;32m/Users/yikoli/anaconda/lib/python3.6/site-packages/pandas/core/internals.py\u001b[0m in \u001b[0;36mmake_block\u001b[0;34m(values, placement, klass, ndim, dtype, fastpath)\u001b[0m\n\u001b[1;32m   2718\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0;32m-> 2719\u001b[0;31m     \u001b[0;32mreturn\u001b[0m \u001b[0mklass\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0mvalues\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0mndim\u001b[0m\u001b[0;34m=\u001b[0m\u001b[0mndim\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0mfastpath\u001b[0m\u001b[0;34m=\u001b[0m\u001b[0mfastpath\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0mplacement\u001b[0m\u001b[0;34m=\u001b[0m\u001b[0mplacement\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m   2720\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n",
      "\u001b[0;32m/Users/yikoli/anaconda/lib/python3.6/site-packages/pandas/core/internals.py\u001b[0m in \u001b[0;36m__init__\u001b[0;34m(self, values, ndim, fastpath, placement, **kwargs)\u001b[0m\n\u001b[1;32m   1843\u001b[0m         super(ObjectBlock, self).__init__(values, ndim=ndim, fastpath=fastpath,\n\u001b[0;32m-> 1844\u001b[0;31m                                           placement=placement, **kwargs)\n\u001b[0m\u001b[1;32m   1845\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n",
      "\u001b[0;32m/Users/yikoli/anaconda/lib/python3.6/site-packages/pandas/core/internals.py\u001b[0m in \u001b[0;36m__init__\u001b[0;34m(self, values, placement, ndim, fastpath)\u001b[0m\n\u001b[1;32m    114\u001b[0m                              'implies %d' % (len(self.values),\n\u001b[0;32m--> 115\u001b[0;31m                                              len(self.mgr_locs)))\n\u001b[0m\u001b[1;32m    116\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n",
      "\u001b[0;31mValueError\u001b[0m: Wrong number of items passed 1, placement implies 2",
      "\nDuring handling of the above exception, another exception occurred:\n",
      "\u001b[0;31mValueError\u001b[0m                                Traceback (most recent call last)",
      "\u001b[0;32m<ipython-input-319-086e0bc8cc0c>\u001b[0m in \u001b[0;36m<module>\u001b[0;34m()\u001b[0m\n\u001b[0;32m----> 1\u001b[0;31m \u001b[0mdd\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0mpd\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mDataFrame\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0mevent_2018\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0mcolumns\u001b[0m\u001b[0;34m=\u001b[0m\u001b[0;34m[\u001b[0m\u001b[0;34m'Performes'\u001b[0m\u001b[0;34m,\u001b[0m\u001b[0;34m'date'\u001b[0m\u001b[0;34m]\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m      2\u001b[0m \u001b[0mdd\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mhead\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
      "\u001b[0;32m/Users/yikoli/anaconda/lib/python3.6/site-packages/pandas/core/frame.py\u001b[0m in \u001b[0;36m__init__\u001b[0;34m(self, data, index, columns, dtype, copy)\u001b[0m\n\u001b[1;32m    328\u001b[0m                 \u001b[0;32melse\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m    329\u001b[0m                     mgr = self._init_ndarray(data, index, columns, dtype=dtype,\n\u001b[0;32m--> 330\u001b[0;31m                                              copy=copy)\n\u001b[0m\u001b[1;32m    331\u001b[0m             \u001b[0;32melse\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m    332\u001b[0m                 \u001b[0mmgr\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0mself\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0m_init_dict\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m{\u001b[0m\u001b[0;34m}\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0mindex\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0mcolumns\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0mdtype\u001b[0m\u001b[0;34m=\u001b[0m\u001b[0mdtype\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
      "\u001b[0;32m/Users/yikoli/anaconda/lib/python3.6/site-packages/pandas/core/frame.py\u001b[0m in \u001b[0;36m_init_ndarray\u001b[0;34m(self, values, index, columns, dtype, copy)\u001b[0m\n\u001b[1;32m    481\u001b[0m             \u001b[0mvalues\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0mmaybe_infer_to_datetimelike\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0mvalues\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m    482\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0;32m--> 483\u001b[0;31m         \u001b[0;32mreturn\u001b[0m \u001b[0mcreate_block_manager_from_blocks\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m[\u001b[0m\u001b[0mvalues\u001b[0m\u001b[0;34m]\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0;34m[\u001b[0m\u001b[0mcolumns\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0mindex\u001b[0m\u001b[0;34m]\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m    484\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m    485\u001b[0m     \u001b[0;34m@\u001b[0m\u001b[0mproperty\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
      "\u001b[0;32m/Users/yikoli/anaconda/lib/python3.6/site-packages/pandas/core/internals.py\u001b[0m in \u001b[0;36mcreate_block_manager_from_blocks\u001b[0;34m(blocks, axes)\u001b[0m\n\u001b[1;32m   4301\u001b[0m         \u001b[0mblocks\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0;34m[\u001b[0m\u001b[0mgetattr\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0mb\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0;34m'values'\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0mb\u001b[0m\u001b[0;34m)\u001b[0m \u001b[0;32mfor\u001b[0m \u001b[0mb\u001b[0m \u001b[0;32min\u001b[0m \u001b[0mblocks\u001b[0m\u001b[0;34m]\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m   4302\u001b[0m         \u001b[0mtot_items\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0msum\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0mb\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mshape\u001b[0m\u001b[0;34m[\u001b[0m\u001b[0;36m0\u001b[0m\u001b[0;34m]\u001b[0m \u001b[0;32mfor\u001b[0m \u001b[0mb\u001b[0m \u001b[0;32min\u001b[0m \u001b[0mblocks\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0;32m-> 4303\u001b[0;31m         \u001b[0mconstruction_error\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0mtot_items\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0mblocks\u001b[0m\u001b[0;34m[\u001b[0m\u001b[0;36m0\u001b[0m\u001b[0;34m]\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mshape\u001b[0m\u001b[0;34m[\u001b[0m\u001b[0;36m1\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m]\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0maxes\u001b[0m\u001b[0;34m,\u001b[0m \u001b[0me\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m   4304\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m   4305\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n",
      "\u001b[0;32m/Users/yikoli/anaconda/lib/python3.6/site-packages/pandas/core/internals.py\u001b[0m in \u001b[0;36mconstruction_error\u001b[0;34m(tot_items, block_shape, axes, e)\u001b[0m\n\u001b[1;32m   4278\u001b[0m         \u001b[0;32mraise\u001b[0m \u001b[0mValueError\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m\"Empty data passed with indices specified.\"\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m   4279\u001b[0m     raise ValueError(\"Shape of passed values is {0}, indices imply {1}\".format(\n\u001b[0;32m-> 4280\u001b[0;31m         passed, implied))\n\u001b[0m\u001b[1;32m   4281\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m   4282\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n",
      "\u001b[0;31mValueError\u001b[0m: Shape of passed values is (1, 21), indices imply (2, 21)"
     ]
    }
   ],
   "source": [
    "dd = pd.DataFrame(event_2018, columns=['Performes','date'])\n",
    "dd.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.6.1"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 2
}
