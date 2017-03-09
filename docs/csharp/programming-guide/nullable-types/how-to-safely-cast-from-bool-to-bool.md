---
title: "Gewusst wie: Sichere Umwandlung von bool? in bool (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Typumwandlung [C#], Typen mit Nullwert"
  - "Typen, die NULL-Werte zulassen [C#], Umwandeln von bool? in bool"
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# Gewusst wie: Sichere Umwandlung von bool? in bool (C#-Programmierhandbuch)
Der `bool?`\-Typ, der NULL\-Werte zulässt, kann drei verschiedene Werte enthalten: `true`, `false` und `null`.  Aus diesem Grund kann der `bool?`\-Typ nicht in Bedingungen mit `if`, `for` oder `while` verwendet werden.  Beispielsweise verursacht der folgende Code einen Compilerfehler:  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 Dies ist nicht zulässig, da unklar ist, was `null` im Kontext eines bedingten Ausdrucks bedeutet.  Wenn Sie `bool?` in einer bedingten Anweisung verwenden möchten, überprüfen Sie zunächst die <xref:System.Nullable%601.HasValue%2A>\-Eigenschaft, um sicherzustellen, dass der Wert nicht `null` ist, und wandeln Sie den Typ dann in `bool` um.  Weitere Informationen finden Sie unter [bool](../../../csharp/language-reference/keywords/bool.md).  Wenn Sie die Umwandlung für einen `bool?`\-Typ mit dem Wert `null` durchführen, wird bei der Prüfung eine <xref:System.InvalidOperationException> ausgelöst.  Das folgende Beispiel zeigt eine Möglichkeit, `bool?` sicher in `bool` umzuwandeln:  
  
## Beispiel  
  
```c#  
bool? test = null;  
// Other code that may or may not  
// give a value to test.  
if(!test.HasValue) //check for a value  
{  
    // Assume that IsInitialized  
    // returns either true or false.  
    test = IsInitialized();  
}  
if((bool)test) //now this cast is safe  
{  
   // Do something.  
}  
```  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Literalschlüsselwörter](../../../csharp/language-reference/keywords/literal-keywords.md)   
 [Typen, die NULL\-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md)   
 [?? Operator](../../../csharp/language-reference/operators/null-conditional-operator.md)