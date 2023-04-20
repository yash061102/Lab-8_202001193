# Lab-8_202001193

Lab Exercise:

Here is the Code For Class Boa 

```
package src;

public class Boa {
	private String name;
	private int length; // the length of the boa, in feet
	private String favoriteFood;
	public Boa (String name, int length, String favoriteFood){
	this.name = name;
	this.length = length;
	this.favoriteFood = favoriteFood;
	}
	// returns true if this boa constrictor is healthy
	public boolean isHealthy(){
	return this.favoriteFood.equals("granola bars");
	}
	// returns true if the length of this boa constrictor is
	// less than the given cage length
	public boolean fitsInCage(int cageLength){
	return this.length < cageLength;
	}

	public int lengthInInches(){
		return this.length*12;
	}
}

```

3. Creating a Junit test case for isHealthy() and fitsInCage(int)

--> This is Test case for isHealthy() function and fitsInCage(int) function.
```
package src;
import static org.junit.Assert.*;

import org.junit.Before;
import org.junit.Test;

public class Boa_test {
	
	private Boa jen;
	private Boa ken;
	

	@Test
	public void testisHealthy1() {
		jen = new Boa("Jennifer", 2, "grapes");
		assertFalse(jen.isHealthy());
		
		
	}
	@Test
	public void testisHealthy2() {
		 ken = new Boa ("Kenneth", 3, "granola bars");
		assertTrue(ken.isHealthy());
		
	}
	
	@Test
	public void testfitsInCage1() {
		ken = new Boa ("Kenneth", 3, "granola bars");
		assertTrue(ken.fitsInCage(5));
	}
	
	@Test
	public void testfitsInCage2() {
		jen = new Boa("Jennifer", 2, "grapes");
		assertFalse(jen.fitsInCage(1));
	}


}
```
4. Using @Before annotation Here i put @Before annotation before Testcode

```
package src;
import static org.junit.Assert.*;

import org.junit.Before;
import org.junit.Test;

public class Boa_test {
	
	private Boa jen;
	private Boa ken;
	public Boa mike;
	public Boa ty;
	@Before
	public void setUp() throws Exception {
	jen = new Boa("Jennifer", 2, "grapes");
	ken = new Boa ("Kenneth", 3, "granola bars");
	mike =new Boa("mike",5,"mango");
	ty=new Boa("tyson",8,"granola bars");
	}
	

	@Test
	public void testisHealthy() {
		assertTrue(ken.isHealthy());
		assertFalse(jen.isHealthy());
		assertFalse(mike.isHealthy());
		assertTrue(ty.isHealthy());
		
	}
	
	@Test
	public void testfitsInCage() {
		assertTrue(ken.fitsInCage(5));
		assertFalse(jen.fitsInCage(1));
		assertTrue(mike.fitsInCage(10));
		assertFalse(ty.fitsInCage(7));
	}


}
```
7. Add a new method to the Boa class, with this purpose and signature
```
public int lengthInInches(){
		return this.length*12;
	}
```
Test Code
```
	@Test
	public void testlengthInInches() {
		int expextedlength=36;
		int ansfromfunction=ken.lengthInInches();
		assertEquals(expextedlength,ansfromfunction);
	}
```


And Here is the Output for Each Question

So First Output for Testcase without @Before Annotation
![Using Test case](https://user-images.githubusercontent.com/112205217/233333954-0860c943-a684-4b6a-b56a-a868685c7563.PNG)


Second Output for TestCase Using @Before Annotation
![test_case using @Before](https://user-images.githubusercontent.com/112205217/233334086-68ddec9c-3524-408c-9b44-c41a5eb17330.PNG)


Third Output for lengthInInches() function
![last ex_1](https://user-images.githubusercontent.com/112205217/233334257-99cf2d5a-cf4e-4e08-a29a-0e373eced99b.PNG)






