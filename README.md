# activity-auditor

A Clojure library designed to monitor a [SQS] (http://aws.amazon.com/sqs/) queue and stores all data's id, message and timestamp.

## Usage

To run, simply pass the environment name as a parameter:

install lien from here http://leiningen.org/#install

```el
$> lein run dev
```

*Setup* includes editing the config.edn file in the resources folder to set your database, amazon, and audit queue settings.  It also assumes you have a schema as followed:

```el
CREATE TABLE activity_audit
(
  id character varying NOT NULL,
  message character varying,
  "timestamp" timestamp with time zone
)
WITH (
  OIDS=FALSE
);
ALTER TABLE activity_audit
  OWNER TO your_user_here;

```

You can also configure log4j's properties in the log4j.properties file in the src/ folder.

## License

Copyright © 2014 Tyler Hoersch

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
