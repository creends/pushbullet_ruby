# PushbulletRuby

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'pushbullet_ruby'
```
## Usage

### Setup
Puts your api-key into a token.json file formatted like this:
```ruby
{"token": "your api-key here"}
```
And setup your client:
```ruby
client = PushbulletRuby::Client.new(PushbulletRuby::Token.load)
```

### List devices
```ruby
client.devices
```
### Update device informations
```ruby
client.update_device(
    id: 'device id',
    params: {
        nickname: 'device name'
    }
)
```
### List contacts
```ruby
client.contacts
```
### List subscriptions(channels)
```ruby
client.subscriptions
```
### Get recent channel pushes
```ruby
client.recent_pushes('channel tag')
```
### List pushes
```ruby
client.pushes
```
### Push
You can send following list:

- note
- link
- file
```ruby
client.push_note(
    receiver: :device,
    identifier: 'devide id',
    params: {
        title: 'Title',
        body: 'Content'
    }
)
```
### Sms
```ruby
client.sens_sms(
    user_identifier: 'user id',
    device_identifier: 'device id',
    params: {
        conversation_iden: 'phone number to send to',
        message: 'Content'
    }
)
```
## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/creends/pushbullet_ruby.


##### This gem is inspired by [washbullet](https://github.com/hrysd/washbullet)



