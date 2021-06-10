---
attachments: [Clipboard_2021-03-23-14-03-31.png]
tags: [programming]
title: SailsJs
created: '2021-03-23T07:39:27.708Z'
modified: '2021-03-23T11:08:48.439Z'
---

# SailsJs
```bash
sails generate controller version
sails lift
```
config/blueprint.js
```js
module.exports.blueprints = {
  actions: true,
}
```

VersionController.js

```js

module.exports = {
  currentVersion: function (req, res) {
    return res.json({
      version: "1.0.0",
    });
  },
};

```
http://localhost:1337/version/currentVersion


### static
```bash
npm install sails-generate-static -save
sails generate static
```

what happened now? 
we replaced defautl config/routes.js from view to static and assets folder created


### blueprint api

```bash
sails generate api texture
```

![](@attachment/Clipboard_2021-03-23-14-03-31.png)


```bash
http://localhost:1337/texture/find
http://localhost:1337/texture/create?name=print1&title=printtest1
http://localhost:1337/texture/find
http://localhost:1337/texture/2
http://localhost:1337/texture/find/2
http://localhost:1337/texture/find?createdAt=1616488807754
http://localhost:1337/texture/update/1?name=changedname
http://localhost:1337/texture/destroy/1
```

config/bootrap.js

```js
module.exports.bootstrap = function (cb) {
  console.log("hello");
  return cb();
};




module.exports.bootstrap =  function() {
  // Set up fake development data (or if we already have some, avast)
  if (await User.count() > 0) {
    return;
  }
  
  await User.createEach([
    { emailAddress: 'ry@example.com', fullName: 'Ryan Dahl', },
    { emailAddress: 'rachael@example.com', fullName: 'Rachael Shaw', },
  ]);
};

```

models.js

```js
module.exports.models = {
  schema: true,
   migrate: 'alter',

}
```

```bash
npm install sails-mongo
```
datastores.js
```js
module.exports.datastores = {
  default: {
    adapter: require('sails-mysql'),
    url: 'mysql://root@localhost:3306/dev',
  },
  existingEcommerceDb: {
    adapter: require('sails-mysql'),
    url: 'mysql://djbluegrass:0ldy3ll3r@legacy.example.com:3306/store',
  },
  q3PromoDb: {
    adapter: require('sails-mongo'),
    url: 'mongodb://djbluegrass:0ldy3ll3r@seasonal-pet-sweaters-promo.example.com:27017/promotional',
  }
};

```

```js

module.exports = {
  attributes: {
    name: {
      type: "string",
      unique: "true",
    },
    description: {
      type: "string",
    },
    path: {
      type: "string",
    },
    enabled: {
      type: "boolean",
      defaultsTo: true,
    },
  },
};

```

http://localhost:1337/texture/create?name=print1&description=printtest1



#### custom action

```js
signup: function(req, res) {
 if (_.isUndefined(req.param('email'))) {
 return res.badRequest('An email address is required!');
 }
 if (_.isUndefined(req.param('password'))) {
 return res.badRequest('A password is required!');
 }
 if (req.param('password').length < 6) {
 return res.badRequest('Password must be at least 6 characters!');
 }
 if (_.isUndefined(req.param('username'))) {
 return res.badRequest('A username is required!');
 }
 if (req.param('username').length < 6) {
 return res.badRequest('Username must be at least 6 characters!');
 }
 if (!_.isString(req.param('username')) ||
req.param('username').match(/[^a-z0-9]/i)) {
 return res.badRequest('Invalid username: must consist of numbers and
letters only.');
 }
 var options = {
 email: req.param('email'),
 username: req.param('username'),
 password: req.param('password')
 };
 return res.json(options);
 }
 }
```


```
pm2 start app.js -x -- --prod
NODE_ENV=production pm2 start app.js

```
