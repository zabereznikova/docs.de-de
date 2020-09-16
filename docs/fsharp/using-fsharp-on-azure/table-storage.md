---
title: Erste Schritte mit Azure Table Storage mit F#
description: Speichern Sie strukturierte Daten mit Azure Table Storage oder Azure Cosmos DB in der Cloud.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: eb25fda0bb3c658eed2f675d6ba79c689a9080a9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548350"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a>Beginnen Sie mit dem Azure-Tabellen Speicher und den Azure Cosmos DB Tabellen-API mit F\#

Azure Table Storage ist ein Dienst, bei dem strukturierte NoSQL-Daten in der Cloud gespeichert werden. Bei Table Storage handelt es sich um einen Schlüssel-/Attributspeicher mit einem schemalosen Design. Aufgrund der Schemalosigkeit von Table Storage ist es einfach, Ihre Daten an die Entwicklung Ihrer Anwendungen anzupassen. Der Datenzugriff ist für alle Arten von Anwendungen schnell und kostengünstig. Table Storage ist in der Regel erheblich günstiger als herkömmliche SQL-Lösungen für ähnliche Datenmengen.

Mit Table Storage können Sie flexible Datasets wie Benutzerdaten für Webanwendungen, Adressbücher, Geräteinformationen und jegliche Art von Metadaten speichern, die Ihr Dienst erfordert. Sie können eine beliebige Anzahl von Entitäten in einer Tabelle speichern, und ein Speicherkonto kann eine beliebige Anzahl von Tabellen enthalten (bis zur Speicherkapazitätsgrenze eines Speicherkontos).

Azure Cosmos DB stellt die Tabellen-API für Anwendungen bereit, die für Azure Table Storage geschrieben wurden und die Premium-Funktionen wie z. b.:

- Globale, sofort einsatzbereite Verteilung
- Dedizierter Durchsatz weltweit.
- Einstellige Latenzzeiten im Millisekundenbereich im 99. Perzentil.
- Garantierte Hochverfügbarkeit.
- Automatische sekundäre Indizierung

Anwendungen, die für Azure Table Storage geschrieben sind, können mit der Table-API ohne Codeänderungen zu Azure Cosmos DB migriert werden und Premium-Funktionen nutzen. Die Tabellen-API verfügt über Client-SDKs, die für .NET, Java, Python und Node.js verfügbar sind.

Weitere Informationen finden Sie unter [Einführung in Azure Cosmos DB Tabellen-API](/azure/cosmos-db/table-introduction).

## <a name="about-this-tutorial"></a>Informationen zu diesem Tutorial

In diesem Tutorial wird gezeigt, wie Sie F #-Code schreiben können, um einige gängige Aufgaben mithilfe von Azure Table Storage oder der Azure Cosmos DB Tabellen-API auszuführen, einschließlich dem Erstellen und Löschen einer Tabelle sowie dem Einfügen, aktualisieren, löschen und Abfragen von Tabellendaten.

