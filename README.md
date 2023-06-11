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


Nullable nullableString = new Nullable("abc"); 
if (!nullableString.isNull()) {
	String value = (String) nullableString.getValue();
}



Nullable nullableString = new Nullable("abc"); 
if (!nullableString.isNull()) {
boolean value = (boolean) nullableString.getValue(); }

}



