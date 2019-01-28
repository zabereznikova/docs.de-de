---
title: Konstruktoren – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: e88cc9b36f64a559105620359f4c163978cf9d8c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692258"
---
# <a name="constructors-c-programming-guide"></a>Konstruktoren (C#-Programmierhandbuch)
Wenn eine [class](../../../csharp/language-reference/keywords/class.md) oder [struct](../../../csharp/language-reference/keywords/struct.md) erstellt wird, wird deren Konstruktor aufgerufen. Eine Klasse oder Struktur verfügt möglicherweise über mehrere Konstruktoren, die andere Argumente verwenden. Mit Konstruktoren können Programmierer Standardwerte festlegen, Instanziierungen einschränken und Code schreiben, der flexibel und leicht zu lesen ist. Weitere Informationen und Beispiele finden Sie unter [Verwenden von Konstruktoren](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) und [Instanzkonstruktoren](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  

## <a name="default-constructors"></a>Standardkonstruktoren
  
Wenn Sie keinen Konstruktor für die Klasse angeben, erstellt C# standardmäßig einen, der das Objekt instanziiert und Membervariablen auf die Standardwerte festlegt, wie in der [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md) aufgeführt. Wenn Sie keinen Konstruktor für die Struktur angeben, stützt sich C# auf einen *impliziten Standardkonstruktor*, um automatisch jedes Feld eines Werttyps auf seinen Standardwert zu initialisieren, wie in der [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md) aufgeführt. Weitere Informationen und Beispiele finden Sie unter [Instanzkonstruktoren](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  

## <a name="constructor-syntax"></a>Konstruktorsyntax

Ein Konstruktor ist eine Methode, dessen Name derselbe ist wie der seines Typs. Die Methodensignatur enthält nur den Methodennamen und die Parameterliste; ein Rückgabetyp ist nicht enthalten. Im folgenden Beispiel wird der Konstruktor für eine Klasse mit dem Namen `Person` gezeigt.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

Wenn ein Konstruktor als einzelne Anweisung implementiert werden kann, können Sie eine [expression body definition (Ausdruckstextdefinition)](../statements-expressions-operators/expression-bodied-members.md) verwenden. Im folgenden Beispiel wird eine `Location`-Klasse definiert, deren Klassenkonstruktor einen einzelnen Zeichenfolgenparameter namens *name* enthält. Die Ausdruckstextdefinition weist das Argument dem Feld `locationName` zu.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a>Statische Konstruktoren

Die vorherigen Beispiele haben alle Instanzkonstruktoren gezeigt, die ein neues Objekt erstellen. Eine Klasse oder Struktur kann auch einen statischen Konstruktor haben, der statische Member dieses Typs initialisiert.  Statische Konstruktoren sind parameterlos. Wenn Sie keinen statischen Konstruktor zum Initialisieren von statischen Feldern angeben, wird der C#-Compiler einen statischen Standardkonstruktor bereitstellen, der statische Felder auf ihren Standardwert initialisiert, wie in der [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md) aufgeführt. 

Im folgenden Beispiel wird ein statischer Konstruktor verwendet, um ein statisches Feld zu initialisieren.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

Sie können einen statischen Konstruktor auch mit einer Ausdruckstextdefinition definieren, wie im folgenden Beispiel gezeigt. 

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

Weitere Informationen und Beispiele finden Sie unter [Statische Konstruktoren](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Verwenden von Konstruktoren](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [Instanzkonstruktoren](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [Private Konstruktoren](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [Statische Konstruktoren](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [Vorgehensweise: Schreiben eines Kopierkonstruktors](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md)
- [static](../../../csharp/language-reference/keywords/static.md)
- [Why Do Initializers Run In The Opposite Order As Constructors? Part One (Warum werden Initialisierer In der entgegengesetzten Reihenfolge ausgeführt wie Konstruktoren? Teil Eins)](https://blogs.msdn.microsoft.com/ericlippert/2008/02/15/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)
