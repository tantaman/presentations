
```ruby
# Rails
User.joins(:tags)
    .where(tags: { name: ['Brunette', 'Impolite'] } )
    .group('users.id')
    .having('count(*) = 2')
```

```php
// Laravel
$users = DB::table('users')
            ->join('contacts', 'users.id', '=', 'contacts.user_id')
            ->join('orders', 'users.id', '=', 'orders.user_id')
            ->select('users.*', 'contacts.phone', 'orders.price')
            ->get();
```
