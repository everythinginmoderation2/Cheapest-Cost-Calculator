def ground_shipping(weight):
  flat_charge = 20.00
  twolb_or_less = weight * 1.50
  over_2 = weight * 3.00
  over_6 = weight * 4.00
  over_10 = weight * 4.75
  if weight < 2:
    return twolb_or_less + flat_charge
  elif weight > 2 and weight <= 6:
    return over_2 + flat_charge
  elif weight > 6 and weight <= 10:
    return over_6 + flat_charge
  elif weight > 10:
    return over_10 + flat_charge
      
def drone_shipping(weight):
  two_lb_or_less = weight * 4.50
  over_2 = weight * 9.00
  over_6 = weight * 12.00
  over_10 = weight * 14.25
  if weight < 2:
    return two_lb_or_less
  elif weight > 2 and weight <= 6:
    return over_2
  elif weight > 6 and weight <= 10:
    return over_6
  elif weight > 10:
    return over_10
      
premium_ground_shipping = 125.00
#print(ground_shipping(8.4))
#print(drone_shipping(1.5))

def cheapest(weight):
  if ground_shipping(weight) < drone_shipping(weight) and ground_shipping(weight) < premium_ground_shipping:
    print("Ground Shipping is the cheapest method.")
    print("It would cost " + "$" + str(ground_shipping(weight)) + " to ship a package of " + str(weight) + "lbs.")
  elif ground_shipping(weight) > drone_shipping(weight) and drone_shipping(weight) < premium_ground_shipping:
    print("Drone Shipping is the cheapest method.")
    print("It would cost " + "$" + str(drone_shipping(weight)) + " to ship a package of " + str(weight) + "lbs.")
  else:
    print("Premium Ground Shipping is the cheapest method.")
    print("It would cost " + "$" + str(premium_ground_shipping) + " to ship a package of " + str(weight) + "lbs.")

#Test code with these statements
print(cheapest(4.8))
print(cheapest(41.5))

#Results should be as follows:
#for print(cheapest(4.8))
#Ground Shipping is the cheapest method.
#It would cost $34.4 to ship a package of 4.8lbs.
#for print(cheapest(41.5))
#Premium Ground Shipping is the cheapest method.
#It would cost $125.0 to ship a package of 41.5lbs.