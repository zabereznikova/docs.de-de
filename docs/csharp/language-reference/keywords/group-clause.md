---
title: group-Klausel – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- group
- group_CSharpKeyword
helpviewer_keywords:
- group keyword [C#]
- group clause [C#]
ms.assetid: c817242e-b12c-4baa-a57e-73ee138f34d1
ms.openlocfilehash: 806bc3de138ebae682d2e248593230c753eb7ba2
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422767"
---
# <a name="group-clause-c-reference"></a>group-Klausel (C#-Referenz)

Die `group`-Klausel gibt eine Sequenz von <xref:System.Linq.IGrouping%602>-Objekten zurück, die null oder mehr Elemente enthalten, die mit dem Schlüsselwert für die Gruppe übereinstimmen. Sie können z.B. eine Sequenz von Zeichenfolgen entsprechend des ersten Buchstaben in jeder Zeichenfolge gruppieren. In diesem Fall ist der erste Buchstabe der Schlüssel, verfügt über einen Typ [char](char.md) und wird in der `Key`-Eigenschaft jedes <xref:System.Linq.IGrouping%602>-Objekts gespeichert. Der Compiler leiten den Typ des Schlüssels her.

Sie können einen Abfrageausdruck mit einer `group`-Klausel beenden, so wie in folgendem Beispiel gezeigt:

[!code-csharp[cscsrefQueryKeywords#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#10)]

Wenn Sie zusätzliche Abfragevorgänge für jede Gruppe ausführen möchten, können Sie einen temporären Bezeichner mithilfe des kontextuellen Schlüsselworts [into](into.md) angeben. Wenn Sie `into` verwenden, müssen Sie mit der Abfrage fortfahren und sie entweder mit einer `select`-Anweisung oder einer anderen `group`-Klausel beenden, so wie im folgenden Auszug dargestellt:

[!code-csharp[cscsrefQueryKeywords#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#11)]

Weitere vollständige Gebrauchsbeispiele für `group` mit und ohne `into` sind im Abschnitt über Beispiele in diesem Artikel enthalten.

## <a name="enumerating-the-results-of-a-group-query"></a>Auflisten der Ergebnisse einer Gruppenabfrage

Da die <xref:System.Linq.IGrouping%602>-Objekte, die von einer `group`-Abfrage erstellt wurden, praktisch eine Liste von Listen sind, müssen Sie eine geschachtelte [foreach](foreach-in.md)-Schleife verwenden, um auf die Elemente in jeder Gruppe zuzugreifen. Die äußere Schleife durchläuft die Gruppenschlüssel, und die innere Schleife durchläuft jedes Element in der Gruppe selbst. Eine Gruppe kann womöglich über einen Schlüssel verfügen, jedoch nicht über Elemente. Nachstehend finden Sie die `foreach`-Schleife, die die Abfrage in den vorherigen Codebeispielen ausführen:

[!code-csharp[cscsrefQueryKeywords#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#12)]

## <a name="key-types"></a>Schlüsseltypen

Gruppenschlüssel können von jedem Typ sein, z.B. eine Zeichenfolge, ein integrierter numerischer Typ oder ein benutzerdefinierter benannter oder anonymer Typ.

### <a name="grouping-by-string"></a>Gruppieren nach Zeichenfolge

Das vorherige Codebeispiel verwendete einen `char`. Es hätte stattdessen einfach ein Zeichenfolgenschlüssel angegeben werden können, z.B. der vollständige letzte Name.

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

### <a name="grouping-by-bool"></a>Gruppieren nach Bool

Das folgende Beispiel zeigt die Verwendung eines booleschen Werts für einen Schlüssel, um die Ergebnisse in zwei Gruppen zu unterteilen. Beachten Sie, dass der Wert durch einen Unterausdruck in der `group`-Klausel erstellt wird.

[!code-csharp[cscsrefQueryKeywords#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#14)]

### <a name="grouping-by-numeric-range"></a>Gruppieren nach numerischen Bereich

Das nächste Beispiel verwendet einen Ausdruck, um einen nummerischen Gruppenschlüssel zu erstellen, der einen Prozentbereich darstellt. Beachten Sie, dass [let](let-clause.md) an einer geeigneten Position eingesetzt wird, um Ergebnisse eines Methodenaufrufs zu speichern, damit Sie die Methode nicht zweimal in der `group`-Klausel aufrufen müssen. Weitere Informationen zur sicheren Verwendung von Methoden in Abfrageausdrücken finden Sie unter [Vorgehensweise: Behandeln von Ausnahmen in Abfrageausdrücken](../../linq/handle-exceptions-in-query-expressions.md).

[!code-csharp[cscsrefQueryKeywords#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#15)]

### <a name="grouping-by-composite-keys"></a>Gruppieren nach zusammengesetzten Schlüsseln

Verwenden Sie einen zusammengesetzten Schlüssel, wenn Sie Elemente gemäß mehrerer Schlüssel gruppieren möchten. Sie erstellen einen zusammengesetzten Schlüssel, indem Sie einen anonymen Typ oder einen benannten Typ verwenden, um das Schlüsselelement aufzunehmen. Im folgenden Beispiel wird davon ausgegangen, dass eine `Person`-Klasse mit Elementen namens `surname` und `city` deklariert wurde. Die `group`-Klausel bewirkt, dass eine separate Gruppe für jede Gruppe von Personen mit dem gleichen Nachnamen und der gleichen Stadt erstellt wird.

```csharp
group person by new {name = person.surname, city = person.city};
```

Verwenden Sie einen benannten Typ, wenn Sie die Abfragevariable an eine andere Methode übergeben müssen. Erstellen Sie eine spezielle Klasse mit automatisch implementierten Eigenschaften für die Schlüssel, und setzen Sie anschließend die Methoden <xref:System.Object.Equals%2A> und <xref:System.Object.GetHashCode%2A> außer Kraft. Sie können auch eine Struktur verwenden. In diesem Fall müssen Sie diese Methoden nicht unbedingt außer Kraft setzen. Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften](../../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md) und [Vorgehensweise: Abfragen von Dateiduplikaten in einer Verzeichnisstruktur](../../programming-guide/concepts/linq/how-to-query-for-duplicate-files-in-a-directory-tree-linq.md). Der zweite Artikel enthält ein Codebeispiel, in dem dargestellt wird, wie ein zusammengesetzter Schlüssel mit einem benannten Typ verwendet wird.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt das Standardmuster für das Sortieren von Quelldaten in Gruppen, wenn keine zusätzliche Abfragelogik auf die Gruppen angewendet wird. Dies wird Gruppierung ohne Fortsetzung genannt. Die Elemente in einem Zeichenfolgenarray werden gemäß des ersten Buchstabens gruppiert. Das Ergebnis der Abfrage ist ein <xref:System.Linq.IGrouping%602>-Typ, der eine öffentliche `Key`-Eigenschaft des Typs `char` und eine <xref:System.Collections.Generic.IEnumerable%601>-Sammlung enthält, die jedes Element in der Gruppierung enthält.

Das Ergebnis einer `group`-Klausel ist eine Sequenz von Sequenzen. Verwenden Sie deshalb eine geschachtelte `foreach`-Schleife innerhalb der Schleife, die die Gruppenschlüssel durchläuft – so wie in folgendem Beispiel gezeigt – um auf die einzelnen Elemente innerhalb jeder zurückgegebenen Gruppe zuzugreifen.

[!code-csharp[cscsrefQueryKeywords#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#16)]

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie zusätzliche Logik auf die Gruppen ausgeführt wird, nachdem Sie diese erstellt haben, indem eine *Fortsetzung* mit `into` verwendet wird. Weitere Informationen finden Sie unter [into](into.md). Das folgende Beispiel fragt jede Gruppe ab, wobei nur die Gruppe ausgewählt werden soll, dessen Schlüsselwert ein Vokal ist.

[!code-csharp[cscsrefQueryKeywords#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#17)]

## <a name="remarks"></a>Anmerkungen

`group`-Klauseln werden zur Kompilierzeit in Aufrufe der <xref:System.Linq.Enumerable.GroupBy%2A>-Methode übersetzt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.IGrouping%602>
- <xref:System.Linq.Enumerable.GroupBy%2A>
- <xref:System.Linq.Enumerable.ThenBy%2A>
- <xref:System.Linq.Enumerable.ThenByDescending%2A>
- [Schlüsselwörter für Abfragen](query-keywords.md)
- [Language-Integrated Query (LINQ)](../../linq/index.md)
- [Erstellen einer geschachtelten Gruppe](../../linq/create-a-nested-group.md)
- [Gruppieren von Abfrageergebnissen](../../linq/group-query-results.md)
- [Ausführen einer Unterabfrage für eine Gruppierungsoperation](../../linq/perform-a-subquery-on-a-grouping-operation.md)
