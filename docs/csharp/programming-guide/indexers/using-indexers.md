---
title: Verwenden von Indexern – C#-Programmierhandbuch
ms.date: 07/15/2020
helpviewer_keywords:
- indexers [C#], about indexers
ms.assetid: df70e1a2-3ce3-4aba-ad80-4b2f3538699f
ms.openlocfilehash: e742e4dd5ea92ec3baf37c915e024e713022b7b6
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416240"
---
# <a name="using-indexers-c-programming-guide"></a>Verwenden von Indexern (C#-Programmierhandbuch)

Indexer sind ein syntaktisches Hilfsmittel, um Ihnen die Erstellung einer [Klasse](../../language-reference/keywords/class.md), [Struktur](../../language-reference/builtin-types/struct.md) oder [Schnittstelle](../../language-reference/keywords/interface.md) zu ermöglichen, auf die Clientanwendungen als Array zugreifen können. Der Compiler generiert die Eigenschaft `Item` (oder eine anders benannte Eigenschaft, wenn <xref:System.Runtime.CompilerServices.IndexerNameAttribute> vorhanden ist) und die entsprechenden Zugriffsmethoden. Indexer werden am häufigsten in Typen implementiert, deren Hauptzweck darin besteht, eine interne Auflistung oder ein Array zu kapseln. Angenommen, Sie verfügen beispielsweise über eine Klasse namens `TempRecord` zur Darstellung der Temperatur in Fahrenheit zu 10 verschiedenen Zeitpunkten während eines 24-stündigen Zeitraums. Die Klasse enthält das Array `temps` vom Typ `float[]` zum Speichern der Temperaturwerte. Durch die Implementierung eines Indexers in dieser Klasse können Clients auf die Temperaturen in einer `TempRecord`-Instanz als `float temp = tempRecord[4]` zugreifen, statt als `float temp = tempRecord.temps[4]`. Die Indexernotation vereinfacht nicht nur die Syntax für Clientanwendungen. Sie ermöglicht es auch anderen Entwicklern, die Klasse und deren Zweck intuitiver zu verstehen.

Um einen Indexer in einer Klasse oder Struktur zu deklarieren, verwenden Sie das [this](../../language-reference/keywords/this.md) -Schlüsselwort, wie im folgenden Beispiel gezeigt:

```csharp
// Indexer declaration
public int this[int index]
{
    // get and set accessors
}
```

> [!IMPORTANT]
> Beim Deklarieren eines Indexers wird automatisch eine Eigenschaft mit dem Namen `Item` für das Objekt generiert. Auf die Eigenschaft `Item` kann nicht direkt über den [Memberzugriffsausdruck](../../language-reference/operators/member-access-operators.md#member-access-expression-) der Instanz zugegriffen werden. Wenn Sie Ihre eigene Eigenschaft `Item` zu einem Objekt mit einem Indexer hinzufügen, wird außerdem der [Compilerfehler CS0102](../../misc/cs0102.md) angezeigt. Verwenden Sie <xref:System.Runtime.CompilerServices.IndexerNameAttribute>, und benennen Sie den Indexer wie unten beschrieben um, um diesen Fehler zu vermeiden.

## <a name="remarks"></a>Hinweise

Der Typ eines Indexers und der Typ seiner Parameter müssen zumindest dieselben Zugriffsmöglichkeiten bieten wie der Indexer selbst. Weitere Informationen zu den Zugriffsebenen finden Sie unter [Zugriffsmodifizierer](../../language-reference/keywords/access-modifiers.md).

Weitere Informationen zum Verwenden von Indexern mit einer Schnittstelle finden Sie unter [Schnittstellenindexer](./indexers-in-interfaces.md).

Die Signatur eines Indexers besteht aus der Anzahl und den Typen seiner formalen Parameter. Sie umfasst weder den Indexertyp noch die Namen der formalen Parameter. Wenn Sie mehrere Indexer in derselben Klasse deklarieren, müssen sie verschiedene Signaturen aufweisen.

Ein Indexerwert wird nicht als Variable klassifiziert. Aus diesem Grund können Sie keinen Indexerwert als [Ref](../../language-reference/keywords/ref.md)- oder [out](../../language-reference/keywords/out-parameter-modifier.md)-Parameter übergeben.

Um für den Indexer einen Namen anzugeben, den andere Sprachen verwenden können, verwenden Sie <xref:System.Runtime.CompilerServices.IndexerNameAttribute?displayProperty=nameWithType>, wie im folgenden Beispiel gezeigt:

```csharp
// Indexer declaration
[System.Runtime.CompilerServices.IndexerName("TheItem")]
public int this[int index]
{
    // get and set accessors
}
```

Dieser Indexer hat den Namen `TheItem`, da er vom Indexernamensattribut überschrieben wird. Standardmäßig ist der Indexername `Item`.

## <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die Deklaration eines öffentlichen Arrayfelds, `temps`, und eines Indexers dargestellt. Der Indexer ermöglicht den direkten Zugriff auf die Instanz `tempRecord[i]`. Als Alternative zur Verwendung des Indexers, kann das Array als [öffentliches](../../language-reference/keywords/public.md) Mitglied deklariert und direkt auf dessen Mitglieder, `tempRecord.temps[i]`, zugegriffen werden.

:::code language="csharp" source="snippets/Temperatures/TempRecord.cs":::

Beachten Sie, dass, wenn der Zugriff eines Indexers, z.B. in einer `Console.Write`-Anweisung ausgewertet wird, der [get](../../language-reference/keywords/get.md)-Accessor aufgerufen wird. Wenn kein `get`-Accessor vorhanden ist, tritt deshalb ein Kompilierzeitfehler auf.

:::code language="csharp" source="snippets/Temperatures/Program.cs":::

## <a name="indexing-using-other-values"></a>Indizieren mit anderen Werten

C# beschränkt den Indexer-Parametertyp nicht auf Integer. Beispielsweise kann es sinnvoll sein, eine Zeichenfolge mit einem Indexer zu verwenden. Ein solcher Indexer kann implementiert werden, indem die Zeichenfolge in der Auflistung gesucht und der richtige Wert zurückgegeben wird. Da Zugriffsmethoden überladen werden können, können die Zeichenfolgen- und die Integer-Version gleichzeitig vorhanden sein.

## <a name="example-2"></a>Beispiel 2

Das folgende Beispiel deklariert eine Klasse, die die Wochentage speichert. Ein `get`-Accessor akzeptiert eine Zeichenfolge – den Namen eines Tages – und gibt den entsprechenden Integer-Wert zurück. „Sunday“ gibt beispielsweise 0 zurück, „Monday“ 1 usw.

:::code language="csharp" source="snippets/StringIndexers/DayCollection.cs":::

### <a name="consuming-example-2"></a>Verwendungsbeispiel 2

:::code language="csharp" source="snippets/StringIndexers/Program.cs":::

## <a name="example-3"></a>Beispiel 3

Im folgenden Beispiel wird eine Klasse deklariert, die die Wochentage mithilfe der Enumeration <xref:System.DayOfWeek?displayProperty=fullName> speichert. Eine `get`-Zugriffsmethode akzeptiert `DayOfWeek` (den Wert für einen Tag) und gibt den entsprechenden Integer-Wert zurück. Bei `DayOfWeek.Sunday` wird beispielsweise 0 zurückgegeben, bei `DayOfWeek.Monday` 1 und so weiter.

:::code language="csharp" source="snippets/DayOfWeekIndexers/DayOfWeekCollection.cs":::

### <a name="consuming-example-3"></a>Verwendungsbeispiel 3

:::code language="csharp" source="snippets/DayOfWeekIndexers/Program.cs":::

## <a name="robust-programming"></a>Stabile Programmierung

Es gibt zwei grundlegende Möglichkeiten, mit denen die Sicherheit und die Zuverlässigkeit von Indexern verbessert werden kann:

- Integrieren Sie irgendeine Form von Fehlerbehandlungsstrategie, für den Fall, dass Clientcode in einem ungültigen Indexwert übergeben wird. Im ersten Beispiel weiter oben in diesem Thema stellt die TempRecord-Klasse eine Length-Eigenschaft bereit, die dem Clientcode ermöglicht, die Eingabe vor der Übergabe an den Indexer zu überprüfen. Sie können den Fehlerbehandlungscode auch in den Indexer selbst einfügen. Achten Sie darauf alle Ausnahmen, die Sie innerhalb eines Indexeraccessors auslösen, für Benutzer zu dokumentieren.

- Schränken Sie den Zugriff auf die [get](../../language-reference/keywords/get.md)- und [set](../../language-reference/keywords/set.md)-Accessors so weit wie möglich ein. Dies ist insbesondere wichtig für den `set`-Accessor. Weitere Informationen finden Sie unter [Einschränken des Accessorzugriffs](../classes-and-structs/restricting-accessor-accessibility.md).

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Indexer](./index.md)
- [Eigenschaften](../classes-and-structs/properties.md)
