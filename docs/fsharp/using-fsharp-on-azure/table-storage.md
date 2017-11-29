---
title: Erste Schritte mit Azure-Tabellenspeicher mit f#
description: Speichern Sie strukturierte Daten in der Cloud mit Azure-Tabellenspeicher, ein NoSQL-Datenspeicher.
keywords: Visual f#, f#, funktionalen Programmierung, .NET, .NET Core, Azure
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9e5d6cea-a98c-461e-a5cc-75f1d154eafd
ms.openlocfilehash: bf833a96809768011f26df35332ab2372ced2aaf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-table-storage-using-f"></a>Erste Schritte mit Azure-Tabellenspeicher mit f# #

Azure-Tabellenspeicher ist ein Dienst, der strukturierte NoSQL-Daten in der Cloud gespeichert. Tabellenspeicher ist ein Key-Attribut mit einem schemaless Entwurf. Da Table Storage schemaless ist, ist es einfach, Daten von Ihrer Anwendung Evolve sich Anforderungen anzupassen. Zugriff auf Daten ist schnell und kostengünstig für alle Arten von Anwendungen. Tabellenspeicher ist in der Regel deutlich niedriger Kosten als herkömmliche SQL für ähnliche Datenmengen.

Sie können Tabellenspeicher zum Speichern von flexible Datasets, wie z. B. Benutzerdaten für Webanwendungen, Adressbücher Geräteinformationen und andere Arten von Metadaten, die Ihr Dienst erfordert, verwenden. Sie können eine beliebige Anzahl von Entitäten in einer Tabelle speichern, und ein Speicherkonto kann eine beliebige Anzahl von Tabellen, bis die Kapazitätsgrenze des Speicherkontos zu enthalten.

### <a name="about-this-tutorial"></a>Zu diesem Lernprogramm

Dieses Lernprogramm zeigt, wie F#-Code werden einige häufig auszuführende Aufgaben mithilfe von Azure-Tabellenspeicher, einschließlich erstellen und Löschen einer Tabelle und einfügen, aktualisieren, löschen und Abfragen von Daten aus Tabellen schreiben.

Eine grundlegende Übersicht des tabellenspeichers finden Sie unter [.NET Guide für den Tabellenspeicher](/azure/storage/storage-dotnet-how-to-use-tables)

## <a name="prerequisites"></a>Erforderliche Komponenten

Um dieser Anleitung zu verwenden, müssen Sie zuerst [Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).
Sie benötigen auch Ihr speicherzugriffsschlüssel für dieses Konto.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen Sie ein f#-Skript und Start f# Interactive

Die Beispiele in diesem Artikel können in einer f#-Anwendung oder ein F#-Skript verwendet werden. Um ein F#-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `tables.fsx`, in der f#-Entwicklungsumgebung.

