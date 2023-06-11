# nullables
public class Nullable { private final String value; 	
public Nullable(String value) { this.value = value; 	}
public String getValue() { return value; 	}
public boolean isNull() { return value == null; 	}

@Override public String toString() { return isNull() ? "null" : value; 	}

}


Nullable x = new Nullable("null olmayan değer"); 
if (!x.isNull()) {
	System.out.println(x.getValue());
}

String nullString = null; 
Nullable y = new Nullable(nullString); 
if (y.isNull()) {
System.out.println("y değişkeni null"); }



import java.util.Date; 
public class NullableDate { 
private final Date value;     
public NullableDate(Date value) { this.value = value; 	}
public Date getValue() { return value; 	}
public boolean isNull() { return value == null; 	}

@Override public String toString() { return isNull() ? "null" : value.toString(); 	}

}





public class Nullable { private final Object value;     
public Nullable(Object value) { this.value = value;     }
public Object getValue() { return value;     }
public boolean isNull() { return value == null;     }
@Override public String toString() { return isNull() ? "null" : value.toString();     }
}


Şimdi bu sınıfı farklı türler üzerinde kullanalım:



Nullable nullableString = new Nullable("abc"); Nullable nullableDate = new Nullable(new Date()); Nullable nullableInt = new Nullable(2020); Nullable nullableDouble = new Nullable(3.14); Nullable nullableBoolean = new Nullable(true);


Yukarıda görebileceğiniz gibi, Nullable sınıfını farklı türler üzerinde kullanabiliriz. Fakat hâlâ bir sorunumuz var: getValue() metodunu çağırdığımız zaman çıkan değeri dönüştürmek zorundayız:



Nullable nullableString = new Nullable("abc"); 
if (!nullableString.isNull()) {
	String value = (String) nullableString.getValue();
}


Bu önemli bir açıktır. Bu açık yüzünden farkında olmadan hataya sebebiyet verebiliriz. Örneğin, aşağıdaki kodu inceleyelim:



Nullable nullableString = new Nullable("abc"); 
if (!nullableString.isNull()) {
boolean value = (boolean) nullableString.getValue(); }
