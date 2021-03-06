lj_rnd_photo
------------

Publishes random [Flickr](http://www.flickr.com/) photo tagged with some tag to [LiveJournal](http://www.livejournal.com/).

To run this task you need to create a **Flickr API Key** [here](http://www.flickr.com/services/apps/create/apply/).

Run
---

    git clone git@github.com:alexandrz/lj_rnd_photo.git
    cd lj_rnd_photo
    bundle install
    rake lj_rnd_photo FLICKR_API_KEY=... FLICKR_SECRET=... TAG=... LJ_LOGIN=... LJ_PASSWORD=... LJ_JOURNAL=...

Deploy on [heroku](http://www.heroku.com/)
------------------------------------------

    heroku create
    heroku config:add FLICKR_API_KEY=... FLICKR_SECRET=... TAG=... LJ_LOGIN=... LJ_PASSWORD=... LJ_JOURNAL=...
    git push heroku master

Run:

    heroku run rake lj_rnd_photo

[Scheduler](https://devcenter.heroku.com/articles/scheduler):

    heroku addons:add scheduler:standard
    heroku addons:open scheduler

Add job ``rake lj_rnd_photo``