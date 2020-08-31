---
title: 'Gewusst wie: Hinzufügen von benutzerdefinierten Methoden für LINQ-Abfragen'
ms.date: 08/28/2020
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
ms.openlocfilehash: 7d38a45263135fa10dc53dc0d09b8129838e78e6
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89117778"
---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a>Gewusst wie: Hinzufügen von benutzerdefinierten Methoden für LINQ-Abfragen (Visual Basic)

Sie erweitern den Satz von Methoden, die Sie für LINQ-Abfragen verwenden, indem Sie der-Schnittstelle Erweiterungs Methoden hinzufügen <xref:System.Collections.Generic.IEnumerable%601> . Beispielsweise können Sie zusätzlich zu den standardmäßigen durchschnittlichen oder maximalen Vorgängen eine benutzerdefinierte Aggregat Methode erstellen, um einen einzelnen Wert aus einer Sequenz von Werten zu berechnen. Außerdem erstellen Sie eine Methode, die als benutzerdefinierter Filter oder eine bestimmte Datentransformation für eine Sequenz von Werten funktioniert und eine neue Sequenz zurückgibt. Beispiele für solche Methoden sind <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Reverse%2A>.

Beim Erweitern der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle können Sie die benutzerdefinierten Methoden auf jede aufzählbare Auflistung anwenden. Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../language-features/procedures/extension-methods.md).

## <a name="adding-an-aggregate-method"></a>Hinzufügen einer Aggregat Methode

Eine aggregierte Methode berechnet einen einzelnen Wert aus einer Gruppe von Werten. LINQ stellt mehrere Aggregatmethoden bereit, einschließlich <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> und <xref:System.Linq.Enumerable.Max%2A>. Sie können Ihre eigene Aggregatmethode erstellen, indem Sie der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle eine Erweiterungsmethode hinzufügen.

Im folgenden Codebeispiel wird veranschaulicht, wie eine Erweiterungsmethode namens `Median` erstellt wird, um einen Median für eine Zahlensequenz des Typs `double` zu berechnen.

:::code language="vb" source="./snippets/LinqExtension.vb" :::

Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Aggregatmethoden aus der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle aufrufen.

> [!NOTE]
> In Visual Basic können Sie entweder einen Methoden aufrufoder eine Standard Abfrage Syntax für die- `Aggregate` oder- `Group By` Klausel verwenden. Weitere Informationen finden Sie unter [Aggregat Klausel](../../../language-reference/queries/aggregate-clause.md) und [Group By-Klausel](../../../language-reference/queries/group-by-clause.md).

Im folgenden Codebeispiel wird die Verwendung der `Median`-Methode für ein Array des Typs `double` veranschaulicht.

:::code language="vb" source="./snippets/Program.vb" ID="MedianUsage":::

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>Überladen einer Aggregat Methode, um verschiedene Typen zu akzeptieren

Sie können die Aggregatmethode überladen, sodass diese Sequenzen verschiedener Typen akzeptiert. Die Standardmethode ist die Erstellung einer Überladung für jeden Typ. Ein anderer Ansatz ist das Erstellen einer Überladung, die einen generischen Typ annimmt und diesen mit einem Delegaten in einen bestimmten Typ konvertiert. Sie können auch beide Methoden kombinieren.

#### <a name="to-create-an-overload-for-each-type"></a>So erstellen Sie eine Überladung für jeden Typ

Sie können eine bestimmte Überladung für jeden Typ erstellen, den Sie unterstützen möchten. Im folgenden Codebeispiel wird eine Überladung der `Median`-Methode für den `integer`-Typ veranschaulicht.

:::code language="vb" source="./snippets/OtherExtensions.vb" ID="IntOverload":::

Sie können nun die `Median`-Überladungen für die `integer`- und `double`-Typen aufrufen, so wie im folgenden Code gezeigt:

:::code language="vb" source="./snippets/Program.vb" ID="OverloadUsage":::

#### <a name="to-create-a-generic-overload"></a>So erstellen Sie eine generische Überladung

Sie können auch eine Überladung erstellen, die eine Sequenz generischer Objekte akzeptiert. Diese Überladung nimmt einen Delegaten als Parameter und verwendet ihn, um eine Sequenz von Objekten eines generischen Typs in einen bestimmten Typ zu konvertieren.

Der folgende Code zeigt eine Überladung der `Median`-Methode, die den <xref:System.Func%602>-Delegaten als Parameter akzeptiert. Dieser Delegat nimmt ein Objekt des generischen Typs an `T` und gibt ein Objekt vom Typ zurück `double` .

:::code language="vb" source="./snippets/OtherExtensions.vb" ID="GenericOverload":::

Sie können nun die `Median`-Methode für eine Sequenz von Objekten beliebigen Typs aufrufen. Wenn der Typ nicht über eine eigene Methodenüberladung verfügt, müssen sie einen Delegatenparameter übergeben. In Visual Basic können Sie einen Lambda Ausdruck zu diesem Zweck verwenden. Wenn Sie `Aggregate` `Group By` anstelle des Methoden Aufrufes auch die-oder-Klausel verwenden, können Sie einen beliebigen Wert oder Ausdruck übergeben, der im Gültigkeitsbereich dieser Klausel enthalten ist.

Der folgende Beispielcode veranschaulicht, wie eine `Median`-Methode für ein Array aus ganzen Zahlen und ein Array aus Zeichenfolgen aufgerufen wird. Für Zeichenfolgen wird der Median für die Längen der Zeichenfolgen im Array berechnet. Das Beispiel zeigt, wie der Delegatparameter `Median` an die <xref:System.Func%602>-Methode für jeden Fall übergeben wird.

:::code language="vb" source="./snippets/Program.vb" ID="GenericUsage":::

## <a name="adding-a-method-that-returns-a-collection"></a>Hinzufügen einer Methode, die eine Auflistung zurückgibt

Sie können die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> mit einer benutzerdefinierten Abfragemethode erweitern, die eine Sequenz von Werten zurückgibt. In diesem Fall muss die Methode eine Auflistung des Typs <xref:System.Collections.Generic.IEnumerable%601> zurückgeben. Solche Methoden können verwendet werden, um Filter oder Datentransformationen auf eine Sequenz von Werten anzuwenden.

Das folgende Beispiel zeigt, wie eine Erweiterungsmethode mit dem Namen `AlternateElements` erstellt wird, die jedes andere Element in einer Auflistung zurückgibt, beginnend mit dem ersten Element.

:::code language="vb" source="./snippets/OtherExtensions.vb" ID="SequenceElement":::

Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Methoden aus der Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> aufrufen, so wie im folgenden Code dargestellt:

:::code language="vb" source="./snippets/Program.vb" ID="SequenceUsage":::

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic.IEnumerable%601>
- [Erweiterungsmethoden](../../language-features/procedures/extension-methods.md)
