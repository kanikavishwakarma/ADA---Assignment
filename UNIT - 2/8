//Implement a divide-and-conquer algorithm for multiplying two large integers.


def karatsuba(x, y):
    # Base case: if either x or y has only one digit, return the product
    if len(str(x)) == 1 or len(str(y)) == 1:
        return x * y
    
    # Determine the maximum number of digits in x and y
    n = max(len(str(x)), len(str(y)))
    
    # Divide x and y into halves, rounded up if necessary
    m = n // 2
    
    # Split x and y into a and b (high-order digits) and c and d (low-order digits)
    a = x // 10**m
    b = x % 10**m
    c = y // 10**m
    d = y % 10**m
    
    # Compute the three products needed for the Karatsuba algorithm
    ac = karatsuba(a, c)
    bd = karatsuba(b, d)
    ad_plus_bc = karatsuba(a + b, c + d) - ac - bd
    
    # Combine the three products to get the final result
    return ac * 10**(2*m) + ad_plus_bc * 10**m + bd
