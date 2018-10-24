# Database with Rails - Active Record - MOOCademy Project

This work was done as a project for [The Hacking Project Bootcamp](https://www.thehackingproject.org/).
The goal was to learn the basics of the Database with Rails and build an SQL database of a MOOC app with the main functionalities of a MOOC database, list of all courses, lessons etc.

## Requirements

You need at least ruby 2.5.1 (maybe under but not tested) and bundler installed on your computer.

1. First of all `git clone the repo`
2. Run `$ cd active_record_blog`
3. Run `$ bundle install`
4. Run `$ rake db:reset` which gonna clean all the cells of our database, and create brand new tables along with our `seeds.rb` file
5. To play with the database run `$ rails console`
6. To check the content of each table, run `sqlite3 db/development.sqlite3` and then run:
	* `.mode column` for better readability
	* `.headers on` to show headers cells in our tables
	* `.tables` to see the list of all tables
	* `SELECT * FROM replace_it_with_the_name_of_a_table;` this command actually shows you the table that you select (don't forget the semicolon at the end!)
	* `.width` if you want to change the width of the columns for better readability. For example, if you wand to set the width of the first column to 20px and the 2nd column to 50px, run `.width 20 50`

### This is the database schema of our app:

```ruby
ActiveRecord::Schema.define(version: 2018_10_24_165719) do

  create_table "courses", force: :cascade do |t|
    t.string "title"
    t.string "description"
    t.datetime "created_at", null: false
    t.datetime "updated_at", null: false
  end

  create_table "lessons", force: :cascade do |t|
    t.string "title"
    t.text "body"
    t.datetime "created_at", null: false
    t.datetime "updated_at", null: false
  end

end
``` 

## Contributions

This project was build with the help of:
* [Nikita Vasilev](https://github.com/nikitavasilev)
* [Arthur Mansuy](https://github.com/tutus06)
* [Nathaniel Debache](https://github.com/Natdenice)
* [Thomas Charvet](https://github.com/TomacTh)
* [Ysaline Macé](https://github.com/Ysalien)

## Contact

Problems or questions? File an issue at [GitHub](https://github.com/nikitavasilev/active_record_blog/issues).


## Database

MOOCademy est une base de données, réalisée à partir de rails, permettant d'accéder à des cours. Ces cours sont définis par un titre et une description et contiennent plusieurs leçons. Les leçons contiennent un titre et un body.
On retrouve alors deux model Course (table courses) et Lesson (table lessons). Leur index est lié sur Lesson.

##### NB
Les models se trouvent dans le sous-fichier model, dans app
Les tables se trouvent dans le fichier migrate, contenu dans db
