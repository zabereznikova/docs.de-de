---
title: Zusammenführen von DataSet-Inhalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e9309a-3ebb-4a9c-9d78-21c4e2bafc5b
ms.openlocfilehash: abc9183666602a7ef369e690e3ae499f8c7b8b11
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784398"
---
# <a name="merging-dataset-contents"></a>Zusammenführen von DataSet-Inhalten

Sie können die <xref:System.Data.DataSet.Merge%2A>-Methode verwenden, um den Inhalt eines <xref:System.Data.DataSet>-, <xref:System.Data.DataTable>- oder <xref:System.Data.DataRow>-Arrays in einem vorhandenen `DataSet` zusammenzuführen. Wie die neuen Daten in einem vorhandenen `DataSet` zusammengeführt werden, hängt von mehreren Faktoren und Optionen ab.

## <a name="primary-keys"></a>Primärschlüssel

Wenn die Tabelle, die neue Daten und Schemas aus einem Merge empfängt, einen Primärschlüssel besitzt, werden die neuen Zeilen aus den empfangenen Daten mit vorhandenen Zeilen verglichen, die dieselben <xref:System.Data.DataRowVersion.Original>-Primärschlüsselwerte besitzen wie die empfangenen Daten. Wenn die Spalten aus dem empfangenen Schema mit denen des vorhandenen Schemas übereinstimmen, werden die Daten in den vorhandenen Zeilen geändert. Spalten, die nicht mit dem vorhandenen Schema übereinstimmen, werden, abhängig vom Wert des <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A>-Parameters, entweder ignoriert oder hinzugefügt. Neue Zeilen mit Primärschlüsselwerten, die nicht mit vorhandenen Zeilen übereinstimmen, werden an die vorhandene Tabelle angehängt.

Wenn empfangene oder vorhandene Zeilen den Zeilenstatus <xref:System.Data.DataRowState.Added> aufweisen, werden ihre Primärschlüsselwerte mit dem <xref:System.Data.DataRowVersion.Current>-Primärschlüsselwert der `Added`-Zeile verglichen, weil es keine `Original`-Zeilenversion gibt.

Wenn eine empfangene Tabelle und eine vorhandene Tabelle eine Spalte mit demselben Namen, aber unterschiedlichen Datentypen enthalten, wird eine Ausnahme generiert, und das <xref:System.Data.DataSet.MergeFailed>-Ereignis des `DataSet` wird ausgelöst. Wenn sowohl eine empfangene Tabelle als auch eine vorhandene Tabelle definierte Primärschlüssel besitzen, die Primärschlüssel aber für verschiedene Spalten gelten, wird eine Ausnahme generiert und das `MergeFailed`-Ereignis des `DataSet` ausgelöst.

Wenn die Tabelle, die neue Daten aus einer Zusammenführung empfängt, keinen Primärschlüssel besitzt, können die neuen Zeilen aus den empfangenen Daten nicht mit vorhandenen Zeilen in der Tabelle verglichen werden. Die Zeilen werden dann stattdessen an die vorhandene Tabelle angehängt.

## <a name="table-names-and-namespaces"></a>Tabellennamen und Namespaces

<xref:System.Data.DataTable>-Objekten kann optional ein <xref:System.Data.DataTable.Namespace%2A>-Eigenschaftswert zugewiesen werden. Wenn <xref:System.Data.DataTable.Namespace%2A>-Werte zugewiesen werden, kann ein <xref:System.Data.DataSet> mehrere <xref:System.Data.DataTable>-Objekte mit demselben <xref:System.Data.DataTable.TableName%2A>-Wert enthalten. Bei Merges werden sowohl der <xref:System.Data.DataTable.TableName%2A> als auch der <xref:System.Data.DataTable.Namespace%2A> verwendet, um das Ziel des Merge anzugeben. Wenn kein <xref:System.Data.DataTable.Namespace%2A> zugewiesen wurde, wird zur Angabe des Ziels nur der <xref:System.Data.DataTable.TableName%2A> verwendet.

> [!NOTE]
> Dieses Verhalten ist in .NET Framework 2.0 neu. In Version 1.1 wurden Namespaces zwar unterstützt, bei Merges wurden sie aber ignoriert. Aus diesem Grund hängt das Verhalten eines <xref:System.Data.DataSet>, das <xref:System.Data.DataTable.Namespace%2A>-Eigenschaftswerte verwendet, von der jeweils verwendeten .NET Framework-Version ab. Nehmen wir z. B. an, es gibt zwei `DataSets`, die `DataTables` mit identischen <xref:System.Data.DataTable.TableName%2A>-Eigenschaftswerten, aber verschiedenen <xref:System.Data.DataTable.Namespace%2A>-Eigenschaftswerten enthalten. In .NET Framework 1.1 werden die verschiedenen <xref:System.Data.DataTable.Namespace%2A>-Namen beim Zusammenführen der beiden <xref:System.Data.DataSet>-Objekte ignoriert. Ab Version 2.0 hingegen werden beim Zusammenführen zwei neue `DataTables` im Ziel-<xref:System.Data.DataSet> erstellt. Auf die ursprünglichen `DataTables` hat die Zusammenführung keine Auswirkung.

