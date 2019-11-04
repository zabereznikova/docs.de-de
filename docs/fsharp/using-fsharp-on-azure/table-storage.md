---
title: Erste Schritte mit Azure Table Storage mit F#
description: Speichern Sie strukturierte Daten mit Azure Table Storage oder Azure Cosmos DB in der Cloud.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: 6833e2264f7543f50b94892b6980140e4bf1cdd1
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424596"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a>Beginnen Sie mit dem Azure-Tabellen Speicher und den Azure Cosmos DB Tabellen-API mit F\#

Azure Table Storage ist ein Dienst, mit dem strukturierte nosql-Daten in der Cloud gespeichert werden. Table Storage ist ein Schlüssel-/Attributspeicher mit einem Schema losen Design. Da der Tabellen Speicher Schema Reich ist, ist es einfach, Ihre Daten anzupassen, wenn sich die Anforderungen Ihrer Anwendung weiterentwickeln. Der Zugriff auf Daten ist für alle Arten von Anwendungen schnell und kostengünstig. Der Tabellen Speicher ist in der Regel erheblich niedriger als herkömmlicher SQL für ähnliche Datenmengen.

Mit Table Storage können Sie flexible Datasets wie Benutzerdaten für Webanwendungen, Adressbücher, Geräteinformationen und andere Metadaten, die für Ihren Dienst erforderlich sind, speichern. Sie können eine beliebige Anzahl von Entitäten in einer Tabelle speichern, und ein Speicherkonto kann eine beliebige Anzahl von Tabellen enthalten, bis die Kapazitätsgrenze des Speicher Kontos erreicht ist.

Azure Cosmos DB stellt die Tabellen-API für Anwendungen bereit, die für Azure Table Storage geschrieben wurden und die Premium-Funktionen wie z. b.:

- Sofort einsetzbare globale Verteilung.
- Weltweit dedizierter Durchsatz.
- Latenzen im einstelligen Millisekundenbereich im 99. Perzentil.
- Garantierte hohe Verfügbarkeit.
- Automatische sekundäre Indizierung.

Anwendungen, die für Azure Table Storage geschrieben wurden, können zu Azure Cosmos DB migriert werden, indem Sie die Tabellen-API ohne Codeänderungen verwenden und die Premium-Funktionen nutzen. In der Tabellen-API sind Client-sdjs für .net, Java, Python und Node. js verfügbar.

Weitere Informationen finden Sie unter [Einführung in Azure Cosmos DB Tabellen-API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).

## <a name="about-this-tutorial"></a>Informationen zu diesem Tutorial

In diesem Tutorial wird gezeigt, F# wie Sie Code schreiben können, um einige gängige Aufgaben mithilfe von Azure Table Storage oder der Azure Cosmos DB Tabellen-API auszuführen. dazu zählen das Erstellen und Löschen einer Tabelle sowie das Einfügen, aktualisieren, löschen und Abfragen von Tabellendaten.

