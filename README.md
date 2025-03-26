# OOP_in_php-examples

## Classes and Object:
````
class Car {
    public $model;
    public function startEngine() {
        return "Engine started!";
    }
}
$tesla = new Car();
$tesla->model = "Model 3";
echo $tesla->startEngine();
````

## Encapsulation:
````
class BankAccount {
    private $balance = 0;
    public function deposit($amount) {
        $this->balance += $amount;
    }
}
````

## inheritance:
````
class Animal {
    public function eat() { return "Eating"; }
}
class Dog extends Animal {
    public function bark() { return "Woof!"; }
}
$dog = new Dog();
echo $dog->eat(); // "Eating" (inherited)
````

## Constructor/Destructor:
````
class User {
    public function __construct($name) {
        echo "Welcome, $name!";
    }
    public function __destruct() {
        echo "User logged out";
    }
}
$user = new User("Alice"); // "Welcome, Alice!"
unset($user); // "User logged out"
````

## Abstraction:
````
abstract class Vehicle {
    abstract public function startEngine();
    
    public function honk() {
        return "Honk! Honk!";
    }
}

class Car extends Vehicle {
    public function startEngine() {
        return "Car engine started";
    }
}
````

## Traits:
````
trait Sharable {
    public function share() {
        return "Sharing to social media";
    }
}
class Post {
    use Sharable;
}
$post = new Post();
echo $post->share();
````

## Static Members:
````
class MathOperations {
    public static $pi = 3.1416;
    
    public static function square($num) {
        return $num * $num;
    }
}

echo MathOperations::$pi;       // Access static property
echo MathOperations::square(5); // Call static method
````

## Polymorphism:
````
interface PaymentMethod {
    public function processPayment($amount);
}

class CreditCard implements PaymentMethod {
    public function processPayment($amount) {
        return "Processing {$amount} via Credit Card";
    }
}

class PayPal implements PaymentMethod {
    public function processPayment($amount) {
        return "Processing {$amount} via PayPal";
    }
}

function checkout(PaymentMethod $payment, $amount) {
    echo $payment->processPayment($amount);
}

checkout(new CreditCard(), 100);
checkout(new PayPal(), 200);
````
