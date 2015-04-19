# Paris.js info submission

Render forms to post new talks and sponsorship and save them on Trello.

## Install

    git clone https://github.com/parisjs/parisjs-talks-submit.git
    cd parisjs-talks-submit
    npm install

## Configuration

    cp config.json{.sample,}
    $EDITOR config.json

* host - by default https://api.trello.com
* key - the oauth app key from Trello (https://trello.com/1/appKey/generate)
* token - the oauth token from Trello (https://trello.com/1/authorize?key=THEKEY&name=ParisjsTrello&expiration=never&response_type=token&scope=read,write)
* idListTalk - the id of the Trello list to post talks
* idListSponsoring - the id of the Trello list to post sponsoring

## Usage

    node server.js

## API

### Render the form

    GET /

Returns 200.

### Post the form and save to Trello

    POST /

Parameters:

* title - The title of the talk
* abstract - a small abstract of the talk (can be some markdown)
* author - the author : Author <email>
* type - the type of the talk (long or short)

Returns 201.

### Render sponsoring form

    GET /sponsoring

### Post the form and save to Trello

    POST /sponsoring

Parameters:

* entity - The entity who offer the sponsoring
* period - when
* type - type of sponsoring as array
* contact - contact infos

Returns 201.

## Tests

    npm test

## Nodejitsu deploy

Everything is ready to deploy it on nodejitsu.

    jitsu deploy

## License

            DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
                    Version 2, December 2004

    Copyright (C) 2013 François de Metz <francois@2metz.fr>

    Everyone is permitted to copy and distribute verbatim or modified
    copies of this license document, and changing it is allowed as long
    as the name is changed.

            DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
    TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION

    0. You just DO WHAT THE FUCK YOU WANT TO.
