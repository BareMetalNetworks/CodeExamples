(0...8).map { (65 + rand(26)).chr }.join

(0...50).map { ('a'..'z').to_a[rand(26)] }.join

o = [('a'..'z'), ('A'..'Z')].map { |i| i.to_a }.flatten
string = (0...50).map { o[rand(o.length)] }.join

34 characters and blazing fast: ('a'..'z').to_a.shuffle[0,8].join.

rand(36**length).to_s(36)

## to avoid confusion no 1 and l etc
def generate_activation_code(size = 6)
  charset = %w{ 2 3 4 6 7 9 A C D E F G H J K M N P Q R T V W X Y Z}
  (0...size).map{ charset.to_a[rand(charset.size)] }.join
end
To be secure you would also want to use SecureRandom.random_number(charset.size) instead of rand(charset.size)

require 'securerandom'
p SecureRandom.urlsafe_base64(5) #=> "UtM7aa8"
p SecureRandom.urlsafe_base64 #=> "UZLdOkzop70Ddx-IJR0ABg"
p SecureRandom.urlsafe_base64(nil, true) #=> "i0XQ-7gglIsHGV2_BNPrdQ=="