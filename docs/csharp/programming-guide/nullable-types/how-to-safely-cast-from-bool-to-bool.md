---
title: 'Gewusst wie: Sichere Umwandlung von bool? in bool (C#-Programmierhandbuch)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- casting [C#], nullable types
- nullable types [C#], casting bool? to bool
ms.assetid: e06e4274-a443-422d-8ef1-9dbf9df55237
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1a6fa65c15bb5f1da9960dbc17bd25b4087ab862
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-safely-cast-from-bool-to-bool-c-programming-guide"></a>Gewusst wie: Sichere Umwandlung von bool? in bool (C#-Programmierhandbuch)
Der `bool?`-Typ, der NULL-Werte zulässt, kann drei verschiedene Werte enthalten: `true`, `false` und `null`. Aus diesem Grund kann der `bool?`-Typ nicht in Bedingungen mit `if`, `for` oder `while` verwendet werden. Beispielsweise verursacht der folgende Code einen Compilerfehler:  
  
```  
bool? b = null;  
if (b) // Error CS0266.  
{  
}  
```  
  
 Dies ist nicht zulässig, da unklar ist, was `null` im Kontext eines bedingten Ausdrucks bedeutet. Wenn Sie `bool?` in einer bedingten Anweisung verwenden möchten, überprüfen Sie zunächst die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft, um sicherzustellen, dass der Wert nicht `null` ist, und wandeln Sie den Typ dann in `bool` um. Weitere Informationen finden Sie unter [bool](../../../csharp/language-reference/keywords/bool.md). Wenn Sie die Umwandlung für einen `bool?`-Typ mit dem Wert `null` durchführen, wird bei der Prüfung eine <xref:System.InvalidOperationException> ausgelöst. Das folgende Beispiel zeigt eine Möglichkeit, `bool?` sicher in `bool` umzuwandeln:  
  
## <a name="example"></a>Beispiel  
  
```csharp  
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
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Literalschlüsselwörter](../../../csharp/language-reference/keywords/literal-keywords.md)  
 [Typen mit Nullwert](../../../csharp/programming-guide/nullable-types/index.md)  
 [?? Operator](../../../csharp/language-reference/operators/null-conditional-operator.md)
