# DB設計

## user
   - nickname
   - password
   - email

has_many: products

admin_user

## category
   - name 

has_many: products

## product
   - name
   - description
   - status
   - category_id
   - user_id
   - price

belongs_to: user
belongs_to:category
has_one: price
has_many: shipment
has_many: price

## price
   - total
   - tax
   - shipment_total

belongs_to: product

## shipment 
   
has_many: products
has_many: destination_addresses
has_many: shipping_methods

## destination_address
   
has_many: user_addresses

## shippng_method
   - compamy_name
     - sagsawa
     - yamato 
     - japan
   - shipping_way
     - 宅急便
     - 飛脚宅急便
     - ゆうパック


## user_address
   - post_number
   - prefecture
   - city
   - detail 

belongs_to:user

## cart

has_many: orders
has_many: users
has_many: shipments

## order

has_many: products
has_many: settlements
has_many: shipping_methods
belomngs_to: user


## settlement  pay.jp
   - amount
   - card
   - currency


order → pay.jp  → 
      
  与信　　仮決済　　本決済    


決済トークン

https://qiita.com/Sa2Knight/items/baefe2a49cefc9f03af6

