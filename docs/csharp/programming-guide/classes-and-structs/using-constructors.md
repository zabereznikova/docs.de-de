---
title: Verwenden von Konstruktoren (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: b19676b2549bbb54af7fb1d72ff0e98352c61383
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529019"
---
# <a name="using-constructors-c-programming-guide"></a>Verwenden von Konstruktoren (C#-Programmierhandbuch)
Wenn eine [Klasse](../../../csharp/language-reference/keywords/class.md) oder [Struktur](../../../csharp/language-reference/keywords/struct.md) erstellt wird, wird deren Konstruktor aufgerufen. Konstruktoren haben den gleichen Namen wie die Klasse oder Struktur, und sie initialisieren normalerweise die Datenmember des neuen Objekts.  
  
 Im folgenden Beispiel wird eine Klasse mit dem Namen `Taxi` durch Verwendung eines einfachen Konstruktors definiert. Die Klasse wird dann mit dem [new](../../../csharp/language-reference/keywords/new.md)-Operator instanziiert. Der `Taxi`-Konstruktor wird sofort durch den `new`-Operator aufgerufen, nachdem Speicher für das neue Objekt zugewiesen wurde.  
  
 [!code-csharp[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]  
  
 Ein Konstruktor, der keine Parameter akzeptiert, wird *Standardkonstruktor* genannt. Standardkonstruktoren werden aufgerufen, wenn ein Objekt durch Verwendung des `new`-Operators instanziiert wird und keine Argumente für `new` bereitgestellt werden. Weitere Informationen finden Sie unter [Instanzkonstruktoren](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  
  
 Klassen ohne Konstruktoren erhalten vom C#-Compiler einen öffentlichen Standardkonstruktor, um die Instanziierung der Klasse zuzulassen, außer die Klasse ist [static](../../../csharp/language-reference/keywords/static.md). Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Sie können verhindern, dass eine Klasse instanziiert wird, indem Sie den Konstruktor auf „privat“ einstellen; dazu müssen Sie wie folgt vorgehen:  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]  
  
 Weitere Informationen finden Sie unter [Private Konstruktoren](../../../csharp/programming-guide/classes-and-structs/private-constructors.md).  
  
 Konstruktoren für [struct](../../../csharp/language-reference/keywords/struct.md)-Typen ähneln Klassenkonstruktoren, `structs` können aber keinen expliziten Standardkonstruktor enthalten, da er automatisch vom Compiler bereitgestellt wird. Dieser Konstruktor initialisiert alle Felder in `struct` auf die Standardwerte. Weitere Informationen finden Sie unter [Tabelle für Standardwerte](../../../csharp/language-reference/keywords/default-values-table.md). Dieser Standardkonstruktor wird jedoch nur aufgerufen, wenn `struct` mit `new` instanziiert wird. Dieser Code verwendet den Standardkonstruktor z.B. für <xref:System.Int32>, damit sichergestellt ist, dass der ganzzahlige Typ initialisiert wird:  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 Der folgende Code verursacht jedoch einen Compilerfehler, da nicht `new` verwendet wird, und da versucht wird, ein Objekt zu verwenden, das nicht initialisiert wurde:  
  
```  
int i;  
Console.WriteLine(i);  
```  
  
 Alternativ können auch Objekte, die auf `structs` basieren, – einschließlich aller integrierten numerischen Typen – initialisiert oder zugewiesen und anschließend verwendet werden, so wie im folgenden Beispiel:  
  
```  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 Es ist also nicht erforderlich, einen Standardkonstruktor für einen Werttyp aufzurufen.  
  
 Sowohl Klassen als auch `structs` können Konstruktoren definieren, die Parameter annehmen. Konstruktoren, die Parameter annehmen, müssen über eine `new`- oder [base](../../../csharp/language-reference/keywords/base.md)-Anweisung aufgerufen werden. Klassen und `structs` können also mehrere Konstruktoren definieren, und keine von beiden wird zum Definieren eines Standardkonstruktors benötigt. Zum Beispiel:  
  
 [!code-csharp[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]  
  
 Diese Klasse kann mithilfe aller folgenden Anweisungen erstellt werden:  
  
 [!code-csharp[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]  
  
 Ein Konstruktor kann das Schlüsselwort `base` verwenden, um den Konstruktor einer Basisklasse aufzurufen. Zum Beispiel:  
  
 [!code-csharp[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]  
  
 In diesem Beispiel wird der Konstruktor der Basisklasse aufgerufen, bevor der Block eines Konstruktors ausgeführt wird. Das Schlüsselwort `base` kann mit oder ohne Parameter verwendet werden. Alle Parameter des Konstruktors können als Parameter für `base` oder als Teil eines Ausdrucks verwendet werden. Weitere Informationen finden Sie unter [base](../../../csharp/language-reference/keywords/base.md).  
  
 Wenn ein Konstruktor der Basisklasse in einer abgeleiteten Klasse nicht explizit durch das Schlüsselwort `base` aufgerufen wird, wird der Standardkonstruktor (falls vorhanden) implizit aufgerufen. Dies bedeutet, dass die folgenden Deklarationen identisch sind:  
  
 [!code-csharp[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]  
  
 [!code-csharp[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]  
  
 Wenn eine Basisklasse keinen Standardkonstruktor bereitstellt, muss die abgeleitete Klasse einen expliziten Aufruf an den Basiskonstruktor mithilfe von `base` durchführen.  
  
 Ein Konstruktor kann einen anderen Konstruktor in demselben Objekt über das Schlüsselwort [this](../../../csharp/language-reference/keywords/this.md) aufrufen. Genau wie `base` kann `this` mit oder ohne Parameter verwendet werden, und alle Parameter im Konstruktor sind als Parameter für `this` oder als Teil eines Ausdrucks verfügbar. Der zweite Konstruktor im vorherigen Beispiel kann z.B. über `this` neu geschrieben werden:  
  
 [!code-csharp[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]  
  
 Die Verwendung des Schlüsselworts `this` im vorherigen Beispiel bewirkt, dass dieser Konstruktor aufgerufen wird:  
  
 [!code-csharp[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]  
  
 Konstruktoren können als [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md) oder [private protected](../../../csharp/language-reference/keywords/private-protected.md) markiert werden. Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse die Klasse konstruieren können. Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Ein Konstruktor kann mithilfe des Schlüsselworts [static](../../../csharp/language-reference/keywords/static.md) als statisch deklariert werden. Statische Konstruktoren werden automatisch aufgerufen, unmittelbar bevor auf ein statisches Feld zugegriffen wird, und werden generell zum Initialisieren statischer Klassenmember verwendet. Weitere Informationen finden Sie unter [Statische Konstruktoren](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [Finalizer](../../../csharp/programming-guide/classes-and-structs/destructors.md)
