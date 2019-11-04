---
title: Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“ – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, versioning
- C# language, override and new
ms.assetid: 88247d07-bd0d-49e9-a619-45ccbbfdf0c5
ms.openlocfilehash: c85f5b6b4552dc4a10c7ad66b8f93331f97a8621
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73196205"
---
# <a name="versioning-with-the-override-and-new-keywords-c-programming-guide"></a>Versionsverwaltung mit den Schlüsselwörtern "override" und "new" (C#-Programmierhandbuch)
Die C#-Sprache wurde entwickelt, damit die Versionierung von [base](../../language-reference/keywords/base.md)- (Basis-) und abgeleiteten Klassen in unterschiedlichen Bibliotheken weiterentwickelt und die Abwärtskompatibilität aufrechterhalten werden kann. Das bedeutet z.B., dass die Einführung eines neuen Members in einer [Basisklasse](../../language-reference/keywords/class.md) mit demselben Name wie ein Member in einer abgeleiteten Klasse von C# vollständig unterstützt wird und nicht zu unerwartetem Verhalten führt. Das bedeutet auch, dass eine Klasse explizit angeben muss, ob eine Methode für das außer Kraft setzen einer geerbten Methode vorgesehen ist, oder ob eine Methode eine neue Methode ist, die eine Methode mit ähnlichem Namen verbirgt.  
  
 In C# können abgeleitete Klassen Methoden mit dem gleichen Namen wie Basisklassen-Methoden enthalten.  
  
- Die Basisklasse muss als [virtual](../../language-reference/keywords/virtual.md) definiert werden.  
  
- Wenn der Methode in der abgeleiteten Klasse nicht die Schlüsselwörter [new](../../language-reference/keywords/new-modifier.md) oder [override](../../language-reference/keywords/override.md) vorangestellt sind, gibt der Compiler eine Warnung aus, und die Methode verhält sich, als ob das Schlüsselwort `new` vorhanden wäre.  
  
- Wenn der Methode in der abgeleiteten Klasse das Schlüsselwort `new` vorangestellt ist, wird die Methode als unabhängig von der Methode in der Basisklasse definiert.  
  
- Wenn der Methode in der abgeleiteten Klasse das Schlüsselwort `override` vorangestellt ist, rufen Objekte der abgeleiteten Klasse diese Methode anstatt der Methode der Basisklasse auf.  
  
- Die Methode der Basisklasse kann mithilfe des Schlüsselworts `base` aus der Basisklasse heraus aufgerufen werden.  
  
