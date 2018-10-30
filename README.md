# sock-merchant
simple script from hacker rank

#!/bin/ruby

require 'json'
require 'stringio'

# Complete the sockMerchant function below.
def sockMerchant(n, ar)

    h = Hash.new(0)
    ar.each { |x| h[x] += 1 }
    
    countPairs = 0
    h.each do |k,v|
        countPairs += (v / 2)
    end
    
    
    countPairs
end

fptr = File.open(ENV['OUTPUT_PATH'], 'w')

n = gets.to_i

ar = gets.rstrip.split(' ').map(&:to_i)

result = sockMerchant n, ar

fptr.write result
fptr.write "\n"

fptr.close()

