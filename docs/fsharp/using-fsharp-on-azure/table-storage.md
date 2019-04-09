---
title: Erste Schritte mit Azure Table Storage mit F#
description: Store strukturierte Daten in der Cloud mit Azure Table Storage oder Azure Cosmos DB.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: 54c777acd454e4f675175b814675c185e41ad9a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086701"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a>Erste Schritte mit Azure Table Storage und Azure Cosmos DB Table API mit F\#

Azure Table Storage ist ein Dienst, der strukturierte NoSQL-Daten in der Cloud gespeichert. Table Storage ist ein Schlüssel-/Attributspeicher mit einem schemalosen Design. Da der Tabellenspeicher schemalos ist, ist es einfach, Daten anzupassen, wenn sich die Anforderungen Ihrer Anwendung ändern. Zugriff auf Daten ist schnell und kostengünstig für alle Arten von Anwendungen. Table Storage ist in der Regel deutlich niedriger Kosten als herkömmliche SQL für ähnliche Datenmengen.

Sie können Table Storage verwenden, um flexible Datasets wie Benutzerdaten für Webanwendungen, Adressbücher, Geräteinformationen und andere Typen von Metadaten, die Ihr Dienst erfordert, zu speichern. Sie können eine beliebige Anzahl von Entitäten in einer Tabelle speichern, und ein Speicherkonto kann eine beliebige Anzahl von Tabellen, die bis zur speicherkapazitätsgrenze des Speicherkontos enthalten.

Azure Cosmos DB bietet die Table-API für Anwendungen, die für Azure Table Storage geschrieben sind und, wie z. B. Premium-Funktionen erfordern:

- Sofort einsatzbereite globale Verteilung.
- Dedizierter Durchsatz, die weltweit.
- Latenzen im einstelligen Millisekundenbereich im 99. Perzentil.
- Garantierte hochverfügbarkeit.
- Automatische sekundäre Indizierung.

Anwendungen für Azure Table Storage geschrieben wurden, können in Azure Cosmos DB mithilfe der Table-API ohne codeänderungen migrieren und profitieren Sie von Premium-Funktionen. Die Table-API enthält verfügbaren Client-SDKs für .NET, Java, Python und Node.js.

Weitere Informationen finden Sie unter [Einführung in die Table-API von Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/table-introduction).

## <a name="about-this-tutorial"></a>Informationen zu diesem Lernprogramm

In diesem Tutorial wird gezeigt, wie zum Schreiben F# Code zum Durchführen allgemeinen Aufgaben mit Azure Table Storage oder Azure Cosmos DB Table API, einschließlich erstellen und Löschen einer Tabelle und einfügen, aktualisieren, löschen und Abfragen von Tabellendaten zu tun.

## <a name="prerequisites"></a>Vorraussetzungen

