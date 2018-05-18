---
title: 'Gewusst wie: Schreiben eines Kopierkonstruktors (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 8a7cc85d40272918f4839d13fcccb79b558eeac7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a>Gewusst wie: Schreiben eines Kopierkonstruktors (C#-Programmierhandbuch)
C# stellt keinen Kopierkonstruktor für Objekte bereit. Sie können jedoch selbst einen schreiben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird von der `Person`-[Klasse](../../../csharp/language-reference/keywords/class.md) ein Kopierkonstruktor definiert, der eine Instanz von `Person` als sein Argument annimmt. Die Werte der Eigenschaften des Arguments werden den Eigenschaften der neuen Instanz von `Person` zugewiesen. Der Code enthält einen alternativen Kopierkonstruktor, der die `Name`- und `Age`-Eigenschaften der Instanz sendet, die Sie in den Instanzenkonstruktor der Klasse kopieren möchten.  
  
 [!code-csharp[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ICloneable>  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md)
