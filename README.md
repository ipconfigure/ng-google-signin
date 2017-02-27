ng-google-plus
==================

[![Build Status](https://api.travis-ci.org/astiusa/ng-google-signin.png)](https://api.travis-ci.org/astiusa/ng-google-signin) 
[![Dependency Status](https://david-dm.org/astiusa/ng-google-signin.png)](https://david-dm.org/astiusa/ng-google-signin) 
[![Dev Dependency Status](https://david-dm.org/astiusa/ng-google-signin/dev-status.png)](https://david-dm.org/astiusa/ng-google-signin#info=devDependencies&view=table) 

> An angular module that handles login with the Google Signin API with deferred client id injection

#### Usage

```js
var app = angular.module('app', ['google-signin']);

app.config(['GoogleSigninProvider', function(GoogleSigninProvider) {
     GoogleSigninProvider.init({});
}]);

app.controller('AuthCtrl', ['$scope', 'GoogleSignin', function ($scope, 
GoogleSignin) {

    GoogleSignin.isReady().then(function() {
        GoogleSignin.initGoogle(YOUR_CLIENT_ID);

        $scope.login = function () {
            GoogleSignin.signIn().then(function (user) {
                console.log(user);
            }, function (err) {
                console.log(err);
            });
        };
    })

}]);
```

#### Credits

- Inspiration from [angular-google-plus](https://github.com/mrzmyr/angular-google-plus)
