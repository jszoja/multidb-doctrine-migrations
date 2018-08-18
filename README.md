# multidb-doctrine-migrations
This project is based on doctrine/migrations:1.5.x, as this is the lastes version supporting PHP 5.6.

There are two goals of this project:
1. Allow you to use custom abstract migration class for all of your migrations
2. Allow it to migrate across multiple database setups

## Custom migration class
I placed the CustomMigration class to the vendors folder.
All generated migrations use classe, which extends this one.

You can pass the full class namespace  name to migrations:generate:
```
vendor/bin/doctrine-migrations migrations:generate --parent="Vendors\CustomMigration"
```

## Multiple database migrations
In my case each customer use its own database. I want to create the logic which will retrieve the list of all customer databases and apply migration to each of them.