Verwenden Sie als Nächstes eine [Paket-Manager](package-management.md) wie z. B. [Paket](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` Paket und Verweis `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`Richtlinie. Führen Sie wieder für "Microsoft.WindowsAzure.ConfigurationManager", um den Namespace Microsoft.Azure zu erhalten.

### <a name="add-namespace-declarations"></a>Fügen Sie Namespacedeklarationen hinzu

Fügen Sie die folgenden `open` Anweisungen am oberen Rand der `tables.fsx` Datei:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Abrufen der Verbindungszeichenfolge

Sie benötigen eine Azure-Speicher-Verbindungszeichenfolge für dieses Lernprogramm. Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Speicherverbindungs-Zeichenfolgen konfigurieren](/azure/storage/storage-configure-connection-string).

Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt ein:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

Dies ist jedoch **nicht empfohlen,** für tatsächliche Projekte. Schlüssel für das Speicherkonto ähnelt das Stammkennwort für Ihr Speicherkonto. Achten Sie stets darauf zum Schützen der Schlüssel für das Speicherkonto. Vermeiden Sie verteilen an andere Benutzer, die eine feste Programmierung, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist. Sie können erneut zu generieren Ihres Schlüssels im Azure-Portal verwenden, wenn Sie glauben, dass er gefährdet sein kann.

Für echten Anwendungen ist die beste Methode zum Verwalten Ihrer speicherverbindungs-Zeichenfolge in einer Konfigurationsdatei. Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie dies tun:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

Mit Azure-Konfigurations-Manager ist optional. Sie können auch eine API wie das .NET Framework `ConfigurationManager` Typ.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungszeichenfolge

Verwenden Sie, um die Verbindungszeichenfolge zu analysieren:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

Dadurch wird zurückgegeben, eine `CloudStorageAccount`.

### <a name="create-the-table-service-client"></a>Erstellen Sie den tabellendienstclient

Die `CloudTableClient` -Klasse ermöglicht es Ihnen, zum Abrufen von Tabellen und Entitäten im Tabellenspeicher gespeichert. Dies ist eine Methode zum Erstellen des Service-Clients:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

Jetzt können Sie Code schreiben, liest Daten aus und schreibt Daten in den Tabellenspeicher.

## <a name="create-a-table"></a>Erstellen Sie eine Tabelle

Dieses Beispiel zeigt, wie eine Tabelle erstellt, wenn sie nicht bereits vorhanden ist:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

## <a name="add-an-entity-to-a-table"></a>Hinzufügen einer Entität zu einer Tabelle

Eine Entität muss einen Typ aufweisen, die von erben `TableEntity`. Sie erweitern können `TableEntity` in beliebig, aber Ihr Typ *müssen* einen parameterlosen Konstruktor aufweisen. Nur Eigenschaften, die sowohl `get` und `set` in Ihrem Azure-Tabelle gespeichert wird.

Eine Entität Partitions- und Zeilenschlüssel ist die Entität in der Tabelle eindeutig identifiziert. Entitäten mit den gleichen Partitionsschlüssel können schneller als mit anderen Partitionsschlüssel abgefragt werden, jedoch mit unterschiedlichen Partitionsschlüssel für eine höhere Skalierbarkeit von parallelen Vorgängen ermöglicht.

Hier ist ein Beispiel für eine `Customer` , verwendet der `lastName` als Partitionsschlüssel und `firstName` als Zeilenschlüssel.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

Nachdem wir hinzufügen unsere `Customer` der Tabelle. Zu diesem Zweck erstellen Sie eine `TableOperation` , die für die Tabelle ausgeführt wird. In diesem Fall erstellen Sie ein `Insert` Vorgang.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

## <a name="insert-a-batch-of-entities"></a>Einfügen eines entitätenbatches

Sie können einen entitätenbatch in einer Tabelle mit einem einzelnen Schreibvorgang einfügen. Batchvorgänge ermöglichen es Ihnen, Vorgänge in eine einzelne Ausführung zu kombinieren, verfügen jedoch über einige Einschränkungen:

- Sie können Updates ausführen löscht, und fügt Sie in einem Batchvorgang.
- Ein Batchvorgang kann bis zu 100 Entitäten enthalten.
- Alle Entitäten in einem Batchvorgang müssen den gleichen Partitionsschlüssel haben.
- Es ist, zwar möglich, eine Abfrage in einem Batchvorgang auszuführen muss es die einzige Vorgang im Batch sein.

Hier ist Teil des Codes, die zwei einfügungen in einem Batchvorgang kombiniert:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

## <a name="retrieve-all-entities-in-a-partition"></a>Rufen Sie aller Entitäten in einer Partition ab

Verwenden Sie zum Abfragen einer Tabelle für alle Entitäten in einer Partition, eine `TableQuery` Objekt. Hier ist filtern Sie für Entitäten, wobei der Partitionsschlüssel ist "Buster".

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L80)]

Jetzt werden die Ergebnisse drucken:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


## <a name="retrieve-a-range-of-entities-in-a-partition"></a>Rufen Sie einen Bereich von Entitäten in einer partition

Wenn Sie nicht alle Entitäten in einer Partition abfragen möchten, können Sie einen Bereich angeben, durch die Kombination der Filter der Partition Schlüssel mit einem Schlüssel Zeilenfilter. Hier verwenden Sie zwei Filter auf alle Entitäten in der Partition "Buster" abrufen, wo der Zeilenschlüssel (Rufname) früher als "M" im Alphabet mit einem Buchstaben beginnt.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

Jetzt werden die Ergebnisse drucken:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

## <a name="retrieve-a-single-entity"></a>Abrufen einer einzelnen Entität

Sie können eine Abfrage zum Abrufen einer bestimmten Entität schreiben. Verwenden Sie hier eine `TableOperation` an den Kunden "Larry Buster". Statt einer Auflistung erhalten Sie wieder eine `Customer`. Der Partitionsschlüssel und Zeilenschlüssel in einer Abfrage angegeben, ist die schnellste Möglichkeit zum Abrufen einer einzelnen Entität aus dem Tabellendienst.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

Jetzt werden die Ergebnisse drucken:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


## <a name="replace-an-entity"></a>Ersetzen einer Entität

Zum Aktualisieren einer Entität aus der Tabellendienst abrufen, das Entitätsobjekt ändern und speichern Sie die Änderungen an der Tabelle mit einer `Replace` Vorgang. Dies bewirkt, dass die Entität, die auf dem Server vollständig ersetzt werden, es sei denn, die Entität, auf dem Server geändert wurde, seit sie abgerufen wurde, in diesem Fall schlägt der Vorgang fehl. Dieser Fehler wird verhindert, dass die Anwendung von Änderungen aus anderen Quellen versehentlich überschrieben.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

## <a name="insert-or-replace-an-entity"></a>INSERT-oder-Ersetzen einer Entität

In einigen Fällen, wissen Sie nicht, wenn die Entität in der Tabelle oder nicht vorhanden ist. Und wenn dies der Fall ist, werden die aktuellen Werte, die darin gespeicherten nicht mehr benötigt. Sie können `InsertOrReplace` zum Erstellen der Entität oder Ersetzen Sie ihn, falls es vorhanden, unabhängig von ihrem Status ist.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L140)]

## <a name="query-a-subset-of-entity-properties"></a>Die Abfrage eine Teilmenge von Entitätseigenschaften

Eine Table-Abfrage kann aus einer Entität anstelle aller Textknoten nur wenige Eigenschaften abgerufen werden. Diese Technik mit dem Namen Projektion kann, insbesondere bei großen Entitäten verbessern. Hier ist Sie zurückkehren nur e-Mail-Adressen mit `DynamicTableEntity` und `EntityResolver`. Beachten Sie, dass die Projektion auf den lokalen Speicheremulator nicht unterstützt wird, sodass dieser Code ausgeführt wird, nur, wenn Sie ein Konto für den Tabellendienst verwenden.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L146-L157)]

## <a name="retrieve-entities-in-pages-asynchronously"></a>Abrufen von Entitäten in Seiten asynchron

Wenn Sie eine große Anzahl von Entitäten lesen gerade und verarbeiten sie abgerufen werden, sondern wartet, bis sie alle zurückgeben, können Sie eine Abfrage segmentierte werden sollen. Hier geben Sie Ergebnisse in Seiten mit einem asynchronen Workflow, damit die Ausführung nicht blockiert wird, während für eine große Anzahl der zurückzugebenden Ergebnisseite warten, können Sie zurück.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L177)]

Sie nun diese Berechnung synchron ausgeführt:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L179-L179)]

## <a name="delete-an-entity"></a>Löschen einer Entität

Sie können eine Entität löschen, nachdem Sie es abgerufen haben. Wie bei der Aktualisierung einer Entität, schlägt dies fehl, wenn die Entität geändert wurde, seit Sie sie abgerufen.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L185-L186)]

## <a name="delete-a-table"></a>Löschen einer Tabelle

Sie können eine Tabelle aus einem Speicherkonto löschen. Eine Tabelle, die gelöscht wurde ist nicht verfügbar für eine bestimmte Zeitdauer nach dem Löschvorgang neu erstellt werden.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L192-L192)]

## <a name="next-steps"></a>Nächste Schritte

Nun, dass Sie die Grundlagen des tabellenspeichers gelernt haben, führen Sie die folgenden Links, um weitere Informationen zu komplexeren Speicheraufgaben:

- [Speicherclientbibliothek für .NET-Referenz](http://go.microsoft.com/fwlink/?LinkID=390731&clcid=0x409)
- [Azure-Speicher-Typanbieter](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [Azure-Speicher-Teamblog](http://blogs.msdn.com/b/windowsazurestorage/)
- [Konfigurieren von Verbindungszeichenfolgen](http://msdn.microsoft.com/library/azure/ee758697.aspx)
- [Erste Schritte mit Azure-Tabellenspeicher in .NET](https://azure.microsoft.com/documentation/samples/storage-table-dotnet-getting-started/)
