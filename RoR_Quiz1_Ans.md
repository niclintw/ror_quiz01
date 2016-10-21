### 1. 請說明 Fixnum (整數) 和 Float (浮點數) 之間的差異
###    Answer:
    (1)Fixnum是沒有小數點形式的整數數值，例如: 2, 1, 0, -1, -2 ......，可以有正負整數。
    (2)Float是具有小數點形式的小數數值，例如: 3.14, 0.2, -1.3 ......，也可以有正負數。
    (3)在運算式中，如果所有運算元都是Fixnum(整數)型態，則運算結果傳回值為Fixnum(整數)型態，如果運算式中有一個運算元是Float(浮點數)型態，則傳回值即為Float(浮點數)型態。

### 2. 今天有兩個字串：
  ```ruby 
  str1 = "Hallo Welt!" 
  str2 = " NTU Rails 261!"
  ```
###    請說明以下兩個印出字串的方式的不同處：
  ```ruby
  puts str1 + str2
  puts "#{str1}#{str2}"
  ```
###    Answer:
    (1)兩個方式的輸出結果相同，都是:
	   Hallo Welt! NTU Rails 261!
	(2)第一個方式是將兩個字串經過 + 這個運算元的運算，以函式堆疊及儲存字串的記憶體內容搬移的結果。
	(3)第二個方式是經過字串變數轉換的方式，直接輸出成一個字串，是透過編譯器轉換所的結果。
  
### 3. 請解釋 array 和 hash 的不同處
###    Answer:
    (1)array(陣列)及hash(雜湊)都是一種由多項物件及合組成的資料結構。
	(2)array(陣列)的內容可以是不同型態的物件，包括整數、浮點數、字串、物件、陣列、Hash等，必須用從0開始的整數索引(index)來存取對應的物件。
	(2)hash(雜湊)則必須用key(鍵)來存取其對應的物件,Key可以是不同的物件，
	   通常是用Symbol(符號)、String(字串)或Fixnum(整數)當作key。

### 4. 請用一行程式碼從 [1, "a string", 3.14, [1,2,3,4]] 這個陣列找出所有非字串的值
###   Answer:
   ```ruby
   arr.reject { |x| x.is_a?(string) }
   ```

### 5. 請用一行程式碼把一個內容為整數 1 到 100 的陣列裡所有的值加上 2
###   Answer:
   ```ruby
   arr.map! { |x| x += 2 }
   ```

### 6. 請寫出以下兩行程式碼迴傳的值，並解釋他們呼叫的方法差別為何：
  ```ruby
  [1, 2, 3, 3].uniq
  [1, 2, 3, 3].uniq!
  ```
###    Answer:
    (1)兩個式子都會傳回 => [1, 2, 3]的陣列
	   因為uniq會將陣列裡重複的項目移除，回傳沒有重複項目的陣列資料。
	(2)兩個式子的差別在於：
	   uniq是將執行的結果輸出為一個新陣列，並不會異動原陣列；
	   uniq!則是直接異動原本的陣列，不會額外產生新的陣列。

### 7. 請列出兩種產出亂數的方法
###   Answer:
    (1)利用shuffle.first從陣列[1, 2, 3]中隨機取樣
  ```ruby
  array = [1, 2, 3]
  puts array.shufflr.first
  ```

    (2)利用sample從陣列[1, 2, 3]中隨機取樣
  ```ruby
  array = [1, 2, 3]
  puts array.sample
  ```

### 8. 以下這段程式碼：
  ```ruby
  ((1 > 3)&&(true == true))||(!!!false)
  ```
###  會執行出什麼結果？ 請試試不用 irb 算出結果
###   Answer：
    (1)會回傳true。
	(2)先看||的左側，((1 > 3) && (true == true))，等於( false && true)，會得出(false)，
       再看||的右側，(!!!false)，等於(!!true)，等於(!false)，等於(true)，
       所以(false)||(true)，結果為(true)。

### 9. 請問 binding.pry 是什麼？ 要如何使用它？
###   Answer:
    (1) pry是一個協助程式中斷除錯的工具套件，必須先用gem install來安裝，才能在程式中使用。
	(2) 使用時，在程式開始處先用require 'pry'，把它引用進來，然後在程式要執行中斷偵錯處，的下一行插入binding.pry這行程式碼，當程式執行到此處時會中斷，即可檢查相關變數值，以進行除錯。
 
### 10. 下面的一段程式碼，請嘗試用其他方法把 if...else...end 簡化成一行
  ```ruby
  var = 5
  if var >= 5
  	return "var is greater than or equal to 5"
  else
  	return "var is less than 5"
  end
  ```
###   Answer:
    可簡化為:
  ```ruby
  var = 5
  return var >= 5 ? "var is greater than or equal to 5" : "var is less than 5"
  ```

### 11. 請列出兩種不同的 hash 寫法
###   Answer:
    (1)第一種寫法:
  ```ruby
  person = { 
   :name => "Bob", 
   :age => 30,
   :occupation => "Engineer"
   }
  ```

    (2)第二種寫法:
  ```ruby
  person = { 
   name: "Bob", 
   age: 30,
   occupation: "Engineer"
   }
  ```