- Die Schlüsselwörter `override`, `virtual` und `new` können auch auf Eigenschaften, Indexer und Ereignisse angewendet werden.  
  
 Standardmäßig sind C#-Methoden nicht virtuell. Wenn eine Methode als virtuell deklariert wird, kann jede Klasse, die die Methode erbt, ihre eigene Version implementieren. Um eine Methode in eine virtuelle Methode zu transformieren, wird der Modifizierer `virtual` in der Methodendeklaration der Basisklasse verwendet. Die abgeleitete Klasse kann anschließend die virtuelle Methode der Basisklasse mithilfe des Schlüsselworts `override` überschreiben oder die virtuelle Methode in der Basisklasse mithilfe des Schlüsselworts `new` verbergen. Wenn weder das Schlüsselwort `override` noch das Schlüsselwort `new` angegeben ist, gibt der Compiler eine Warnung aus, und die Methode in der abgeleiteten Klasse verbirgt die Methode in der Basisklasse.  
  
 Nehmen wir zur Veranschaulichung dieser Vorgehensweise für einen Moment an, dass die Firma A eine Klasse mit dem Namen `GraphicsClass` erstellt, die Ihr Programm benutzt. Die folgende Datei ist `GraphicsClass`:  
  
 [!code-csharp[csProgGuideInheritance#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#27)]  
  
 Ihr Unternehmen verwendet diese Klasse, und Sie verwenden sie zum Ableiten einer Klasse oder zum Hinzufügen einer neuen Methode:  
  
 [!code-csharp[csProgGuideInheritance#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#28)]  
  
 Ihre Anwendung wird ohne Probleme verwendet, bis Firma A eine neue Version von `GraphicsClass` herausgibt, die dem folgenden Code ähnelt:  
  
 [!code-csharp[csProgGuideInheritance#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#29)]  
  
 Die neue Version von `GraphicsClass` enthält jetzt eine Methode namens `DrawRectangle`. Anfänglich geschieht nichts. Die neue Version ist immer noch binärkompatibel mit der alten Version. Jede Software, die Sie entwickelt haben, funktioniert weiterhin, sogar wenn die neue Klasse auf diesen Computersystemen installiert ist. Aufgrund vorhandener Aufrufe der Methode verweist `DrawRectangle` weiterhin auf Ihre Version in Ihrer abgeleiteten Klasse.  
  
 Sobald Sie Ihre Anwendung aber mit der neuen Version von `GraphicsClass` neu kompilieren, erhalten Sie vom Compiler eine Warnung, CS0108. Diese Warnung informiert Sie darüber, dass Sie das gewünschte Verhalten der `DrawRectangle`-Methode in Ihrer Anwendung bestimmen müssen.  
  
 Wenn Sie möchten, dass Ihre Methode die neue Basisklassenmethode außer Kraft setzt, verwenden Sie das Schlüsselwort `override`:  
  
 [!code-csharp[csProgGuideInheritance#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#30)]  
  
 Das Schlüsselwort `override` stellt sicher, dass alle Objekte, die von `YourDerivedGraphicsClass` abgeleitet sind, die Version von `DrawRectangle` der abgeleiteten Klasse verwenden. Objekte, die von `YourDerivedGraphicsClass` abgeleitet sind, können auf die Basisklassenversion von `DrawRectangle` mithilfe des base-Schlüsselworts zugreifen:  
  
 [!code-csharp[csProgGuideInheritance#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#44)]  
  
 Wenn Sie nicht möchten, dass Ihre Methode die neue Basisklassenmethode außer Kraft setzt, gelten die folgenden Überlegungen. Sie können Ihre Methode umbenennen, um Verwechslungen zwischen den beiden Methoden zu vermeiden. Dies kann zeitaufwändig und fehleranfällig sein und ist in einigen Fällen einfach nicht praktikabel. Wenn das Projekt aber relativ klein ist, können Sie die Refactoring-Optionen von Visual Studio verwenden, um die Methode umzubenennen. Weitere Informationen finden Sie unter [Refactoring von Klassen und Typen (Klassen-Designer)](/visualstudio/ide/class-designer/refactoring-classes-and-types).  
  
 Alternativ können Sie die Warnung vermeiden, indem Sie in der Definition Ihrer abgeleiteten Klasse das Schlüsselwort `new` verwenden:  
  
 [!code-csharp[csProgGuideInheritance#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#31)]  
  
 Mit dem Schlüsselwort `new` teilt der Compiler mit, dass Ihre Definition die Definition ausblendet, die in der Basisklasse enthalten ist. Dies ist das Standardverhalten.  
  
## <a name="override-and-method-selection"></a>Überschreiben und Methodenauswahl  
 Wenn eine Methode in einer Klasse benannt wird, wählt der C#-Compiler die beste Methode zum Aufrufen aus, wenn mehr als eine Methode mit dem Aufruf kompatibel ist, z.B. wenn es zwei Methoden mit dem gleichen Namen und Parameter gibt, die mit dem übergebenen Parameter kompatibel sind. Die folgenden Methoden wären kompatibel:  
  
 [!code-csharp[csProgGuideInheritance#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#32)]  
  
 Wenn `DoWork` für eine Instanz von `Derived` aufgerufen wird, versucht der C#-Compiler zuerst, den Aufruf mit den Versionen von `DoWork` kompatibel zu machen, die ursprünglich für `Derived` deklariert wurden. Override-Methoden werden nicht als Methoden angesehen, die für eine Klasse deklariert sind. Stattdessen sind sie neue Implementierungen einer Methode, die für eine Basisklasse deklariert wurde. Nur wenn der C#-Compiler keine Übereinstimmung des Methodenaufrufs mit dem Aufruf einer ursprünglichen Methode in `Derived` feststellen kann, versucht er, den Aufruf mit einer überschriebenen Methode mit dem gleichen Namen und kompatiblen Parametern übereinzustimmen. Beispiel:  
  
 [!code-csharp[csProgGuideInheritance#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#33)]  
  
 Da die Variable `val` implizit in einen Double-Wert konvertiert werden kann, ruft der C#-Compiler `DoWork(double)` anstelle von `DoWork(int)` auf. Es gibt zwei Möglichkeiten, das zu vermeiden. Vermeiden Sie zuerst das Deklarieren neuer Methoden mit dem gleichen Namen wie virtuelle Methoden. Zweitens können Sie den C#-Compiler anweisen, die virtuelle Methode aufzurufen, indem Sie eine Suche nach der Liste der Basisklassenmethode durchführen lassen. Dies geschieht durch umwandeln der Instanz von `Derived` in `Base`. Da es sich um eine virtuelle Methode handelt, wird die Implementierung von `DoWork(int)` auf `Derived` aufgerufen. Beispiel:  
  
 [!code-csharp[csProgGuideInheritance#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#34)]  
  
 Weitere Beispiele für `new` und `override` finden Sie unter [Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden?](./knowing-when-to-use-override-and-new-keywords.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Methoden](./methods.md)
- [Vererbung](./inheritance.md)
