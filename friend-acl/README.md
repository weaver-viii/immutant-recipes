# friend-acl

an immutant project to show how to integrate friend for authentication/authorization

it uses the builtin workflow interactive-form that processes a web form via POST

it also uses ring-router for routing.

## Usage

clone the project, deploy it with "lein immutant deploy"

visit http://localhost:8080/friend-acl/api/login

login with user "jane" password "user\_password" or "root" and "admin\_password"

* visit http://localhost:8080/friend-acl/api/auth to see auth details
* visit http://localhost:8080/friend-acl/api/ping to see a service anyone can access
* visit http://localhost:8080/friend-acl/api/user-only-ping to see a service that only users with the "user" role can access (for example jane)
* visit http://localhost:8080/friend-acl/api/admin-only-ping to see a service that only users with the "admin" role can access (for example root)
* visit http://localhost:8080/friend-acl/api/logout to logout

## License

Copyright © 2012 marianoguerra

Distributed under the Eclipse Public License, the same as Clojure.

## Notes

some things I discovered while making the example

* wrap-session and wrap-keyword-params are required on the app to make friend work
* wrap-authorize requires a seq of roles
