---
title: Abstrakte und versiegelte Klassen und Klassenmember – C#-Programmierhandbuch
description: Das abstrakte Schlüsselwort in C# erstellt unvollständige Klassen und Klassenmember. Das versiegelte Schlüsselwort verhindert die Vererbung vorheriger virtueller Klassen oder Klassenmember.
ms.date: 07/20/2015
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
ms.openlocfilehash: 391a8ccbb1fbe6626d1cd5a4b6fcfd9ace3506e6
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474487"
---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a>Abstrakte und versiegelte Klassen und Klassenmember (C#-Programmierhandbuch)
Das Schlüsselwort [abstract](../../language-reference/keywords/abstract.md) ermöglicht die Erstellung von Klassen und [Klassenmembern](../../language-reference/keywords/class.md), die unvollständig sind und in einer abgeleiteten Klasse implementiert werden müssen.  
  
 Mit dem Schlüsselwort [sealed](../../language-reference/keywords/sealed.md) können Sie die Vererbung von Klassen oder bestimmten Klassenmembern unterbinden, die zuvor als [virtuell](../../language-reference/keywords/virtual.md) gekennzeichnet wurden.  
  
## <a name="abstract-classes-and-class-members"></a>Abstrakte Klassen und Klassenmember  
 Klassen können durch Festlegen des Schlüsselworts `abstract` vor der Klassendefinition als abstrakt deklariert werden. Zum Beispiel:  
  
 [!code-csharp[csProgGuideInheritance#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#13)]  
  
 Eine abstrakte Klasse darf nicht instanziiert werden. Der Zweck einer abstrakten Klasse ist die Bereitstellung einer allgemeinen Definition einer Basisklasse, die für mehrere abgeleitete Klassen freigegeben ist. Eine Klassenbibliothek kann beispielsweise eine abstrakte Klasse definieren, die als Parameter für ihre Funktionen verwendet wird. Programmierer, die diese Bibliothek verwenden, benötigen ihre eigene Implementierung der Klasse, die sie von ihr ableiten können.  
  
 Abstrakte Klassen können auch abstrakte Methoden definieren. Zu diesem Zweck wird das Schlüsselwort `abstract` vor dem Rückgabetyp der Methode einfügt. Zum Beispiel:  
  
 [!code-csharp[csProgGuideInheritance#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#14)]  
  
 Abstrakte Methoden verfügen über keine Implementierung, deshalb folgt der Methodendefinition ein Semikolon statt eines normalen Methodenblocks. Von der abstrakten Klasse abgeleitete Klassen müssen alle abstrakten Methoden implementieren. Wenn eine abstrakte Klasse eine virtuelle Methode von einer Basisklasse erbt, kann sie die virtuelle Methode mit einer abstrakten Methode überschreiben. Zum Beispiel:  
  
 [!code-csharp[csProgGuideInheritance#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#15)]  
  
 Wenn eine `virtual`-Methode als `abstract` deklariert ist, bleibt sie für alle Klassen virtuell, die von der abstrakten Klasse erben. Eine Klasse, die eine abstrakte Methode erbt, kann nicht auf die ursprüngliche Implementierung der Methode zugreifen. Im vorherigen Beispiel konnte `DoWork` auf Klasse F `DoWork` auf Klasse D nicht aufrufen. So kann eine abstrakte Klasse abgeleitete Klassen dazu zwingen, neue Methodenimplementierungen für virtuelle Methoden bereitzustellen.  
  
## <a name="sealed-classes-and-class-members"></a>Versiegelte Klassen und Klassenmember  
 Klassen können durch Festlegen des Schlüsselworts `sealed` vor der Klassendefinition als [sealed](../../language-reference/keywords/sealed.md) deklariert werden. Zum Beispiel:  
  
 [!code-csharp[csProgGuideInheritance#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#16)]  
  
 Eine versiegelte Klasse kann nicht als Basisklasse verwendet werden. Aus diesem Grund kann sie auch keine abstrakte Klasse sein. Von versiegelten Klassen kann nicht abgeleitet werden. Weil sie nicht als Basisklasse verwendet werden können, können Aufrufe an versiegelte Klassenmember durch Laufzeitoptimierungen etwas beschleunigt werden.  
  
 Methoden, Indexer, Eigenschaften oder Ereignisse einer abgeleiteten Klasse, die einen virtuellen Member der Basisklasse überschreiben, können diesen Member als versiegelt deklarieren. Damit wird der virtuelle Aspekt des Members für jede weitere abgeleitete Klasse aufgehoben. Dazu wird in die Klassenmemberdeklaration das Schlüsselwort `sealed` vor dem Schlüsselwort [override](../../language-reference/keywords/override.md) eingefügt. Beispiel:  
  
 [!code-csharp[csProgGuideInheritance#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#17)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Vererbung](./inheritance.md)
- [Methoden](./methods.md)
- [Felder](./fields.md)
- [Definieren von abstrakten Eigenschaften](./how-to-define-abstract-properties.md)
