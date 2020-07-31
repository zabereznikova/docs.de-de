---
title: Objekt- und Auflistungsinitialisierer – C#-Programmierhandbuch
description: Objektinitialisierer in C# weisen bei der Erstellung verfügbaren Feldern oder Eigenschaften eines Objekts Werte zu, nachdem ein Konstruktor aufgerufen wurde.
ms.date: 12/19/2018
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: 81deed8a21bff10364524c3e0784c562d4e727e6
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864773"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a>Objekt- und Auflistungsinitialisierer (C#-Programmierhandbuch)

Mit C# können Sie ein Objekt oder eine Sammlung instanziieren und Memberzuweisungen in einer einzigen Anweisung durchführen.

## <a name="object-initializers"></a>Objektinitialisierer

Mit Objektinitialisierern können Sie allen verfügbaren Feldern oder Eigenschaften eines Objekts zum Erstellungszeitpunkt Werte zuweisen, ohne einen Konstruktor gefolgt von Zeilen mit Zuweisungsanweisungen aufrufen zu müssen. Mit der Objektinitialisierersyntax können Sie Argumente für einen Konstruktor angeben oder die Argumente (und Klammersyntax) weglassen.  Das folgende Beispiel zeigt, wie Sie einen Objektinitialisierer mit einem benannten Typ (`Cat`) verwenden und den parameterlosen Konstruktor aufrufen. Beachten Sie die Verwendung automatisch implementierter Eigenschaften in der `Cat`-Klasse. Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](auto-implemented-properties.md).  
  
