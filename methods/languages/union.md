# Descriptions

Create a type that contains one of multiple types: type A = type B or Type C or Type D or ...

# Solution

Use one common memory box for all types. Common box memory size equals to the size of the largest type.

# Examples

## C union type

```C
union Data {
   int i;
   float f;
   char str[100];
};


int main( ) {
   // union occupies the maximum(sizeof(int, sizeof(float), sizeof(char[100])) = sizeof(char[100] 
   union Data data;        
  
   data.i = 10;
   data.f = 220.5;
   strcpy( data.str, "C Programming");
  
   // The last string assingment modifies the whole memory box:
   // data.i : 1917853763
   // data.f : 4122360580327794860452759994368.000000
   // data.str : C Programming

   return 0;
}
```

## Swift Associated Values

```Swift
enum Barcode {
    case upc(Int, Int, Int, Int)
    case qrCode(String)
}
    
// Initialization
var productBarcode = Barcode.upc(8, 85909, 51226, 3)
// or
var productBarcode = .qrCode("ABCDEFGHIJKLMNOP")

// Pattern matching
switch productBarcode {
  case let .upc(numberSystem, manufacturer, product, check):
    print("UPC : \(numberSystem), \(manufacturer), \(product), \(check).")
  case let .qrCode(productCode):
    print("QR code: \(productCode).")
}

```

