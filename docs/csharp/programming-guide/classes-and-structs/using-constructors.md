---
title: Verwenden von Konstruktoren – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: 7c227b61c6d5b4ead00fced0dba046b90683fde1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77626411"
---
# <a name="using-constructors-c-programming-guide"></a>Verwenden von Konstruktoren (C#-Programmierhandbuch)

Wenn eine [Klasse](../../language-reference/keywords/class.md) oder [Struktur](../../language-reference/builtin-types/struct.md) erstellt wird, wird deren Konstruktor aufgerufen. Konstruktoren haben den gleichen Namen wie die Klasse oder Struktur, und sie initialisieren normalerweise die Datenmember des neuen Objekts.  
  
 Im folgenden Beispiel wird eine Klasse mit dem Namen `Taxi` durch Verwendung eines einfachen Konstruktors definiert. Die Klasse wird dann mit dem [new](../../language-reference/operators/new-operator.md)-Operator instanziiert. Der `Taxi`-Konstruktor wird sofort durch den `new`-Operator aufgerufen, nachdem Speicher für das neue Objekt zugewiesen wurde.  
  
 [!code-csharp[csProgGuideObjects#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#53)]  
  
 Ein Konstruktor, der keine Parameter akzeptiert, wird *parameterloser Konstruktor* genannt. Parameterlose Konstruktoren werden aufgerufen, wenn ein Objekt durch Verwendung des Operators `new` instanziiert wird und keine Argumente für `new` bereitgestellt werden. Weitere Informationen finden Sie unter [Instanzkonstruktoren](./instance-constructors.md).  
  
 Klassen ohne Konstruktoren erhalten vom C#-Compiler einen öffentlichen parameterlosen Konstruktor, um die Instanziierung der Klasse zuzulassen, außer die Klasse ist [static](../../language-reference/keywords/static.md). Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](./static-classes-and-static-class-members.md).  
  
 Sie können verhindern, dass eine Klasse instanziiert wird, indem Sie den Konstruktor auf „privat“ einstellen; dazu müssen Sie wie folgt vorgehen:  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 Weitere Informationen finden Sie unter [Private Konstruktoren](./private-constructors.md).  
  
 Konstruktoren für [struct](../../language-reference/builtin-types/struct.md)-Typen ähneln Klassenkonstruktoren, `structs` können aber keinen expliziten parameterlosen Konstruktor enthalten, da er automatisch vom Compiler bereitgestellt wird. Dieser Konstruktor initialisiert alle Felder in `struct` auf die [Standardwerte](../../language-reference/builtin-types/default-values.md). Dieser parameterlose Konstruktor wird jedoch nur aufgerufen, wenn `struct` mit `new` instanziiert wird. Dieser Code verwendet den parameterlosen Konstruktor z.B. für <xref:System.Int32>, damit sichergestellt ist, dass der ganzzahlige Typ initialisiert wird:  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 Der folgende Code verursacht jedoch einen Compilerfehler, da nicht `new` verwendet wird, und da versucht wird, ein Objekt zu verwenden, das nicht initialisiert wurde:  
  
```csharp  
int i;  
Console.WriteLine(i);  
```  
  
 Alternativ können auch Objekte, die auf `structs` basieren, – einschließlich aller integrierten numerischen Typen – initialisiert oder zugewiesen und anschließend verwendet werden, so wie im folgenden Beispiel:  
  
```csharp  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 Es ist also nicht erforderlich, einen parameterlosen Konstruktor für einen Werttyp aufzurufen.  
  
 Sowohl Klassen als auch `structs` können Konstruktoren definieren, die Parameter annehmen. Konstruktoren, die Parameter annehmen, müssen über eine `new`- oder [base](../../language-reference/keywords/base.md)-Anweisung aufgerufen werden. Klassen und `structs` können also mehrere Konstruktoren definieren, und keine von beiden wird zum Definieren eines parameterlosen Konstruktors benötigt. Beispiel:  
  
 [!code-csharp[csProgGuideObjects#54](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#54)]  
  
 Diese Klasse kann mithilfe aller folgenden Anweisungen erstellt werden:  
  
 [!code-csharp[csProgGuideObjects#55](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#55)]  
  
 Ein Konstruktor kann das Schlüsselwort `base` verwenden, um den Konstruktor einer Basisklasse aufzurufen. Beispiel:  
  
 [!code-csharp[csProgGuideObjects#56](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#56)]  
  
 In diesem Beispiel wird der Konstruktor der Basisklasse aufgerufen, bevor der Block eines Konstruktors ausgeführt wird. Das Schlüsselwort `base` kann mit oder ohne Parameter verwendet werden. Alle Parameter des Konstruktors können als Parameter für `base` oder als Teil eines Ausdrucks verwendet werden. Weitere Informationen finden Sie unter [base](../../language-reference/keywords/base.md).  
  
 Wenn ein Konstruktor der Basisklasse in einer abgeleiteten Klasse nicht explizit durch das Schlüsselwort `base` aufgerufen wird, wird der parameterlose Konstruktor (falls vorhanden) implizit aufgerufen. Dies bedeutet, dass die folgenden Deklarationen identisch sind:  
  
 [!code-csharp[csProgGuideObjects#58](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#58)]  
  
 [!code-csharp[csProgGuideObjects#57](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#57)]  
  
 Wenn eine Basisklasse keinen parameterlosen Konstruktor bereitstellt, muss die abgeleitete Klasse einen expliziten Aufruf an den Basiskonstruktor mithilfe von `base` durchführen.  
  
 Ein Konstruktor kann einen anderen Konstruktor in demselben Objekt über das Schlüsselwort [this](../../language-reference/keywords/this.md) aufrufen. Genau wie `base` kann `this` mit oder ohne Parameter verwendet werden, und alle Parameter im Konstruktor sind als Parameter für `this` oder als Teil eines Ausdrucks verfügbar. Der zweite Konstruktor im vorherigen Beispiel kann z.B. über `this` neu geschrieben werden:  
  
 [!code-csharp[csProgGuideObjects#59](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#59)]  
  
 Die Verwendung des Schlüsselworts `this` im vorherigen Beispiel bewirkt, dass dieser Konstruktor aufgerufen wird:  
  
 [!code-csharp[csProgGuideObjects#60](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#60)]  
  
 Konstruktoren können als [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) oder [private protected](../../language-reference/keywords/private-protected.md) markiert werden. Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse die Klasse konstruieren können. Weitere Informationen finden Sie unter [Zugriffsmodifizierer](./access-modifiers.md).  
  
 Ein Konstruktor kann mithilfe des Schlüsselworts [static](../../language-reference/keywords/static.md) als statisch deklariert werden. Statische Konstruktoren werden automatisch aufgerufen, unmittelbar bevor auf ein statisches Feld zugegriffen wird, und werden generell zum Initialisieren statischer Klassenmember verwendet. Weitere Informationen finden Sie unter [Statische Konstruktoren](./static-constructors.md).  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  

Weitere Informationen erhalten Sie unter [Instanzkonstruktoren](~/_csharplang/spec/classes.md#instance-constructors) und [Statische Konstruktoren](~/_csharplang/spec/classes.md#static-constructors) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Konstruktoren](./constructors.md)
- [Finalizer](./destructors.md)
