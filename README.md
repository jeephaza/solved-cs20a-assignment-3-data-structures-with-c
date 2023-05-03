Download Link: https://assignmentchef.com/product/solved-cs20a-assignment-3-data-structures-with-c
<br>
<strong> </strong>If you do not explicitly define a copy constructor or assignment operator for your objects, what happens when you attempt to make copies or assign one object to another?  In what cases must you define a copy constructor and assignment operator?

<strong>Problem 2: </strong>

What are the primary advantages of inheritance, provide a small programing example with two classes illustrating each point.  <strong> </strong>

<strong>Problem 3: </strong>

Suppose Child is a class derived from the class Parent, and the class Grandchild is a class derived from the class Child. This question is concerned with the constructors and destructors for the three classes Parent, Child, and Grandchild. When a constructor for the class Grandchild is invoked, what constructors are invoked and in what order? When the destructor for the class Grandchild is invoked, what destructors are invoked and in what order?

<strong>Problem 4: </strong>

Suppose you were tasked with developing a program that incorporated the following three objects: Car, Prius, and Engine.  How would you organize these objects’ relationship with one another? Why?

<strong>Problem 5: </strong>

Why can’t we assign a base class object to a derived class variable?

<strong>Problem 6: </strong>

Suppose the base class and the derived class each have a member function with the same signature. When you have a pointer to a base class object and call a function member through the pointer, discuss what determines which function is actually called—the base class member function or the derived-class function.

<strong>Program Problems </strong>

For the following programming problems make an attempt <strong>without</strong> using your computer this can be done on scratch paper if you prefer.  After the initial attempt you may program the problems to check you work. Your final answer should be written on the assignment.

<strong>Problem 7: </strong>

This program is supposed to write 1 4 9 16 25 36 49 64 81 100 , but it probably does not. What is the problem with this program? (We’re not asking you to propose a fix to the problem.)

int* computeSquares(int&amp; n) {  int arr[10];  n = 10;

for (int k = 0; k &lt; n; k++)        arr[k] = (k + 1) * (k + 1);  return arr;

}  void f() {

int junk[100];  for (int k = 0; k &lt; 100; k++)          junk[k] = 123400000 + k;

}  int main() {  int m;

int* ptr = computeSquares(m);  f();

for (int i = 0; i &lt; m; i++)

cout &lt;&lt; ptr[i] &lt;&lt; ‘ ‘;

}

<strong>Problem 8: </strong>

Write delete statements that correctly delete the following dynamically allocated entities.

int *p1 = new int[10];

int *p2[15];        for (int i = 0; i &lt; 15; i++)

p2[i] = new int[5];        int **p3 = new int*[5];

for (int i = 0; i &lt; 5; i++)              p3[i] = new int;        int *p4 = new int;        int *temp = p4;  p4 = p1;        p1 = temp;

<strong>Problem 9: </strong>

Consider the code fragment below.  It is supposed to construct a 3×4 (3 rows 4 columns) 2d array of integers and set each value to zero.  However, as given it does not.  Add the proper dereferences (*) or references (&amp;) to make this code work properly:

int   rows,   col1,   col2,   col3;

<table width="632">

 <tbody>

  <tr>

   <td width="288">      rows   = new    int[3];</td>

   <td width="344">// Create 3 pointers to columns</td>

  </tr>

  <tr>

   <td width="288">      col1   = new    int[4];</td>

   <td width="344">// Create first row with 4 elements</td>

  </tr>

  <tr>

   <td width="288">      col2   = new    int[4];</td>

   <td width="344">// Create second row with 4 elements</td>

  </tr>

  <tr>

   <td width="288">      col3   = new    int[4];</td>

   <td width="344">// Create third row with 4 elements</td>

  </tr>

  <tr>

   <td width="288">      (  rows + 0 ) =   col1[0];</td>

   <td width="344">// Point to first row</td>

  </tr>

  <tr>

   <td width="288">      (  rows + 1 ) =   col2[0];</td>

   <td width="344">// Point to second row</td>

  </tr>

  <tr>

   <td width="288">      (  rows + 2 ) =   col3[0];</td>

   <td width="344">// Point to third row</td>

  </tr>

 </tbody>

</table>




for (int i = 0; i&lt;3; i++)         for (int j = 0; j&lt;3; j++)

(   (   rows + i) + j) = 0 // rows[i][j] = 0;