## <a name="prerequisites"></a>Erforderliche Voraussetzungen

Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure-Speicherkonto](/azure/storage/storage-create-storage-account) oder [Azure Cosmos DB Konto](https://azure.microsoft.com/try/cosmosdb/)erstellen.

## <a name="create-an-f-script-and-start-f-interactive"></a>F# Skript erstellen und interaktiv starten F#

Die Beispiele in diesem Artikel können entweder in einer F# Anwendung oder in einem F# Skript verwendet werden. Um ein F# Skript zu erstellen, erstellen Sie F# eine Datei mit der Erweiterung "`.fsx`" (z. b. `tables.fsx`) in der Entwicklungsumgebung.

Verwenden Sie als nächstes einen [Paket-Manager](package-management.md) wie z. b. [Paket](https://fsprojects.github.io/Paket/) oder [nuget](https://www.nuget.org/) , um das `WindowsAzure.Storage`-Paket zu installieren, und verweisen Sie `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`-Direktive Wiederholen Sie den Vorgang für `Microsoft.WindowsAzure.ConfigurationManager`, um den Microsoft. Azure-Namespace zu erhalten.

### <a name="add-namespace-declarations"></a>Namespace Deklarationen hinzufügen

Fügen Sie am Anfang der Datei `tables.fsx` die folgenden `open`-Anweisungen ein:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a>Azure Storage Verbindungs Zeichenfolge erhalten

Wenn Sie eine Verbindung mit Azure Storage Tabellen Dienst herstellen, benötigen Sie die Verbindungs Zeichenfolge für dieses Tutorial. Sie können die Verbindungs Zeichenfolge aus der Azure-Portal kopieren. Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.

### <a name="get-your-azure-cosmos-db-connection-string"></a>Azure Cosmos DB Verbindungs Zeichenfolge erhalten

Wenn Sie eine Verbindung mit Azure Cosmos DB herstellen, benötigen Sie die Verbindungs Zeichenfolge für dieses Tutorial. Sie können die Verbindungs Zeichenfolge aus der Azure-Portal kopieren. Wechseln Sie in der Azure-Portal in Ihrem Cosmos DB Konto zu **Einstellungen** > **Verbindungs Zeichenfolge**, und klicken Sie auf die Schaltfläche " **Kopieren** ", um die primäre Verbindungs Zeichenfolge zu kopieren.

Geben Sie für das Tutorial die Verbindungs Zeichenfolge in Ihrem Skript ein, wie im folgenden Beispiel gezeigt:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

Dies wird jedoch nicht für echte Projekte **empfohlen** . Ihr Speicherkonto Schlüssel ähnelt dem Stamm Kennwort für Ihr Speicherkonto. Achten Sie immer darauf, ihren Speicherkonto Schlüssel zu schützen. Verteilen Sie Sie nicht an andere Benutzer, hart codieren Sie Sie, oder speichern Sie Sie in einer nur-Text-Datei, auf die andere Benutzer zugreifen können. Sie können Ihren Schlüssel mithilfe des Azure-Portals neu generieren, wenn Sie der Meinung sind, dass er möglicherweise kompromittiert wurde

Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei. Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

Die Verwendung von Azure Configuration Manager ist optional. Sie können auch eine API verwenden, z. b. den `ConfigurationManager`-Typ der .NET Framework.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungs Zeichenfolge

Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

Dies gibt einen `CloudStorageAccount` zurück.

### <a name="create-the-table-service-client"></a>Erstellen des Tabellen Dienst Clients

Die `CloudTableClient`-Klasse ermöglicht das Abrufen von Tabellen und Entitäten im Tabellen Speicher. Dies ist eine Möglichkeit, den Dienst Client zu erstellen:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

Jetzt können Sie Code schreiben, der Daten aus dem Tabellen Speicher liest und Daten in den Tabellen Speicher schreibt.

### <a name="create-a-table"></a>Erstellen einer Tabelle

Dieses Beispiel zeigt, wie eine Tabelle erstellt wird, wenn Sie nicht bereits vorhanden ist:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a>Hinzufügen einer Entität zu einer Tabelle

Eine Entität muss über einen Typ verfügen, der von `TableEntity` erbt. Sie können `TableEntity` in beliebiger Weise erweitern, aber der Typ *muss* über einen Parameter losen Konstruktor verfügen. Nur Eigenschaften, die sowohl `get` als auch `set` aufweisen, werden in der Azure-Tabelle gespeichert.

Mit dem Partitions-und Zeilen Schlüssel einer Entität wird die Entität in der Tabelle eindeutig identifiziert. Entitäten mit demselben Partitions Schlüssel können schneller abgefragt werden als solche mit unterschiedlichen Partitions Schlüsseln, die Verwendung verschiedener Partitions Schlüssel ermöglicht jedoch eine größere Skalierbarkeit paralleler Vorgänge.

Im folgenden finden Sie ein Beispiel für eine `Customer`, die die `lastName` als Partitions Schlüssel und die `firstName` als Zeilen Schlüssel verwendet.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

Fügen Sie nun `Customer` der Tabelle hinzu. Erstellen Sie zu diesem Zweck eine `TableOperation`, die für die Tabelle ausgeführt wird. In diesem Fall erstellen Sie einen `Insert`-Vorgang.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a>Einfügen eines entitätenbatches

Sie können einen Batch von Entitäten in eine Tabelle einfügen, indem Sie einen einzelnen Schreibvorgang verwenden. Mit Batch Vorgängen können Sie Vorgänge in einer einzelnen Ausführung kombinieren, aber Sie haben einige Einschränkungen:

- Sie können Updates, Löschungen und Einfügungen im gleichen Batch Vorgang ausführen.
- Ein Batch Vorgang kann bis zu 100 Entitäten umfassen.
- Alle Entitäten in einem Batch Vorgang müssen über denselben Partitions Schlüssel verfügen.
- Obwohl es möglich ist, eine Abfrage in einem Batch Vorgang auszuführen, muss dies der einzige Vorgang im Batch sein.

Hier ist ein Code, der zwei Einfügungen in einem Batch Vorgang kombiniert:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a>Abrufen aller Entitäten in einer Partition

Um eine Tabelle für alle Entitäten in einer Partition abzufragen, verwenden Sie ein `TableQuery`-Objekt. Hier Filtern Sie nach Entitäten, bei denen "Smith" der Partitions Schlüssel ist.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

Sie drucken nun die Ergebnisse:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a>Abrufen eines Bereichs von Entitäten in einer Partition

Wenn Sie nicht alle Entitäten in einer Partition Abfragen möchten, können Sie einen Bereich angeben, indem Sie den Partitions Schlüssel Filter mit einem Zeilen Schlüssel Filter kombinieren. Hier verwenden Sie zwei Filter, um alle Entitäten in der "Smith"-Partition zu erhalten, wobei der Zeilen Schlüssel (Vorname) mit einem Buchstaben vor "M" im Alphabet beginnt.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

Sie drucken nun die Ergebnisse:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a>Abrufen einer einzelnen Entität

Sie können eine Abfrage schreiben, um eine einzelne, bestimmte Entität abzurufen. Hier verwenden Sie einen `TableOperation`, um den Kunden "Ben Smith" anzugeben. Anstelle einer Auflistung erhalten Sie eine `Customer`. Das Angeben von Partitions Schlüssel und Zeilen Schlüssel in einer Abfrage ist die schnellste Möglichkeit, um eine einzelne Entität aus dem Tabellen Dienst abzurufen.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

Sie drucken nun die Ergebnisse:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a>Ersetzen einer Entität

Um eine Entität zu aktualisieren, rufen Sie Sie aus dem Tabellen Dienst ab, ändern Sie das Entitäts Objekt, und speichern Sie die Änderungen dann mit einem `Replace`-Vorgang im Tabellen Dienst. Dadurch wird die Entität auf dem Server vollständig ersetzt, es sei denn, die Entität auf dem Server wurde seit dem Abrufen geändert. in diesem Fall schlägt der Vorgang fehl. Dieser Fehler soll verhindern, dass Ihre Anwendung versehentlich Änderungen aus anderen Quellen überschreibt.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a>Einfügen oder Ersetzen einer Entität

Manchmal wissen Sie nicht, ob eine Entität in der Tabelle vorhanden ist. Wenn dies der Fall ist, werden die darin gespeicherten aktuellen Werte nicht mehr benötigt. Sie können `InsertOrReplace` verwenden, um die Entität zu erstellen, oder Sie ersetzen, wenn Sie vorhanden ist, unabhängig von Ihrem Zustand.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a>Abfragen einer Teilmenge von Entitäts Eigenschaften

Eine Tabellen Abfrage kann nur einige wenige Eigenschaften aus einer Entität abrufen, anstatt Sie zu verwenden. Diese Technik, die als Projektion bezeichnet wird, kann die Abfrageleistung verbessern, insbesondere bei großen Entitäten. Hier geben Sie nur e-Mail-Adressen mit `DynamicTableEntity` und `EntityResolver` zurück. Beachten Sie, dass die Projektion nicht auf dem lokalen Speicher Emulator unterstützt wird, sodass dieser Code nur ausgeführt wird, wenn Sie ein Konto für den Tabellen Speicherdienst verwenden.

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

Sie können eine Tabelle aus einem Speicherkonto löschen. Eine Tabelle, die gelöscht wurde, kann für einen bestimmten Zeitraum nach dem Löschvorgang nicht neu erstellt werden.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie sich nun mit den Grundlagen von Table Storage vertraut gemacht haben, folgen Sie diesen Links, um mehr über komplexere Speicher Aufgaben und die Azure Cosmos DB Tabellen-API zu erfahren.

- [Einführung in Azure Cosmos DB Tabellen-API](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [Referenz zur Speicher Client Bibliothek für .net](https://docs.microsoft.com/dotnet/api/overview/azure/storage)
- [Azure Storage Typanbieter](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [Azure Storage Teamblog](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Verbindungs Zeichenfolgen konfigurieren](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