## <a name="preservechanges"></a>PreserveChanges

Wenn Sie ein `DataSet`-, ein `DataTable`- oder ein `DataRow`-Array an die `Merge`-Methode übergeben, können Sie mit optionalen Parametern angeben, ob Änderungen im vorhandenen `DataSet` beibehalten werden sollen und wie die neuen Schemaelemente in den empfangenen Daten zu behandeln sind. Der erste dieser Parameter nach den empfangenen Daten ist ein Boolean-Flag, <xref:System.Data.LoadOption.PreserveChanges>, das angibt, ob die Änderungen im vorhandenen `DataSet` beibehalten werden sollen. Wenn das `PreserveChanges`-Flag auf `true` festgelegt ist, werden vorhandene Werte in der `Current`-Zeilenversion der vorhandenen Zeile nicht durch die empfangenen Werte überschrieben. Wenn das `PreserveChanges`-Flag auf `false` festgelegt ist, werden die vorhandenen Werte in der `Current`-Zeilenversion der vorhandenen Zeile mit den empfangenen Werten überschrieben. Wenn für das `PreserveChanges`-Flag nichts angegeben wird, wird es standardmäßig auf `false` festgelegt. Weitere Informationen zu Zeilen Versionen finden Sie unter [Zeilen Status und Zeilen Versionen](row-states-and-row-versions.md).

Wenn das `PreserveChanges`-Flag auf `true` festgelegt ist, werden die Daten der vorhandenen Zeile in der <xref:System.Data.DataRowVersion.Current>-Zeilenversion der vorhandenen Zeile beibehalten, während die Daten aus der <xref:System.Data.DataRowVersion.Original>-Zeilenversion der vorhandenen Zeile durch die Daten aus der `Original`-Zeilenversion der empfangenen Zeile überschrieben werden. Der <xref:System.Data.DataRow.RowState%2A> der vorhandenen Zeile wird auf <xref:System.Data.DataRowState.Modified> festgelegt. Beachten Sie folgende Ausnahmen:

- Wenn der `RowState` der vorhandenen Zeile `Deleted` lautet, bleibt dieser `RowState` als `Deleted` erhalten und wird nicht auf `Modified` festgelegt. In diesem Fall werden die Daten aus der empfangenen Zeile immer noch in der Zeilenversion `Original` der vorhandenen Zeile gespeichert, wobei die Zeilenversion `Original` der vorhandenen Zeile überschrieben wird (es sei denn, der `RowState` der empfangenen Zeile lautet `Added`).

- Wenn der `RowState` der empfangenen Zeile `Added` lautet, werden die Daten aus der `Original`-Zeilenversion der vorhandenen Zeile nicht mit den Daten der empfangenen Zeile überschrieben, weil die empfangene Zeile keine `Original`-Zeilenversion besitzt.

Wenn das `PreserveChanges`-Flag auf `false` festgelegt ist, werden sowohl die `Current`-Zeilenversion als auch die `Original`-Zeilenversion in der vorhandenen Zeile durch die Daten der empfangenen Zeile überschrieben, und der `RowState` der vorhandenen Zeile wird auf den `RowState` der empfangenen Zeile festgelegt. Beachten Sie folgende Ausnahmen:

- Wenn die empfangene Zeile den `RowState``Unchanged` und die vorhandene Zeile den `RowState``Modified`, `Deleted` oder `Added` besitzt, wird der `RowState` der vorhandenen Zeile auf `Modified` festgelegt.

- Wenn die empfangene Zeile den `RowState``Added` und die vorhandene Zeile den `RowState``Unchanged`, `Modified` oder `Deleted` besitzt, wird der `RowState` der vorhandenen Zeile auf `Modified` festgelegt. Außerdem werden die Daten der `Original`-Zeilenversion der vorhandenen Zeile nicht durch die Daten der empfangenen Zeile überschrieben, weil die empfangene Zeile keine `Original`-Zeilenversion besitzt.

## <a name="missingschemaaction"></a>MissingSchemaAction

Mit dem optionalen <xref:System.Data.MissingSchemaAction>-Parameter der `Merge`-Methode können Sie angeben, wie die `Merge`-Methode Schemaelemente in den empfangenen Daten behandeln soll, die nicht Teil des bestehenden `DataSet` sind.

Eine Beschreibung der Optionen für `MissingSchemaAction` finden Sie in der folgenden Tabelle.

