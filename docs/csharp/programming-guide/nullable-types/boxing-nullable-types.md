---
title: "Boxing von Typen, die NULL-Werte zulassen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Boxing [C#], Typen mit Nullwert"
  - "Typen, die NULL-Werte zulassen [C#], Boxing und Unboxing"
  - "Unboxing [C#], Typen mit Nullwert"
ms.assetid: bdb5b626-abc0-405d-8f64-0f0a0bf883a4
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# Boxing von Typen, die NULL-Werte zulassen (C#-Programmierhandbuch)
Objekte, die auf Typen basieren, die NULL\-Werte zulassen, werden nur geschachtelt, wenn das Objekt nicht NULL ist.  Wenn <xref:System.Nullable%601.HasValue%2A> den Wert `false` aufweist, wird das Objekt nicht geschachtelt. Stattdessen wird der Objektverweis einfach `null` zugewiesen.  Beispiele:  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Wenn das Objekt nicht NULL ist – wenn <xref:System.Nullable%601.HasValue%2A> den Wert `true` aufweist –, findet das Boxing statt, es wird aber nur der zugrunde liegende Typ geschachtelt, auf dem das auf NULL festlegbare Objekt basiert.  Beim Schachteln eines auf NULL festlegbaren Werttyps, der nicht NULL lautet, wird der Werttyp selbst und nicht das <xref:System.Nullable%601?displayProperty=fullName> geschachtelt, das den Werttyp umschließt.  Beispiele:  
  
```  
bool? b = false;  
int? i = 44;  
object bBoxed = b; // bBoxed contains a boxed bool.  
object iBoxed = i; // iBoxed contains a boxed int.  
```  
  
 Die zwei geschachtelten Objekte sind identisch mit den Objekten, die durch das Schachteln von nicht auf NULL festlegbaren Typen erstellt werden.  Und wie nicht auf NULL festlegbare geschachtelte Typen können sie mittels Unboxing in auf NULL festlegbare Typen konvertiert werden. Beispiel:  
  
```  
bool? b2 = (bool?)bBoxed;  
int? i2 = (int?)iBoxed;  
```  
  
## Hinweise  
 Das Verhalten von auf NULL festlegbaren geschachtelten Typen bietet zwei Vorteile:  
  
1.  Auf NULL festlegbare Objekte und ihre geschachtelten Entsprechungen können auf NULL\-Werte getestet werden:  
  
    ```  
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
  
2.  Geschachtelte auf NULL festlegbare Typen unterstützen vollständig die Funktionen des zugrunde liegenden Typs:  
  
    ```  
    double? d = 44.4;  
    object iBoxed = d;  
    // Access IConvertible interface implemented by double.  
    IConvertible ic = (IConvertible)iBoxed;  
    int i = ic.ToInt32(null);  
    string str = ic.ToString();  
    ```  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Typen, die NULL\-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md)   
 [Gewusst wie: Identifizieren eines Typs, der NULL\-Werte zulässt](../../../csharp/programming-guide/nullable-types/how-to-identify-a-nullable-type.md)