Um dieses Handbuch verwenden zu können, müssen Sie zuerst [erstellen Sie ein Azure Storage-Konto](/azure/storage/storage-create-storage-account) oder [Azure Cosmos DB-Konto](https://azure.microsoft.com/try/cosmosdb/).

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen Sie einen F#-Skript, und starten F# Interactive

In die Beispielen in diesem Artikel verwendet werden können, entweder in eine F# Anwendung oder ein F# Skript. Zum Erstellen einer F# Skript, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `tables.fsx`in Ihre F# Entwicklungsumgebung.

Verwenden Sie als Nächstes eine [-Paket-Manager](package-management.md) wie z. B. [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` Paket und Verweis `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`Richtlinie. Führen Sie es noch mal `Microsoft.WindowsAzure.ConfigurationManager` um den Microsoft.Azure-Namespace zu erhalten.

### <a name="add-namespace-declarations"></a>Hinzufügen von Namespacedeklarationen

Fügen Sie die folgenden `open` Anweisungen am Anfang der `tables.fsx` Datei:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a>Die Azure Storage-Verbindungszeichenfolge abzurufen

Wenn Sie mit Azure Table Storage-Dienst verbinden, benötigen Sie die Verbindungszeichenfolge für dieses Tutorial. Sie können die Verbindungszeichenfolge aus dem Azure-Portal kopieren. Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Konfigurieren von Speicher-Verbindungszeichenfolgen](/azure/storage/storage-configure-connection-string).

### <a name="get-your-azure-cosmos-db-connection-string"></a>Die Azure Cosmos DB-Verbindungszeichenfolge abzurufen

Wenn Sie mit Azure Cosmos DB verbinden, benötigen Sie die Verbindungszeichenfolge für dieses Tutorial. Sie können die Verbindungszeichenfolge aus dem Azure-Portal kopieren. Navigieren Sie im Azure-Portal in Ihrem Cosmos DB-Konto zu **Einstellungen** > **Verbindungszeichenfolge**, und klicken Sie auf die **Kopie** , um die primäre Verbindung zu kopieren. Eine Zeichenfolge. 

Geben Sie Ihre Verbindungszeichenfolge für das Tutorial in Ihrem Skript verwenden, wie im folgenden Beispiel:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

Dies ist jedoch **nicht empfohlen,** für echte Projekte. Ihr speicherkontoschlüssel ähnelt das Stammkennwort für Ihr Speicherkonto. Achten Sie immer darauf zum Schützen der Schlüssel Ihres Speicherkontos. Vermeiden sie zu anderen Benutzern oder fest zu programmieren, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist. Sie können Ihren Schlüssel mithilfe von Azure-Portal, wenn Sie glauben, dass es unter Umständen kompromittiert wurden neu generieren.

Für reale Anwendungen, ist die beste Methode zum Verwalten Ihrer Speicher-Verbindungszeichenfolge in einer Konfigurationsdatei. Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie so vorgehen:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

Verwenden von Azure Configuration Manager ist optional. Sie können auch eine API wie die .NET Framework `ConfigurationManager` Typ.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungszeichenfolge

Um die Verbindungszeichenfolge zu analysieren, verwenden Sie:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

Dies gibt eine `CloudStorageAccount`.

### <a name="create-the-table-service-client"></a>Erstellen des Tabellenspeicherdienst-Clients

Die `CloudTableClient` -Klasse ermöglicht es Ihnen, Tabellen und Entitäten im Tabellenspeicher abrufen. Hier ist eine Möglichkeit zum Erstellen des Dienstclients:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

Jetzt können Sie Code schreiben, liest Daten aus und schreibt Daten in Table Storage.

### <a name="create-a-table"></a>Erstellen einer Tabelle

Dieses Beispiel zeigt, wie Sie eine Tabelle zu erstellen, wenn es nicht bereits vorhanden ist:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a>Hinzufügen einer Entität zu einer Tabelle

Eine Entität muss einen Typ aufweisen, die von erbt `TableEntity`. Sie können die erweitern `TableEntity` beliebig, aber der Typ *müssen* einen parameterlosen Konstruktor aufweisen. Nur Eigenschaften, die sowohl `get` und `set` in Ihrem Azure-Tabelle gespeichert sind.

Eine Entität des Partitions- und Zeilenschlüssel identifiziert eindeutig die Entität in der Tabelle. Entitäten mit demselben Partitionsschlüssel können schneller abgerufen werden als Entitäten mit verschiedenen partitionsschlüsseln, aber die Verwendung verschiedener Partitionsschlüssel ermöglicht größere Skalierbarkeit paralleler Vorgänge.

Hier ist ein Beispiel für eine `Customer` , verwendet der `lastName` als Partitionsschlüssel und die `firstName` als Zeilenschlüssel.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

Fügen Sie jetzt hinzu `Customer` in die Tabelle. Zu diesem Zweck erstellen Sie eine `TableOperation` , für die Tabelle ausführt. In diesem Fall erstellen Sie eine `Insert` Vorgang.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a>Einfügen eines entitätsbatchs

Sie können einen entitätsbatch in einer Tabelle mit einem einzelnen Schreibvorgang einfügen. Batch-Vorgänge ermöglichen es Ihnen, Vorgänge in eine einzelne Ausführung zu kombinieren, verfügen jedoch über einige Einschränkungen:

- Sie können Updates ausführen Lösch- und Einfügevorgänge in einem Batchvorgang.
- Ein Batchvorgang kann bis zu 100 Entitäten enthalten.
- Alle Entitäten in einem Batchvorgang müssen den gleichen Partitionsschlüssel aufweisen.
- Es ist, zwar möglich, eine Abfrage in einem Batchvorgang auszuführen muss es der einzige Vorgang im Batch sein.

Hier ist Code, der zwei Einfügevorgänge in einem Batchvorgang kombiniert:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a>Rufen Sie aller Entitäten in einer Partition ab

Um eine Tabelle für alle Entitäten in einer Partition abzufragen, verwenden eine `TableQuery` Objekt. Hier filtern Sie Entitäten, wobei "Smith" der Partitionsschlüssel ist.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

Sie werden nun die Ergebnisse drucken:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a>Abrufen eines entitätsbereichs in einer partition

Wenn Sie nicht alle Entitäten in einer Partition abrufen möchten, können Sie einen Bereich angeben, indem Sie den partitionsschlüsselfilter mit einem zeilenschlüsselfilter kombinieren. Hier verwenden Sie zwei Filter auf alle Entitäten in der Partition "Smith" abzurufen, in dem der Zeilenschlüssel (Vorname) mit einem Buchstaben vor "M" im Alphabet beginnt.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

Sie werden nun die Ergebnisse drucken:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a>Abrufen einer einzelnen Entität

Sie können eine Abfrage zum Abrufen einer bestimmten Entität schreiben. Hier ein `TableOperation` um den Kunden "Ben Smith" anzugeben. Anstatt einer Sammlung, erhalten Sie wieder eine `Customer`. Sowohl der Partitionsschlüssel und Zeilenschlüssel angeben, in einer Abfrage ist die schnellste Möglichkeit, eine einzelne Entität aus dem Tabellendienst abzurufen.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

Sie werden nun die Ergebnisse drucken:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a>Ersetzen einer Entität

Um eine Entität zu aktualisieren, rufen Sie sie aus dem Tabellendienst, ändern Sie das Entitätsobjekt und speichern Sie die Änderungen an den Tabellenspeicherdienst mit einem `Replace` Vorgang. Dies bewirkt, dass die Entität, die auf dem Server vollständig ersetzt werden, es sei denn, der die Entität, auf dem Server geändert wurde, seit sie abgerufen wurde, in diesem Fall schlägt der Vorgang fehl. Um zu verhindern, dass Ihre Anwendung von versehentlich überschriebenen Änderungen aus anderen Quellen für diesen Fehler ist.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a>Einfügen-oder-Ersetzen einer Entität

In einigen Fällen wissen Sie nicht, ob eine Entität in der Tabelle vorhanden ist. Und wenn dies der Fall ist, werden die aktuellen Werte, die darin gespeicherten nicht mehr benötigt. Sie können `InsertOrReplace` zum Erstellen der Entitäts oder Ersetzen Sie ihn, falls es vorhanden, unabhängig von ihrem Status ist.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a>Abfragen einer Teilmenge von Entitätseigenschaften

Eine Tabellenabfrage kann nur einige Eigenschaften aus einer Entität anstelle aller Textknoten abrufen. Diese Technik, die sogenannten Projektion, kann die abfrageleistung, besonders bei großen Entitäten verbessern. Hier ist Sie zurückkehren, nur e-Mail-Adressen, mit `DynamicTableEntity` und `EntityResolver`. Beachten Sie, dass Projektion nicht auf dem lokalen Speicheremulator unterstützt wird, damit dieser Code ausgeführt wird, nur, wenn Sie ein Konto für den Tabellendienst verwenden.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a>Abrufen von Entitäten in Seiten asynchron

Wenn Sie eine große Anzahl von Entitäten lesen und für die Verarbeitung warten, bis sie alle zurückgeben, können Sie eine segmentierte Abfrage verwenden, anstatt sie abgerufen werden sollen. Hier ist zurückgeben Sie Ergebnisse seitenweise mithilfe eines asynchronen Workflows, damit die Ausführung nicht blockiert wird, während Sie für eine große Anzahl zurückzugebender Ergebnisse warten.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

Sie führen Sie nun diese Berechnung synchron:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a>Löschen einer Entität

Sie können eine Entität löschen, nachdem Sie es abgerufen haben. Wie bei der Aktualisierung einer Entitätstyps Fehler dies, wenn die Entität geändert wurde, seitdem Sie abgerufen.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a>Löschen einer Tabelle

Sie können eine Tabelle aus einem Speicherkonto löschen. Eine Tabelle, die gelöscht wurde, werden als nicht verfügbar für eine bestimmte Zeitdauer nach dem Löschvorgang neu erstellt werden.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a>Nächste Schritte

Nun, da Sie die Grundlagen von Table Storage vertraut gemacht haben, führen Sie diesen Links Weitere Informationen zu komplexeren Speicheraufgaben und der Azure Cosmos DB-Tabellen-API.

- [Einführung in Azure Cosmos DB-Tabellen-API](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [Storage-Clientbibliothek für .NET-Referenz](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [Azure-Speicher-Typanbieter](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [Azure Storage-Teamblog](https://blogs.msdn.com/b/windowsazurestorage/)
- [Konfigurieren von Verbindungszeichenfolgen](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [Erste Schritte mit Azure Table Storage in .NET](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