## <a name="prerequisites"></a>Voraussetzungen

Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure-Speicherkonto](/azure/storage/storage-create-storage-account) oder [Azure Cosmos DB Konto](https://azure.microsoft.com/try/cosmosdb/)erstellen.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen eines F #-Skripts und starten F# Interactive

Die Beispiele in diesem Artikel können in einer f #-Anwendung oder einem f #-Skript verwendet werden. Um ein F #-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z `tables.fsx` . b. in ihrer F #-Entwicklungsumgebung.

Verwenden Sie als nächstes einen [Paket-Manager](package-management.md) , z. b. [Paket](https://fsprojects.github.io/Paket/) oder [nuget](https://www.nuget.org/) , um das Paket zu installieren, `WindowsAzure.Storage` und verweisen `WindowsAzure.Storage.dll` Sie mithilfe einer-Anweisung in Ihrem Skript `#r` Führen Sie es erneut aus `Microsoft.WindowsAzure.ConfigurationManager` , um den Microsoft. Azure-Namespace zu erhalten.

### <a name="add-namespace-declarations"></a>Hinzufügen von Namespace-Deklarationen

Fügen Sie am Anfang der Datei `tables.fsx` die folgenden `open`-Anweisungen ein:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a>Azure Storage Verbindungs Zeichenfolge erhalten

Wenn Sie eine Verbindung mit Azure Storage Tabellen Dienst herstellen, benötigen Sie die Verbindungs Zeichenfolge für dieses Tutorial. Sie können die Verbindungs Zeichenfolge aus der Azure-Portal kopieren. Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.

### <a name="get-your-azure-cosmos-db-connection-string"></a>Azure Cosmos DB Verbindungs Zeichenfolge erhalten

Wenn Sie eine Verbindung mit Azure Cosmos DB herstellen, benötigen Sie die Verbindungs Zeichenfolge für dieses Tutorial. Sie können die Verbindungs Zeichenfolge aus der Azure-Portal kopieren. Wechseln Sie in der Azure-Portal in Ihrem Cosmos DB Konto zu **Einstellungen**  >  **Verbindungs Zeichenfolge**, und klicken Sie auf die Schaltfläche **Kopieren** , um die primäre Verbindungs Zeichenfolge zu kopieren.

Geben Sie für das Tutorial die Verbindungs Zeichenfolge in Ihrem Skript ein, wie im folgenden Beispiel gezeigt:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

Dies wird jedoch nicht für echte Projekte **empfohlen** . Ihr Speicherkontoschlüssel ähnelt dem Stammkennwort für das Speicherkonto. Achten Sie darauf, den Speicherkontoschlüssel immer gut zu schützen. Geben Sie ihn nicht an andere Benutzer weiter, vermeiden Sie das Hartcodieren, und speichern Sie ihn nicht in einer Klartextdatei, auf die andere Benutzer zugreifen können. Sie können Ihren Schlüssel mithilfe des Azure-Portals neu generieren, wenn Sie der Meinung sind, dass er möglicherweise kompromittiert wurde

Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei. Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

Die Verwendung von Azure Configuration Manager ist optional. Sie können auch eine API verwenden, z. b. den Typ der .NET Framework `ConfigurationManager` .

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungszeichenfolge

Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

Gibt einen zurück `CloudStorageAccount` .

### <a name="create-the-table-service-client"></a>Erstellen des Tabellenspeicherdienst-Clients

Mit der- `CloudTableClient` Klasse können Sie Tabellen und Entitäten im Tabellen Speicher abrufen. Hier sehen Sie eine Möglichkeit zum Erstellen des Dienstclients:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

Jetzt können Sie Code schreiben, der Daten aus dem Tabellenspeicher liest und Daten in den Tabellenspeicher schreibt.

### <a name="create-a-table"></a>Erstellen einer Tabelle

Dieses Beispiel zeigt, wie Sie eine Tabelle erstellen, falls sie nicht bereits vorhanden ist:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a>Hinzufügen einer Entität zu einer Tabelle

Eine Entität muss über einen Typ verfügen, der von erbt `TableEntity` . Sie können `TableEntity` in beliebig erweitern, aber der Typ *muss* über einen Parameter losen Konstruktor verfügen. Nur Eigenschaften, die sowohl `get` als auch aufweisen, `set` werden in der Azure-Tabelle gespeichert.

Mit dem Partitions-und Zeilen Schlüssel einer Entität wird die Entität in der Tabelle eindeutig identifiziert. Entitäten mit demselben Partitionsschlüssel können schneller abgerufen werden als Entitäten mit unterschiedlichen Partitionsschlüsseln, die Verwendung verschiedener Partitionsschlüssel ermöglicht jedoch eine größere Skalierbarkeit paralleler Vorgänge.

Im folgenden finden Sie ein Beispiel für einen `Customer` , der `lastName` als Partitions Schlüssel und `firstName` als Zeilen Schlüssel verwendet.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

Fügen Sie nun `Customer` der Tabelle hinzu. Erstellen Sie hierzu einen `TableOperation` , der für die Tabelle ausgeführt wird. In diesem Fall erstellen Sie einen `Insert` Vorgang.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a>Einfügen eines Entitätsbatchs

Sie können einen Batch von Entitäten in eine Tabelle einfügen, indem Sie einen einzelnen Schreibvorgang verwenden. Mit Batch Vorgängen können Sie Vorgänge in einer einzelnen Ausführung kombinieren, aber Sie haben einige Einschränkungen:

- Sie können Updates, Löschungen und Einfügungen im gleichen Batch Vorgang ausführen.
- Ein Batch Vorgang kann bis zu 100 Entitäten umfassen.
- Alle Entitäten in einem Batch Vorgang müssen über denselben Partitions Schlüssel verfügen.
- Obwohl es möglich ist, eine Abfrage in einem Batch Vorgang auszuführen, muss dies der einzige Vorgang im Batch sein.

Hier ist ein Code, der zwei Einfügungen in einem Batch Vorgang kombiniert:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a>Abrufen aller Entitäten einer Partition

Verwenden Sie ein `TableQuery`-Objekt, um für eine Tabelle alle Entitäten einer Partition abzufragen. Hier Filtern Sie nach Entitäten, bei denen "Smith" der Partitions Schlüssel ist.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

Sie drucken nun die Ergebnisse:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a>Abrufen eines Entitätsbereichs in einer Partition

Wenn Sie nicht alle Entitäten in einer Partition abrufen möchten, können Sie einen Bereich angeben, indem Sie den Partitionsschlüsselfilter mit einem Zeilenschlüsselfilter kombinieren. Hier verwenden Sie zwei Filter, um alle Entitäten in der "Smith"-Partition zu erhalten, wobei der Zeilen Schlüssel (Vorname) mit einem Buchstaben vor "M" im Alphabet beginnt.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

Sie drucken nun die Ergebnisse:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a>Abrufen einer einzelnen Entität

Sie können eine Abfrage schreiben, um eine einzelne bestimmte Entität abzurufen. Hier verwenden Sie einen `TableOperation` , um den Kunden "Ben Smith" anzugeben. Anstelle einer Auflistung erhalten Sie eine `Customer` . Das Angeben von Partitions Schlüssel und Zeilen Schlüssel in einer Abfrage ist die schnellste Möglichkeit, um eine einzelne Entität aus dem Tabellen Dienst abzurufen.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

Sie drucken nun die Ergebnisse:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a>Ersetzen einer Entität

Um eine Entität zu aktualisieren, rufen Sie Sie aus dem Tabellen Dienst ab, ändern Sie das Entitäts Objekt, und speichern Sie die Änderungen dann mit einem-Vorgang im Tabellen Dienst `Replace` . Dadurch wird die Entität auf dem Server vollständig ersetzt, es sei denn, die Entität auf dem Server wurde seit dem Abrufen geändert. in diesem Fall schlägt der Vorgang fehl. Dieser Fehler soll verhindern, dass Ihre Anwendung versehentlich Änderungen aus anderen Quellen überschreibt.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a>Einfügen-oder-Ersetzen einer Entität

Manchmal wissen Sie nicht, ob eine Entität in der Tabelle vorhanden ist. Wenn dies der Fall ist, werden die darin gespeicherten aktuellen Werte nicht mehr benötigt. Sie können verwenden, `InsertOrReplace` um die Entität zu erstellen oder zu ersetzen, wenn Sie vorhanden ist, unabhängig von Ihrem Zustand.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a>Abfragen einer Teilmenge von Entitätseigenschaften

Eine Tabellen Abfrage kann nur einige wenige Eigenschaften aus einer Entität abrufen, anstatt Sie zu verwenden. Diese Technik, die als Projektion bezeichnet wird, kann die Abfrageleistung verbessern, insbesondere bei großen Entitäten. Hier geben Sie nur e-Mail-Adressen mit `DynamicTableEntity` und zurück `EntityResolver` . Beachten Sie, dass Projektion nicht auf dem lokalen Speicheremulator unterstützt wird, weshalb dieser Code nur ausgeführt wird, wenn Sie ein Konto für den Tabellendienst verwenden.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a>Asynchrones Abrufen von Entitäten in Seiten

Wenn Sie eine große Anzahl von Entitäten lesen und diese beim Abrufen verarbeiten möchten, anstatt darauf zu warten, dass alle zurückgegeben werden, können Sie eine segmentierte Abfrage verwenden. Hier geben Sie die Ergebnisse in Seiten zurück, indem Sie einen asynchronen Workflow verwenden, sodass die Ausführung nicht blockiert wird, während Sie auf die Rückgabe eines großen Ergebnissatzes warten.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

Sie führen diese Berechnung nun synchron aus:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a>Löschen einer Entität

Sie können eine Entität löschen, nachdem Sie sie abgerufen haben. Wie beim Aktualisieren einer Entität schlägt dies fehl, wenn sich die Entität seit dem Abruf geändert hat.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a>Löschen einer Tabelle

Sie können eine Tabelle aus einem Speicherkonto löschen. Eine gelöschte Tabelle kann für eine bestimmte Zeitdauer nach dem Löschvorgang nicht neu erstellt werden.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie sich nun mit den Grundlagen von Table Storage vertraut gemacht haben, folgen Sie diesen Links, um mehr über komplexere Speicher Aufgaben und die Azure Cosmos DB Tabellen-API zu erfahren.

- [Einführung in Azure Cosmos DB Tabellen-API](/azure/cosmos-db/table-introduction)
- [Referenz zur Storage-Clientbibliothek für .NET](/dotnet/api/overview/azure/storage)
- [Azure Storage Typanbieter](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [Azure Storage-Teamblog](/archive/blogs/windowsazurestorage/)
- [Konfigurieren von Verbindungszeichenfolgen](/azure/storage/common/storage-configure-connection-string)
