---
title: 'Vorgehensweise: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (C#)'
description: Hier erfahren Sie, wie Sie die Syntax von LINQ-Abfragen erweitern, indem Sie Erweiterungsmethoden zur IEnumerable<T>-Schnittstelle in C# hinzufügen.
ms.date: 08/26/2020
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: 768882fce40a2fc6e018f24c8928341e7c65bc4b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122424"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a>Vorgehensweise: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (C#)

Sie erweitern die Methoden, die Sie für LINQ-Abfragen durch Hinzufügen von Erweiterungsmethoden zur <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle verwenden. Zusätzlich zu den durchschnittlichen oder maximalen Standardvorgängen erstellen Sie eine benutzerdefinierte Aggregatmethode, um einen einzelnen Wert aus einer Sequenz von Werten zu berechnen. Sie erstellen auch eine Methode, die als benutzerdefinierter Filter oder spezifische Datentransformation für eine Sequenz von Werten agiert und eine neue Sequenz zurückgibt. Beispiele für solche Methoden sind <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Reverse%2A>.

Beim Erweitern der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle können Sie die benutzerdefinierten Methoden auf jede aufzählbare Auflistung anwenden. Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../classes-and-structs/extension-methods.md).

## <a name="adding-an-aggregate-method"></a>Hinzufügen einer Aggregatmethode

Eine aggregierte Methode berechnet einen einzelnen Wert aus einer Gruppe von Werten. LINQ stellt mehrere Aggregatmethoden bereit, einschließlich <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> und <xref:System.Linq.Enumerable.Max%2A>. Sie können Ihre eigene Aggregatmethode erstellen, indem Sie der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle eine Erweiterungsmethode hinzufügen.

Im folgenden Codebeispiel wird veranschaulicht, wie eine Erweiterungsmethode namens `Median` erstellt wird, um einen Median für eine Zahlensequenz des Typs `double` zu berechnen.

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="LinqExtensionClass":::

Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Aggregatmethoden aus der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle aufrufen.

Im folgenden Codebeispiel wird die Verwendung der `Median`-Methode für ein Array des Typs `double` veranschaulicht.

:::code language="csharp" source="./snippets/Program.cs" ID="MedianUsage":::

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>Überladen einer Aggregatmethode zum Akzeptieren verschiedener Typen

Sie können die Aggregatmethode überladen, sodass diese Sequenzen verschiedener Typen akzeptiert. Die Standardmethode ist die Erstellung einer Überladung für jeden Typ. Ein anderer Ansatz ist das Erstellen einer Überladung, die einen generischen Typ annimmt und diesen mit einem Delegaten in einen bestimmten Typ konvertiert. Sie können auch beide Methoden kombinieren.

#### <a name="to-create-an-overload-for-each-type"></a>So erstellen Sie eine Überladung für jeden Typ

Sie können eine bestimmte Überladung für jeden Typ erstellen, den Sie unterstützen möchten. Im folgenden Codebeispiel wird eine Überladung der `Median`-Methode für den `int`-Typ veranschaulicht.

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="IntOverload":::

Sie können nun die `Median`-Überladungen für die `integer`- und `double`-Typen aufrufen, so wie im folgenden Code gezeigt:

:::code language="csharp" source="./snippets/Program.cs" ID="OverloadUsage":::

#### <a name="to-create-a-generic-overload"></a>So erstellen Sie eine generische Überladung

Sie können auch eine Überladung erstellen, die eine Sequenz generischer Objekte akzeptiert. Diese Überladung nimmt einen Delegaten als Parameter und verwendet ihn, um eine Sequenz von Objekten eines generischen Typs in einen bestimmten Typ zu konvertieren.

Der folgende Code zeigt eine Überladung der `Median`-Methode, die den <xref:System.Func%602>-Delegaten als Parameter akzeptiert. Dieser Delegat übernimmt ein Objekt des generischen Typs „T“ und gibt ein Objekt vom Typ `double` zurück.

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="GenericOverload":::

Sie können nun die `Median`-Methode für eine Sequenz von Objekten beliebigen Typs aufrufen. Wenn der Typ nicht über eine eigene Methodenüberladung verfügt, müssen Sie einen Delegatenparameter übergeben. In C# können Sie zu diesem Zweck einen Lambdaausdruck verwenden. Wenn Sie die `Aggregate`- oder `Group By`-Klausel anstatt des Methodenaufrufs verwenden, können Sie auch einen beliebigen Wert oder Ausdruck übergeben, der im Bereich dieser Klausel vorhanden ist. Diese Methode ist nur in Visual Basic verfügbar.

Der folgende Beispielcode veranschaulicht, wie eine `Median`-Methode für ein Array aus ganzen Zahlen und ein Array aus Zeichenfolgen aufgerufen wird. Für Zeichenfolgen wird der Median für die Längen der Zeichenfolgen im Array berechnet. Das Beispiel zeigt, wie der Delegatparameter `Median` an die <xref:System.Func%602>-Methode für jeden Fall übergeben wird.

:::code language="csharp" source="./snippets/Program.cs" ID="GenericUsage":::

## <a name="adding-a-method-that-returns-a-sequence"></a>Hinzufügen einer Methode, die eine Sequenz zurückgibt

Sie können die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> mit einer benutzerdefinierten Abfragemethode erweitern, die eine Sequenz von Werten zurückgibt. In diesem Fall muss die Methode eine Auflistung des Typs <xref:System.Collections.Generic.IEnumerable%601> zurückgeben. Solche Methoden können verwendet werden, um Filter oder Datentransformationen auf eine Sequenz von Werten anzuwenden.

Das folgende Beispiel zeigt, wie eine Erweiterungsmethode mit dem Namen `AlternateElements` erstellt wird, die jedes andere Element in einer Auflistung zurückgibt, beginnend mit dem ersten Element.

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="SequenceElement":::

Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Methoden aus der Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> aufrufen, so wie im folgenden Code dargestellt:

:::code language="csharp" source="./snippets/Program.cs" ID="SequenceUsage":::

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic.IEnumerable%601>
- [Erweiterungsmethoden](../../classes-and-structs/extension-methods.md)