|MissingSchemaAction-Option|Beschreibung|
|--------------------------------|-----------------|
|<xref:System.Data.MissingSchemaAction.Add>|Fügt dem `DataSet` die neuen Schemainformationen hinzu und füllt die neuen Spalten mit den empfangenen Werten auf. Dies ist die Standardeinstellung.|
|<xref:System.Data.MissingSchemaAction.AddWithKey>|Fügt dem `DataSet` die neuen Schema- und Primärschlüsselinformationen hinzu und füllt die neuen Spalten mit den empfangenen Werten auf.|
|<xref:System.Data.MissingSchemaAction.Error>|Auslösen einer Ausnahme, wenn nicht übereinstimmende Schemainformationen gefunden werden.|
|<xref:System.Data.MissingSchemaAction.Ignore>|Ignorieren der neuen Schemainformationen.|

## <a name="constraints"></a>Einschränkungen

Bei der `Merge`-Methode werden Einschränkungen erst überprüft, wenn dem vorhandenen `DataSet` alle neuen Daten hinzugefügt wurden. Sobald die Daten hinzugefügt wurden, werden die Einschränkungen für die aktuellen Werte im `DataSet` erzwungen. Sie müssen sicherstellen, dass Ihr Code die Behandlung von Ausnahmen ermöglicht, die aufgrund von Einschränkungsverletzungen ausgelöst werden.

Nehmen wir einmal an, eine vorhandene Zeile in einem `DataSet` ist eine Zeile mit dem `Unchanged`-Zeilenstatus und dem Primärschlüsselwert 1. Beim Zusammenführen mit einer empfangenen Zeile mit dem `Modified`-Zeilenstatus und dem `Original`-Primärschlüsselwert 2 sowie dem `Current`-Primärschlüsselwert 1 werden die vorhandene Zeile und die empfangene Zeile als nicht übereinstimmend betrachtet, weil die `Original`-Primärschlüsselwerte unterschiedlich sind. Wenn die Zusammenführung abgeschlossen ist und die Einschränkungen überprüft werden, wird allerdings eine Ausnahme ausgelöst, weil die `Current`-Primärschlüsselwerte die &lt;legacyBold&gt;Unique&lt;/legacyBold&gt;-Einschränkung für die Primärschlüsselspalte verletzen.

> [!NOTE]
> Beim Einfügen von Zeilen in Datenbanktabellen mit automatisch inkrementierenden Spalten, z. B. Identitätsspalten, ist es möglich, dass der von der Einfügung zurückgegebene Wert für die Identitätsspalte nicht mit dem Wert im `DataSet` übereinstimmt, sodass die zurückgegebenen Zeilen nicht zusammengeführt, sondern angefügt werden. Weitere Informationen finden Sie unter [Abrufen von Identitäts-oder](../retrieving-identity-or-autonumber-values.md)Auto Sequenz Werten.

Im folgenden Codebeispiel werden zwei `DataSet` -Objekte mit unterschiedlichen Schemas `DataSet` in einem zusammen mit den kombinierten Schemas der `DataSet` beiden eingehenden-Objekte zusammengeführt.

[!code-csharp[DataWorks DataSet.Merge#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataSet.Merge/CS/source.cs#1)]
[!code-vb[DataWorks DataSet.Merge#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataSet.Merge/VB/source.vb#1)]

Im folgenden Codebeispiel gibt es ein vorhandenes `DataSet` mit Updates, die an einen `DataAdapter` übergeben werden, der an der Datenquelle verarbeitet werden soll. Die Ergebnisse werden anschließend im ursprünglichen `DataSet` zusammengeführt. Nachdem die Änderungen zurückgewiesen wurden, die zu einem Fehler führten, wird mit `AcceptChanges` ein Commit für die zusammengeführten Änderungen ausgeführt.

[!code-csharp[DataWorks DataSet.MergeAcceptChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/CS/source.cs#1)]
[!code-vb[DataWorks DataSet.MergeAcceptChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/VB/source.vb#1)]

[!code-csharp[DataWorks DataSet.MergeAcceptChanges#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/CS/source.cs#2)]
[!code-vb[DataWorks DataSet.MergeAcceptChanges#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataSet.MergeAcceptChanges/VB/source.vb#2)]

## <a name="see-also"></a>Siehe auch

- [DataSets, DataTables und DataViews](index.md)
- [Zeilenstatus und Zeilenversionen](row-states-and-row-versions.md)
- [DataAdapters und DataReaders](../dataadapters-and-datareaders.md)
- [Abrufen und Ändern von Daten in ADO.NET](../retrieving-and-modifying-data.md)
- [Abrufen von Identity- oder Autonumber-Werten](../retrieving-identity-or-autonumber-values.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
