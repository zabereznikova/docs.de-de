---
title: Boxing von Typen, die NULL-Werte zulassen (C#-Programmierhandbuch) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- boxing [C#], nullable types
- unboxing [C#], nullable types
- nullable types [C#], boxing and unboxing
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: e4ff2e8a31ca5a59494f80597460e90107e78c8a
ms.contentlocale: de-de
ms.lasthandoff: 03/24/2017

---
# <a name="boxing-nullable-types-c-programming-guide"></a>Boxing von Typen, die NULL-Werte zulassen (C#-Programmierhandbuch)
Objekte, die auf Typen basieren, die NULL-Werte zulassen, werden nur dann umschlossen, wenn das Objekt ungleich NULL ist. Wenn <xref:System.Nullable%601.HasValue%2A> `false` ist, wird der Objektverweis `null` zugewiesen, anstatt dass er geboxt wird. Zum Beispiel:  
  
```csharp  
bool? b = null;  
object o = b;  
// Now o is null.  
```  
  
 Wenn das Objekt ungleich NULL ist – wenn <xref:System.Nullable%601.HasValue%2A> `true` ist –, kommt es zum Boxing. Allerdings wird nur der zugrundeliegende Typ, auf dem das auf NULL festlegbare Objekt basiert, geboxt. Das Boxing eines nicht auf NULL festlegbaren Werttyps umschließt den Werttyp selbst und nicht das <xref:System.Nullable%601?displayProperty=fullName>-Objekt, das den Werttyp umschließt. Zum Beispiel:  
  
```csharp  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 Die beiden geboxten Objekte stimmen mit Objekten überein, die beim Boxing von nicht auf NULL festlegbaren Typen entstehen. Sie können, genauso wie nicht auf NULL festlegbare Typen, in auf NULL festlegbare Typen „ausgewickelt“ werden, so wie in folgendem Beispiel:  
  
```csharp  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## <a name="remarks"></a>Hinweise  
 Das Verhalten von umschlossenen, auf NULL festlegbaren Typen hat zwei Vorteile:  
  
1.  Auf NULL festlegbare Objekte und ihre umschlossenen Gegenstücke könne auf NULL getestet werden:  
  
    ```csharp  
    bool? b = null;  
    object boxedB = b;  
    if (b == null)  
    {  
      // True.  
    }  
    if (boxedB == null)  
    {  
      // Also true.  
    }  
    ```  
  
2.  Umschlossene, auf NULL festlegbare Typen unterstützen die Funktionen des zugrundeliegenden Typs vollständig:  
  
    ```csharp  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Typen, die NULL-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md)   
 [Gewusst wie: Identifizieren eines Typs mit Nullwerten](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)
