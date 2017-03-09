---
title: "Gewusst wie: Identifizieren eines Typs, der NULL-Werte zul&#228;sst (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Typen, die NULL-Werte zulassen [C#], Identifizieren"
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
caps.latest.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 7
---
# Gewusst wie: Identifizieren eines Typs, der NULL-Werte zul&#228;sst (C#-Programmierhandbuch)
Sie können den Operator [typeof](../../../csharp/language-reference/keywords/typeof.md) von C\# verwenden, um ein <xref:System.Type>\-Objekt zu erstellen, das einen Typ darstellt, der NULL\-Werte zulässt:  
  
```  
System.Type type = typeof(int?);  
```  
  
 Darüber hinaus können Sie die Klassen und Methoden des <xref:System.Reflection>\-Namespaces verwenden, um <xref:System.Type>\-Objekte zu generieren, die Typen darstellen, die NULL\-Werte zulassen.  Wenn Sie jedoch versuchen, zur Laufzeit mit der <xref:System.Object.GetType%2A>\-Methode oder dem Operator `is` Typinformation von Variablen abzurufen, die NULL\-Werte zulassen, wird ein <xref:System.Type>\-Objekt generiert, das den zugrunde liegenden Typ darstellt und nicht den Typ, der NULL\-Werte zulässt.  
  
 Das Aufrufen von `GetType` für einen Typ, der NULL\-Werte zulässt, resultiert in einem Boxingvorgang, wenn der Typ implizit in <xref:System.Object> konvertiert wird.  Daher gibt <xref:System.Object.GetType%2A> immer ein <xref:System.Type>\-Objekt zurück, das den zugrunde liegenden Typ darstellt, nicht den Typ, der NULL\-Werte zulässt.  
  
```  
int? i = 5;  
Type t = i.GetType();  
Console.WriteLine(t.FullName); //"System.Int32"  
```  
  
 Der Operator [is](../../../csharp/language-reference/keywords/is.md) von C\# kann für den zugrunde liegenden Typ eines Typs, der NULL\-Werte zulässt, verwendet werden.  Daher kann mit `is` nicht bestimmt werden, ob eine Variable ein Typ ist, der NULL\-Werte zulässt.  Das folgende Beispiel zeigt, dass der Operator `is` eine \<int\>\-Variable, die NULL\-Werte zulässt, als int behandelt.  
  
```  
static void Main(string[] args)  
{  
  int? i = 5;  
  if (i is int) // true  
    //…  
}  
```  
  
## Beispiel  
 Verwenden Sie den folgenden Code, um zu bestimmen, ob ein <xref:System.Type>\-Objekt einen Typ darstellt, der NULL\-Werte zulässt.  Beachten Sie, dass dieser Code immer false zurückgibt, wenn das `Type`\-Objekt durch einen Aufruf von <xref:System.Object.GetType%2A> zurückgegeben wurde, wie oben beschrieben.  
  
```  
if (type.IsGenericType && type.GetGenericTypeDefinition() == typeof(Nullable<>)) {…}  
```  
  
## Siehe auch  
 [Typen, die NULL\-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md)   
 [Boxing von Typen, die NULL\-Werte zulassen](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)