[!code-csharp[ObjectInitializer1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#CatDeclaration)]  
[!code-csharp[ObjectInitializer1a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ObjectPropertyInitialization)]  

Die Syntax von Objektinitialisierern ermöglicht Ihnen die Erstellung einer Instanz und weist danach das neu erstellte Objekt mit seinen zugewiesenen Eigenschaften der Variable in der Zuweisung zu.

Ab C# 6 können die Objektinitialisierer nicht nur Felder und Eigenschaften zuweisen, sondern auch zusätzlich Indexer festlegen. Betrachten Sie diese grundlegende `Matrix`-Klasse:

[!code-csharp[ObjectInitializer2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixDeclaration)]  

Sie können die Identitätsmatrix mit folgendem Code initialisieren:

[!code-csharp[ObjectInitializer2a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixInitialization)]  

Alle zugänglichen Indexer, die zugängliche Setter enthalten, können unabhängig von der Anzahl und Typen der Argumente als einer der Ausdrücke in einem Objektinitialisierer verwendet werden. Die Indexargumente bilden die linke Seite der Zuweisung, und der Wert befindet sich auf der rechten Seite des Ausdrucks.  Diese sind beispielsweise alle gültig, wenn `IndexersExample` über die entsprechenden Indexer verfügt:

```csharp
var thing = new IndexersExample {
    name = "object one",
    [1] = '1',
    [2] = '4',
    [3] = '9',
    Size = Math.PI,
    ['C',4] = "Middle C"
}
```

Der `IndexersExample`-Typ muss für das Erstellen des obigen Codes die folgenden Member vorweisen:

```csharp
public string name;
public double Size { set { ... }; }
public char this[int i] { set { ... }; }
public string this[char c, int i] {  set { ... }; }
```

## <a name="object-initializers-with-anonymous-types"></a>Objektinitialisierer mit anonymen Typen

Obwohl Objektinitialisierer in jedem Kontext verwendet werden können, sind sie vor allem in LINQ-Abfrageausdrücken nützlich. Abfrageausdrücke verwenden häufig [anonyme Typen](./anonymous-types.md), die nur mit einem Objektinitialisierer initialisiert werden können, wie in der folgenden Deklaration veranschaulicht.  

```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```

Anonyme Typen ermöglichen der `select`-Klausel in einem LINQ-Abfrageausdruck, Objekte der ursprünglichen Sequenz in Objekte zu transformieren, deren Wert und Form sich vom Original unterscheiden können. Dies ist nützlich, wenn Sie nur einen Teil der Informationen aus jedem Objekt in einer Sequenz speichern möchten. Im folgenden Beispiel wird angenommen, dass ein Produktobjekt (`p`) viele Felder und Methoden enthält und dass Sie nur eine Sequenz von Objekten erstellen möchten, die den Produktnamen und den Einzelpreis enthalten.  
  
[!code-csharp[ObjectInitializer3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#AnonymousUse)]  

Wenn diese Abfrage ausgeführt wird, enthält die `productInfos`-Variable eine Sequenz von Objekten, auf die Sie über eine `foreach`-Anweisung, wie im folgenden Beispiel gezeigt, zugreifen können:  

```csharp
foreach(var p in productInfos){...}  
```

Jedes Objekt im neuen anonymen Typ weist zwei öffentliche Eigenschaften auf, die die gleichen Namen wie die Eigenschaften oder Felder im ursprünglichen Objekt erhalten. Sie können ein Feld auch umbenennen, wenn Sie einen anonymen Typ erstellen. Im folgenden Beispiel wird das `UnitPrice`-Feld in `Price` umbenannt.  

```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```

## <a name="collection-initializers"></a>Auflistungsinitialisierer

Mit Auflistungsinitialisierern können Sie einen oder mehrere Elementinitialisierer festlegen, wenn Sie einen Auflistungstyp initialisieren, der <xref:System.Collections.IEnumerable> implementiert und über `Add` mit der entsprechenden Signatur als Instanzmethode oder Erweiterungsmethode verfügt. Die Elementinitialisierer können ein einfacher Wert, ein Ausdruck oder ein Objektinitialisierer sein. Wenn Sie einen Sammlungsinitialisierer verwenden, ist es nicht nötig, selbst Aufrufe anzugeben, da der Compiler diese automatisch hinzufügt.  
  
Im folgenden Beispiel werden zwei einfache Sammlungsinitialisierer dargestellt:  

```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```

Der folgende Auflistungsinitialisierer verwendet Objektinitialisierer, um Objekte der `Cat`-Klasse, die in einem vorherigen Beispiel definiert wurden, zu initialisieren. Beachten Sie, dass die einzelnen Objektinitialisierer in geschweifte Klammern eingeschlossen und durch Kommas voneinander getrennt werden.  
  
[!code-csharp[ListInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitializer)]  
  
Sie können [NULL](../../language-reference/keywords/null.md) als ein Element in einem Auflistungsinitialisierer festlegen, wenn die `Add`-Methode der Auflistung dies zulässt.  
  
[!code-csharp[ListInitializerNull](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitialerWithNull)]  
  
 Sie können indizierte Elemente angeben, wenn die Sammlung das Lesen oder Schreiben von Indizierungen unterstützt.
  
[!code-csharp[DictionaryInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryIndexerInitializer)]  

Im vorherigen Beispiel wurde Code generiert, der die <xref:System.Collections.Generic.Dictionary%602.Item(%600)>-Eigenschaft zum Festlegen der Werte aufruft. Mit Versionen vor C# 6 können Sie Wörterbücher und andere assoziative Container mithilfe der folgenden Syntax initialisieren. Es gilt zu beachten, dass anstelle einer Indexersyntax mit Klammern und einer Zuweisung ein Objekt mit mehreren Werten verwendet wird:

[!code-csharp[DictionaryAddInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryAddInitializer)]  

Bei diesem Beispiel eines Initialisierers wird <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> aufgerufen, um die drei Elemente dem Wörterbuch hinzuzufügen. Diese zwei verschiedenen Arten des Initialisierens assoziativer Sammlungen verhalten sich aufgrund der vom Compiler generierten Methodenaufrufe etwas unterschiedlich. Beide Varianten unterstützen aber die `Dictionary`-Klasse. Bei anderen Typen wird abhängig von deren öffentlicher API möglicherweise nur eine der beiden unterstützt.

## <a name="examples"></a>Beispiele

Im folgenden Beispiel werden die Konzepte des Objekt- und Auflistungsinitialisierers verbunden.

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullExample)]  

Im folgenden Beispiel wird ein Objekt veranschaulicht, das <xref:System.Collections.IEnumerable> implementiert und eine `Add`-Methode mit mehreren Parametern enthält. Es wird ein Sammlungsinitialisierer mit mehreren Elementen pro Element in der Liste verwendet, die der Signatur der `Add`-Methode entsprechen.

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullListExample)]  

`Add`-Methoden können durch das Schlüsselwort `params` eine variable Anzahl von Argumenten akzeptieren, wie im folgenden Beispiel gezeigt wird. In diesem Beispiel wird die benutzerdefinierte Implementierung eines Indexers sowie die Initialisierung einer Sammlung mithilfe von Indizes veranschaulicht.

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullDictionaryInitializer)]  

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [LINQ in C#](../../linq/index.md)
- [Anonyme Typen](anonymous-types.md)
