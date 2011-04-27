# Queue Classic
__0.3.1__ (beta)

Queue Classic is a queueing library for Ruby apps (Rails, Sinatra, Etc...) Queue Classic features a blocking dequeue, database maintained locks and no ridiculous dependencies.

I am using this in production applications with 100s of Heroku workers. I plan to maintain and support this library for a long time.


[wiki](https://github.com/ryandotsmith/queue_classic/wiki "wiki")

[discussion group](http://groups.google.com/group/queue_classic "discussion group")


## Installation

    $ gem install queue_classic
    psql=# CREATE TABLE queue_classic_jobs (id serial, details text, locked_at timestamp);
    psql=# CREATE INDEX queue_classic_jobs_id_idx ON queue_classic_jobs (id);
    $ rake qc:load_functions
    irb: QC.enqueue "Class.method", "arg"
    $ rake jobs:work

### Dependencies

  Postgres version 9
  Ruby. Gems: pg, json

### Upgrade from 0.2 to 0.3

    $ psql your_database
    your_database=# ALTER TABLE jobs RENAME TO queue_classic_jobs;