<strong>Problem 10: </strong>

For this problem, you will be asked to write some code to accomplish a particular task given the code fragment below.  Each task may depend on the tasks that came before it.  Your code must be syntactically correct. <strong> </strong>

class S { public:

S(int init) :m_num(init) {}    S() :m_num(0) {}

void set(int num) {m_num = num);}      int get() { return m_num; } private:

int num;

};




S d1, d2(4), d3(-15);       S *sp1, **sp2, ***sp3;

Set sp1 to point to d1.

Using sp2 change the value of <em>num</em> in d1 to the value of <em>num</em> in d2 (you may not use d1).

Using sp3 make sp1 point to d3 (you may not use sp1).

What does the following code output? cout&lt;&lt; **&amp;*sp3; If it is a value, state the value, if it is an address state the name of the variable to which the address belongs.

<strong>Problem 11: </strong>

Consider the following program:

<table width="660">

 <tbody>

  <tr>

   <td width="306">class A { public:A() :m_msg(“Apple”) {}        A(string msg) : m_msg(msg) {}        virtual ~A() { message(); }        void message() const {              cout &lt;&lt; m_msg &lt;&lt; endl;}private:string m_msg;};</td>

   <td width="354">class B :public A { public:B() :A(“Orange”) {}B(string msg) : A(msg), m_a(msg) {}        void message() const {               m_a.message();} private:A m_a;}; </td>

  </tr>

 </tbody>

</table>




int main() {

<ul>

 <li>*b1 = new B;</li>

 <li>*b2 = new B;     A *b3 = new B(“Apple”);      b1-&gt;message();      b2-&gt;message();  (*b3).message();      delete b1;      delete b2;      delete b3;</li>

</ul>

}

How many times will you see the word Apple in the output? ____

How about Orange? ____

Now make A’s message() virtual, i.e.,

virtual void message() const;

How many times will you see the word Apple in the output? ____

How about Orange? ____

<strong>Problem 12: </strong>

Consider the following program and generated output:

<table width="678">

 <tbody>

  <tr>

   <td width="330">class Security { public:Security(int id):m_id(id), m_badge(id % 10) {} ~Security() {   cout &lt;&lt; “Security::~Security: ”&lt;&lt; m_id &lt;&lt; endl;}// Get badge reference  Badge &amp; badge() {   cout &lt;&lt; “Security::badge: Ret ref ”&lt;&lt; endl;return m_badge;}// Get badge value  Badge  badgeV() {cout &lt;&lt; “Security::badge: Ret val ”&lt;&lt; endl;return m_badge;}private:int m_id;  Badge m_badge;};</td>

   <td width="348">class Badge { public:// ConstructorBadge(int num) :m_num(num) {   m_stuff = new int[6];for (int i = 0; i &lt; 6; i++) {           m_stuff[i] = num;}}// Destructor  ~Badge() {cout &lt;&lt; “Badge::~Badge: ” &lt;&lt; m_num&lt;&lt; endl;delete[] m_stuff;} void setNum(int num) {   m_num = num;for (int i = 0; i &lt; 6; i++) {           m_stuff[i] = num;}}void print() {   cout &lt;&lt; “Badge Num: “;for (int i = 0; i &lt; 6; i++) {           cout &lt;&lt;m_stuff[i];}cout &lt;&lt; endl;}private:int m_num;  int *m_stuff;};</td>

  </tr>

  <tr>

   <td width="330">int main() {  Security s(11);s.badge().print();  if (true) {Badge b = s.badge();   b.setNum(2);b.print(); s.badge().print();    cout &lt;&lt; “Main::Leaving if:”&lt;&lt; endl;}cout &lt;&lt; “Main::Leaving main:” &lt;&lt; endl; }</td>

   <td width="348"> Output:Security::badge: Ret refBadge Num: 111111Security::badge: Ret refBadge Num: 222222Security::badge: Ret refBadge Num: 222222  Main::Leaving if:Badge::~Badge: 2Main::Leaving main:Security::~Security: 11Badge::~Badge: 1</td>

  </tr>

 </tbody>

</table>

Question on the next page:

This program runs fine until the very end where we experience a runtime crash.  Using a debugger we discover that there is an exception when calling the destructor for Badges at the line delete[] m_stuff;.  What is causing this crash how would you improve the Badge class to prevent this from occurring?










































































