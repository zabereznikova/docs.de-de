---
title: Ausdruckskörpermember – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36f71352dca584c107af4f45850ce21bb016ba01
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238116"
---
# <a name="expression-bodied-members-c-programming-guide"></a>Ausdruckskörpermember (C#-Programmierhandbuch)
Mit Ausdruckstextdefinitionen können Sie die Implementierung eines Members in einer sehr präzisen und lesbaren Form darstellen. Sie können eine Ausdruckstextdefinition verwenden, wann immer die Logik für einen unterstützten Member, z.B. eine Methode oder Eigenschaft, aus einem einzelnen Ausdruck besteht. Eine Ausdruckstextdefinition hat die folgende allgemeine Syntax:

```csharp
member => expression;
```

wobei *expression* ein gültiger Ausdruck ist. 

Die Unterstützung für Ausdruckskörperdefinitionen wurde für Methoden und Get-Eigenschaftenzugriffsmethoden in C# 6 eingeführt und in C# 7.0 erweitert. Ausdruckstextdefinitionen können mit Typmember verwendet werden, die in der folgenden Tabelle aufgeführt sind: 

|Member  |Unterstützt ab... |
|---------|---------|
|[Methode](#methods)  |C# 6 |
|[Konstruktor](#constructors)   |C# 7.0 |
|[Finalizer](#finalizers)     |C# 7.0 |
|[Get-Methode der Eigenschaft](#property-get-statements)  |C# 6 |
|[Set-Methode der Eigenschaft](#property-set-statements)  |C# 7.0 |
|[Indexer](#indexers)       |C# 7.0 |

## <a name="methods"></a>Methoden

Eine Ausdruckskörpermethode besteht aus einem einzelnen Ausdruck, der einen Wert zurückgibt, dessen Typ mit dem Rückgabetyp der Methode übereinstimmt bzw. für Methoden, die `void` zurückgeben, das einige Vorgänge ausführt. Beispielsweise enthalten Typen, die die <xref:System.Object.ToString%2A>-Methode außer Kraft setzen normalerweise einen einzelnen Ausdruck, der die Zeichenfolgendarstellung des aktuellen Objekts zurückgibt. 

Das folgende Beispiel definiert eine `Person`-Klasse, die die <xref:System.Object.ToString%2A>-Methode mit einer Ausdruckstextmethode außer Kraft setzt. Es wird auch eine `DisplayName`-Methode definiert, die einen Namen für die Konsole anzeigt. Beachten Sie, dass das Schlüsselwort `return` nicht in der Ausdruckstextmethode `ToString` verwendet wird.

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

Weitere Informationen finden Sie unter [Methoden (C#-Programmierhandbuch)](../classes-and-structs/methods.md).
 
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

## <a name="property-get-statements"></a>Anweisungen der Get-Methode der Eigenschaft

Wenn Sie selbst einen Accessor der Get-Methode der Eigenschaft implementieren möchten, können Sie eine Ausdruckstextdefinition für Eigenschaftswerte verwenden, die den Eigenschaftswert einfach zurückgeben. Beachten sie, dass die Anweisung `return` nicht verwendet wird.

Im folgenden Beispiel wird eine `Location.Name`-Anweisung definiert, deren Accessor der Get-Methode der Eigenschaft den Wert des privaten `locationName`-Felds zurückgibt, das hinter der Eigenschaft liegt. 

[!code-csharp[expression-bodied-property-getter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

Schreibgeschützte Eigenschaften, die eine Ausdruckstextdefinition verwenden, können ohne explizite `set`-Anweisung implementiert werden. Die Syntax lautet:

```csharp
PropertyName => returnValue;
```

Das folgende Beispiel definiert eine `Location`-Klasse, deren schreibgeschützte Eigenschaft `Name` als Ausdruckstextdefinition implementiert wird, die den Wert des privaten `locationName`-Felds zurückgibt.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

Weitere Informationen finden Sie unter [Eigenschaften (C#-Programmierhandbuch)](../classes-and-structs/properties.md).

## <a name="property-set-statements"></a>Anweisungen der Set-Methode der Eigenschaft

Wenn Sie selbst einen Accessor der Set-Methode der Eigenschaft implementieren möchten, können Sie eine Ausdruckstextdefinition für einen Ausdruck mit nur einer Zeile verwenden, der dem Feld einen Wert zuweist, das hinter der Eigenschaft steht.

Im folgenden Beispiel wird eine `Location.Name`-Eigenschaft definiert, deren Set-Methode der Eigenschaft das Eingabeargument dem privaten `locationName`-Feld zuweist, das hinter der Eigenschaft steht.

[!code-csharp[expression-bodied-property-setter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

Weitere Informationen finden Sie unter [Eigenschaften (C#-Programmierhandbuch)](../classes-and-structs/properties.md).

## <a name="indexers"></a>Indexer

Genauso wie Eigenschaften bestehen die Accessoren der Get- und Set-Methode des Indexers aus Ausdruckstextdefinitionen, wenn der Get-Accessor aus einer einzelnen Anweisung besteht, die einen Wert zurückgibt, oder der Set-Accessor führt eine einfache Zuweisung aus.

Im folgenden Beispiel wird eine Klasse namens `Sports` definiert, die ein internes <xref:System.String>-Array enthält, das aus den Namen von verschiedenen Sportarten besteht. Die Get- und Set-Accessoren des Indexers werden als Ausdruckstextdefinitionen implementiert.

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)] 

Weitere Informationen finden Sie unter [Indexer (C#-Programmierhandbuch)](../indexers/index.md).

