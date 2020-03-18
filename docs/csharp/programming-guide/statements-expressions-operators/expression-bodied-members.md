---
title: Ausdruckskörpermember – C#-Programmierhandbuch
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: f212bb707d3dd2d4a7cc917d335a83cff01ed0cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75711986"
---
# <a name="expression-bodied-members-c-programming-guide"></a>Ausdruckskörpermember (C#-Programmierhandbuch)

Mit Ausdruckstextdefinitionen können Sie die Implementierung eines Members in einer sehr präzisen und lesbaren Form darstellen. Sie können eine Ausdruckstextdefinition verwenden, wann immer die Logik für einen unterstützten Member, z.B. eine Methode oder Eigenschaft, aus einem einzelnen Ausdruck besteht. Eine Ausdruckstextdefinition hat die folgende allgemeine Syntax:

```csharp
member => expression;
```

wobei *expression* ein gültiger Ausdruck ist.

Die Unterstützung für Ausdruckskörperdefinitionen wurde für Methoden und schreibgeschützte Eigenschaften in C# 6 eingeführt und in C# 7.0 erweitert. Ausdruckstextdefinitionen können mit Typmember verwendet werden, die in der folgenden Tabelle aufgeführt sind:

|Member  |Unterstützt ab... |
|---------|---------|
|[Methode](#methods)  |C# 6 |
|[Schreibgeschützte Eigenschaft](#read-only-properties)   |C# 6  |
|[Eigenschaft](#properties)  |C# 7.0 |
|[Konstruktor](#constructors)   |C# 7.0 |
|[Finalizer](#finalizers)     |C# 7.0 |
|[Indexer](#indexers)       |C# 7.0 |

## <a name="methods"></a>Methoden

Eine Ausdruckskörpermethode besteht aus einem einzelnen Ausdruck, der einen Wert zurückgibt, dessen Typ mit dem Rückgabetyp der Methode übereinstimmt bzw. für Methoden, die `void` zurückgeben, das einige Vorgänge ausführt. Beispielsweise enthalten Typen, die die <xref:System.Object.ToString%2A>-Methode außer Kraft setzen normalerweise einen einzelnen Ausdruck, der die Zeichenfolgendarstellung des aktuellen Objekts zurückgibt.

Das folgende Beispiel definiert eine `Person`-Klasse, die die <xref:System.Object.ToString%2A>-Methode mit einer Ausdruckstextmethode außer Kraft setzt. Es wird auch eine `DisplayName`-Methode definiert, die einen Namen für die Konsole anzeigt. Beachten Sie, dass das Schlüsselwort `return` nicht in der Ausdruckstextmethode `ToString` verwendet wird.

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

Weitere Informationen finden Sie unter [Methoden (C#-Programmierhandbuch)](../classes-and-structs/methods.md).

## <a name="read-only-properties"></a>Schreibgeschützte Eigenschaften

Ab C# 6 können Sie Ausdruckskörperdefinitionen zum Implementieren von schreibgeschützten Eigenschaften verwenden. Verwenden Sie hierzu die folgende Syntax:

```csharp
PropertyType PropertyName => expression;
```

Im folgenden Beispiel wird eine `Location`-Klasse definiert, deren schreibgeschützte Eigenschaft `Name` als Ausdruckskörperdefinition implementiert wird, die den Wert des privaten `locationName`-Felds zurückgibt:

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

Weitere Informationen zu Eigenschaften finden Sie unter [Eigenschaften (C#-Programmierhandbuch)](../classes-and-structs/properties.md).

## <a name="properties"></a>Eigenschaften

Ab C# 7.0 können Sie Ausdruckskörperdefinitionen zum Implementieren von `get`-Eigenschaften und `set`-Accessoren verwenden. Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht:

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

Weitere Informationen zu Eigenschaften finden Sie unter [Eigenschaften (C#-Programmierhandbuch)](../classes-and-structs/properties.md).

## <a name="constructors"></a>Konstruktoren

Eine Ausdruckstextdefinition für einen Konstruktor enthält in der Regel einen einzelnen Zuweisungsausdruck oder einen Methodenaufruf, der die Argumente des Konstruktors behandelt oder den Instanzzustand initialisiert.

Im folgenden Beispiel wird eine `Location`-Klasse definiert, deren Klassenkonstruktor einen einzelnen Zeichenfolgenparameter namens *name* enthält. Die Ausdruckstextdefinition weist das Argument für die Eigenschaft `Name` zu.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

Weitere Informationen finden Sie unter [Konstruktoren (C#-Programmierhandbuch)](../classes-and-structs/constructors.md).

## <a name="finalizers"></a>Finalizer

Eine Ausdruckstextdefinition für einen Finalizer enthält normalerweise Bereinigungsanweisungen, z.B. Anweisungen, die nicht verwaltete Ressourcen veröffentlichen.

Im folgenden Beispiel wird ein Finalizer definiert, der eine Ausdruckstextdefinition verwendet, um anzugeben, dass der Finalizer aufgerufen wurde.

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

Weitere Informationen finden Sie unter [Finalizer (C#-Programmierhandbuch)](../classes-and-structs/destructors.md).

## <a name="indexers"></a>Indexer

Genauso wie Eigenschaften bestehen die `get`- und `set`-Accessoren des Indexers aus Ausdruckstextdefinitionen, wenn der `get`-Accessor aus einem einzelnen Ausdruck besteht, der einen Wert zurückgibt, oder der `set`-Accessor führt eine einfache Zuweisung aus.

Im folgenden Beispiel wird eine Klasse namens `Sports` definiert, die ein internes <xref:System.String>-Array enthält, das aus den Namen von verschiedenen Sportarten besteht. Die `get`- und `set`-Accessoren des Indexers werden als Ausdruckstextdefinitionen implementiert.

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

Weitere Informationen finden Sie unter [Indexer (C#-Programmierhandbuch)](../indexers/index.md).
