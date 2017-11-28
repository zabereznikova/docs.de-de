---
title: struct (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e8a848d5543291ef335e72cb7806158827e865dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="struct-c-reference"></a>struct (C#-Referenz)
Ein `struct`-Typ ist ein ein Werttyp, der in der Regeln verwendet wird, um eine kleine Gruppe verwandter Variablen zusammenzufassen, z. B. Koordinaten eines Rechtecks oder die Merkmale eines Lagerartikels. Im folgenden Beispiel wird eine einfache Strukturdeklaration veranschaulicht:  
  
```  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a>Hinweise  
 Strukturen können auch [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md), [Konstanten](../../../csharp/programming-guide/classes-and-structs/constants.md), [Felder](../../../csharp/programming-guide/classes-and-structs/fields.md), [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md), [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md), [Indexer](../../../csharp/programming-guide/indexers/index.md), [Operatoren](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [Ereignisse](../../../csharp/programming-guide/events/index.md) und [geschachtelte Typen](../../../csharp/programming-guide/classes-and-structs/nested-types.md) enthalten. Wenn jedoch mehrere solche Member erforderlich sind, sollten Sie sich überlegen, den Typ in eine Klasse umzuwandeln.  
  
 Beispiele finden Sie unter [Verwenden von Strukturen](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
 Strukturen können eine Schnittstelle implementieren, aber nicht von einer anderen Struktur erben. Aus diesem Grund können Strukturmember nicht als `protected` deklariert werden.  
  
 Weitere Informationen finden Sie unter [Strukturen](../../../csharp/programming-guide/classes-and-structs/structs.md).  
  
## <a name="examples"></a>Beispiele  
 Weitere Beispiele und Informationen finden Sie unter [Verwenden von Strukturen](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 Beispiele finden Sie unter [Verwenden von Strukturen](../../../csharp/programming-guide/classes-and-structs/using-structs.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md)  
 [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [Typen](../../../csharp/language-reference/keywords/types.md)  
 [Werttypen](../../../csharp/language-reference/keywords/value-types.md)  
 [class](../../../csharp/language-reference/keywords/class.md)  
 [interface](../../../csharp/language-reference/keywords/interface.md)  
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)
