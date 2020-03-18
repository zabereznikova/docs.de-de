---
title: Konstruktoren – C#-Programmierhandbuch
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 8eedfaed111f01cc2ec55a2f42df66d4588bd42f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398400"
---
# <a name="constructors-c-programming-guide"></a>Konstruktoren (C#-Programmierhandbuch)

Wenn eine [class](../../language-reference/keywords/class.md) oder [struct](../../language-reference/builtin-types/struct.md) erstellt wird, wird deren Konstruktor aufgerufen. Eine Klasse oder Struktur verfügt möglicherweise über mehrere Konstruktoren, die andere Argumente verwenden. Mit Konstruktoren können Programmierer Standardwerte festlegen, Instanziierungen einschränken und Code schreiben, der flexibel und leicht zu lesen ist. Weitere Informationen und Beispiele finden Sie unter [Verwenden von Konstruktoren](./using-constructors.md) und [Instanzkonstruktoren](./instance-constructors.md).  

## <a name="parameterless-constructors"></a>Parameterlose Konstruktoren
  
Wenn Sie keinen Konstruktor für die Klasse angeben, erstellt C# standardmäßig einen, der das Objekt instanziiert und Membervariablen auf die Standardwerte festlegt, wie in den [Standardwerten der C#-Typen](../../language-reference/builtin-types/default-values.md) aufgeführt. Wenn Sie keinen Konstruktor für die Struktur angeben, stützt sich C# auf einen *impliziten parameterlosen Konstruktor*, um automatisch jedes Feld auf seinen Standardwert zu initialisieren. Weitere Informationen und Beispiele finden Sie unter [Instanzkonstruktoren](instance-constructors.md).  

## <a name="constructor-syntax"></a>Konstruktorsyntax

Ein Konstruktor ist eine Methode, dessen Name derselbe ist wie der seines Typs. Die Methodensignatur enthält nur den Methodennamen und die Parameterliste; ein Rückgabetyp ist nicht enthalten. Im folgenden Beispiel wird der Konstruktor für eine Klasse mit dem Namen `Person` gezeigt.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

Wenn ein Konstruktor als einzelne Anweisung implementiert werden kann, können Sie eine [expression body definition (Ausdruckstextdefinition)](../statements-expressions-operators/expression-bodied-members.md) verwenden. Im folgenden Beispiel wird eine `Location`-Klasse definiert, deren Klassenkonstruktor einen einzelnen Zeichenfolgenparameter namens *name* enthält. Die Ausdruckstextdefinition weist das Argument dem Feld `locationName` zu.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a>Statische Konstruktoren

Die vorherigen Beispiele haben alle Instanzkonstruktoren gezeigt, die ein neues Objekt erstellen. Eine Klasse oder Struktur kann auch einen statischen Konstruktor haben, der statische Member dieses Typs initialisiert.  Statische Konstruktoren sind parameterlos. Wenn Sie keinen statischen Konstruktor zum Initialisieren von statischen Feldern angeben, initialisiert der C#-Compiler statische Felder mit ihrem Standardwert, wie unter [Standardwerte der C#-Typen](../../language-reference/builtin-types/default-values.md) aufgeführt.

Im folgenden Beispiel wird ein statischer Konstruktor verwendet, um ein statisches Feld zu initialisieren.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

Sie können einen statischen Konstruktor auch mit einer Ausdruckstextdefinition definieren, wie im folgenden Beispiel gezeigt.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

Weitere Informationen und Beispiele finden Sie unter [Statische Konstruktoren](./static-constructors.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Verwenden von Konstruktoren](./using-constructors.md)  
  
 [Instanzkonstruktoren](./instance-constructors.md)  
  
 [Private Konstruktoren](./private-constructors.md)  
  
 [Statische Konstruktoren](./static-constructors.md)  
  
 [Schreiben eines Kopierkonstruktors](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Finalizer](./destructors.md)
- [static](../../language-reference/keywords/static.md)
- [Why Do Initializers Run In The Opposite Order As Constructors? Part One (Warum werden Initialisierer In der entgegengesetzten Reihenfolge ausgeführt wie Konstruktoren? Teil Eins)](https://docs.microsoft.com/archive/blogs/ericlippert/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one)
