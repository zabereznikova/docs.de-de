---
title: Abstrakte und versiegelte Klassen und Klassenmember (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0788ea0778b3f8b846231fc2408938b2236314c9
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a>Abstrakte und versiegelte Klassen und Klassenmember (C#-Programmierhandbuch)
Das Schlüsselwort [abstract](../../../csharp/language-reference/keywords/abstract.md) ermöglicht die Erstellung von Klassen und [Klassenmembern](../../../csharp/language-reference/keywords/class.md), die unvollständig sind und in einer abgeleiteten Klasse implementiert werden müssen.  
  
 Mit dem Schlüsselwort [sealed](../../../csharp/language-reference/keywords/sealed.md) können Sie die Vererbung von Klassen oder bestimmten Klassenmembern unterbinden, die zuvor als [virtuell](../../../csharp/language-reference/keywords/virtual.md) gekennzeichnet wurden.  
  
## <a name="abstract-classes-and-class-members"></a>Abstrakte Klassen und Klassenmember  
 Klassen können durch Festlegen des Schlüsselworts `abstract` vor der Klassendefinition als abstrakt deklariert werden. Zum Beispiel:  
  
 [!code-cs[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]  
  
 Eine abstrakte Klasse darf nicht instanziiert werden. Der Zweck einer abstrakten Klasse ist die Bereitstellung einer allgemeinen Definition einer Basisklasse, die für mehrere abgeleitete Klassen freigegeben ist. Eine Klassenbibliothek kann beispielsweise eine abstrakte Klasse definieren, die als Parameter für ihre Funktionen verwendet wird. Programmierer, die diese Bibliothek verwenden, benötigen ihre eigene Implementierung der Klasse, die sie von ihr ableiten können.  
  
 Abstrakte Klassen können auch abstrakte Methoden definieren. Zu diesem Zweck wird das Schlüsselwort `abstract` vor dem Rückgabetyp der Methode einfügt. Zum Beispiel:  
  
 [!code-cs[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]  
  
 Abstrakte Methoden verfügen über keine Implementierung, deshalb folgt der Methodendefinition ein Semikolon statt eines normalen Methodenblocks. Von der abstrakten Klasse abgeleitete Klassen müssen alle abstrakten Methoden implementieren. Wenn eine abstrakte Klasse eine virtuelle Methode von einer Basisklasse erbt, kann sie die virtuelle Methode mit einer abstrakten Methode überschreiben. Zum Beispiel:  
  
 [!code-cs[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]  
  
 Wenn eine `virtual`-Methode als `abstract` deklariert ist, bleibt sie für alle Klassen virtuell, die von der abstrakten Klasse erben. Eine Klasse, die eine abstrakte Methode erbt, kann nicht auf die ursprüngliche Implementierung der Methode zugreifen. Im vorherigen Beispiel konnte `DoWork` auf Klasse F `DoWork` auf Klasse D nicht aufrufen. So kann eine abstrakte Klasse abgeleitete Klassen dazu zwingen, neue Methodenimplementierungen für virtuelle Methoden bereitzustellen.  
  
## <a name="sealed-classes-and-class-members"></a>Versiegelte Klassen und Klassenmember  
 Klassen können durch Festlegen des Schlüsselworts `sealed` vor der Klassendefinition als [sealed](../../../csharp/language-reference/keywords/sealed.md) deklariert werden. Zum Beispiel:  
  
 [!code-cs[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]  
  
 Eine versiegelte Klasse kann nicht als Basisklasse verwendet werden. Aus diesem Grund kann sie auch keine abstrakte Klasse sein. Von versiegelten Klassen kann nicht abgeleitet werden. Weil sie nicht als Basisklasse verwendet werden können, können Aufrufe an versiegelte Klassenmember durch Laufzeitoptimierungen etwas beschleunigt werden.  
  
 Methoden, Indexer, Eigenschaften oder Ereignisse einer abgeleiteten Klasse, die einen virtuellen Member der Basisklasse überschreiben, können diesen Member als versiegelt deklarieren. Damit wird der virtuelle Aspekt des Members für jede weitere abgeleitete Klasse aufgehoben. Dazu wird in die Klassenmemberdeklaration das Schlüsselwort `sealed` vor dem Schlüsselwort [override](../../../csharp/language-reference/keywords/override.md) eingefügt. Zum Beispiel:  
  
 [!code-cs[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md)   
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Felder](../../../csharp/programming-guide/classes-and-structs/fields.md)   
 [Gewusst wie: Definieren von abstrakten Eigenschaften](../../../csharp/programming-guide/classes-and-structs/how-to-define-abstract-properties.md)

