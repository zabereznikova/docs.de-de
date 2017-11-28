---
title: Strukturen (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 475d9b96e078270faf6c841a62e6031556e8e539
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="structs-c-programming-guide"></a>Strukturen (C#-Programmierhandbuch)
Strukturen werden mit dem [struct](../../../csharp/language-reference/keywords/struct.md)-Schlüsselwort definiert, beispielsweise:  
  
 [!code-csharp[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 Strukturen teilen sich einen großen Teil der Syntax mit Klassen, obwohl Strukturen eingeschränkter als Klassen sind:  
  
-   Innerhalb einer Strukturdeklaration können Felder nicht initialisiert werden, außer Sie werden als const oder static deklariert.  
  
-   Eine Struktur kann keinen Standardkonstruktor (ein Konstruktor ohne Parameter) oder Finalizer deklarieren.  
  
-   Strukturen werden bei Zuweisung kopiert. Wenn eine Struktur einer neuen Variable zugewiesen wird, werden alle Daten kopiert, und jede Änderung an der neuen Kopie ändert nicht die Daten für das Original. Es ist wichtig, sich das zu merken, wenn Sie mit Auflistungen von Wertetypen wie Dictionary\<string, myStruct> arbeiten.  
  
-   Strukturen sind Werttypen, und Klassen sind Verweistypen.  
  
-   Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden.  
  
-   Strukturen können Konstruktoren deklarieren, die Parameter besitzen.  
  
-   Eine Struktur kann nicht von einer anderen Struktur oder Klasse erben, und sie kann auch nicht die Basis einer Klasse sein. Alle Strukturen erben direkt von `System.ValueType`, das von `System.Object` erbt.  
  
-   Eine Struktur kann Schnittstellen implementieren.  
  
-   Eine Struktur kann als ein Nullable-Typ verwendet werden und kann einen NULL-Wert zugewiesen bekommen.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen finden Sie unter:   
  
-   [Verwenden von Strukturen](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [Typen mit Nullwert](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [Gewusst wie: Unterschiede zwischen dem Übergeben einer Struktur und dem Übergeben eines Klassenverweises an eine Methode](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)
