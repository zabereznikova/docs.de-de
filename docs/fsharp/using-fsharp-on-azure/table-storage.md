---
title: Erste Schritte mit Azure-Tabellenspeicher mit f#
description: Speichern Sie strukturierte Daten in der Cloud mit Azure Table Storage oder Azure-Cosmos-Datenbank.
keywords: Visual f#, f#, funktionalen Programmierung, .NET, .NET Core, Azure
author: sylvanc
ms.author: phcart
ms.date: 03/26/2018
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9e5d6cea-a98c-461e-a5cc-75f1d154eafd
ms.openlocfilehash: 6d40211e13e8d213aa5a40d585dd384abf49ddfa
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="a6e1e-104">Erste Schritte mit Azure-Tabellenspeicher und Azure Cosmos DB-Tabellen-API mit f#</span><span class="sxs-lookup"><span data-stu-id="a6e1e-104">Get started with Azure Table storage and the Azure Cosmos DB Table API using F#</span></span> # 

<span data-ttu-id="a6e1e-105">Azure-Tabellenspeicher ist ein Dienst, der strukturierte NoSQL-Daten in der Cloud gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-105">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="a6e1e-106">Tabellenspeicher ist ein Key-Attribut mit einem schemaless Entwurf.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-106">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="a6e1e-107">Da Table Storage schemaless ist, ist es einfach, Daten von Ihrer Anwendung Evolve sich Anforderungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-107">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="a6e1e-108">Zugriff auf Daten ist schnell und kostengünstig für alle Arten von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-108">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="a6e1e-109">Tabellenspeicher ist in der Regel deutlich niedriger Kosten als herkömmliche SQL für ähnliche Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-109">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="a6e1e-110">Sie können Tabellenspeicher zum Speichern von flexible Datasets, wie z. B. Benutzerdaten für Webanwendungen, Adressbücher Geräteinformationen und andere Arten von Metadaten, die Ihr Dienst erfordert, verwenden.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-110">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="a6e1e-111">Sie können eine beliebige Anzahl von Entitäten in einer Tabelle speichern, und ein Speicherkonto kann eine beliebige Anzahl von Tabellen, bis die Kapazitätsgrenze des Speicherkontos zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-111">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="a6e1e-112">Azure Cosmos-Datenbank bietet die Tabellendienst-API für Anwendungen, die für den Azure-Tabellenspeicher geschrieben sind und Premium-Funktionen wie z. B. erfordert:</span><span class="sxs-lookup"><span data-stu-id="a6e1e-112">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="a6e1e-113">Sofort verwendbare globale Verteilung.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-113">Turnkey global distribution.</span></span>
- <span data-ttu-id="a6e1e-114">Dedizierte Durchsatz weltweit.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-114">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="a6e1e-115">Einstellige Millisekunde Wartezeiten bei 99 Prozent entsprachen.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-115">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="a6e1e-116">Ist die hohen Verfügbarkeit gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-116">Guaranteed high availability.</span></span>
- <span data-ttu-id="a6e1e-117">Automatische sekundären indizieren.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-117">Automatic secondary indexing.</span></span>

<span data-ttu-id="a6e1e-118">Anwendungen für Azure-Tabellenspeicher können Migrieren zu Azure-Cosmos-Datenbank mithilfe der Tabellendienst-API ohne codeänderungen und Premium-Funktionen nutzen.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-118">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="a6e1e-119">Die Tabellendienst-API hat verfügbaren Client-SDKs für .NET, Java, Python und Node.js.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-119">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="a6e1e-120">Weitere Informationen finden Sie unter [Einführung in Azure Cosmos DB Tabellendienst-API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span><span class="sxs-lookup"><span data-stu-id="a6e1e-120">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="a6e1e-121">Zu diesem Lernprogramm</span><span class="sxs-lookup"><span data-stu-id="a6e1e-121">About this tutorial</span></span>

<span data-ttu-id="a6e1e-122">Dieses Lernprogramm zeigt, wie F#-Code werden einige häufig auszuführende Aufgaben mithilfe von Azure-Tabellenspeicher oder die Azure Cosmos DB Tabelle-API, einschließlich erstellen und Löschen einer Tabelle und einfügen, aktualisieren, löschen und Abfragen von Daten aus Tabellen schreiben.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-122">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a6e1e-123">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="a6e1e-123">Prerequisites</span></span>

<span data-ttu-id="a6e1e-124">Um dieser Anleitung zu verwenden, müssen Sie zuerst [Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account) oder [Azure Cosmos-DB-Konto](https://azure.microsoft.com/try/cosmosdb/).</span><span class="sxs-lookup"><span data-stu-id="a6e1e-124">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>


## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="a6e1e-125">Erstellen Sie ein f#-Skript und Start f# Interactive</span><span class="sxs-lookup"><span data-stu-id="a6e1e-125">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="a6e1e-126">Die Beispiele in diesem Artikel können in einer f#-Anwendung oder ein F#-Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-126">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="a6e1e-127">Um ein F#-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `tables.fsx`, in der f#-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-127">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="a6e1e-128">Verwenden Sie als Nächstes eine [Paket-Manager](package-management.md) wie z. B. [Paket](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` Paket und Verweis `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-128">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="a6e1e-129">Führen Sie ihn erneut für `Microsoft.WindowsAzure.ConfigurationManager` ändern, um den Namespace Microsoft.Azure zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-129">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="a6e1e-130">Fügen Sie Namespacedeklarationen hinzu</span><span class="sxs-lookup"><span data-stu-id="a6e1e-130">Add namespace declarations</span></span>

<span data-ttu-id="a6e1e-131">Fügen Sie die folgenden `open` Anweisungen am oberen Rand der `tables.fsx` Datei:</span><span class="sxs-lookup"><span data-stu-id="a6e1e-131">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="a6e1e-132">Abrufen der Verbindungszeichenfolge des Azure-Speicher</span><span class="sxs-lookup"><span data-stu-id="a6e1e-132">Get your Azure Storage connection string</span></span>

<span data-ttu-id="a6e1e-133">Wenn Sie Azure-Speichertabelle-Dienst herstellen, benötigen Sie die Verbindungszeichenfolge für dieses Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-133">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="a6e1e-134">Sie können die Verbindungszeichenfolge aus der Azure-Portal kopieren.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-134">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="a6e1e-135">Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Speicherverbindungs-Zeichenfolgen konfigurieren](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="a6e1e-135">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="a6e1e-136">Abrufen der Azure-Cosmos-DB-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a6e1e-136">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="a6e1e-137">Wenn Sie mit der Azure-Cosmos-Datenbank herstellen, benötigen Sie die Verbindungszeichenfolge für dieses Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-137">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="a6e1e-138">Sie können die Verbindungszeichenfolge aus der Azure-Portal kopieren.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-138">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="a6e1e-139">Im Azure-Portal, in Ihrem Konto Cosmos-DB, wechseln Sie zu **Einstellungen** > **Verbindungszeichenfolge**, und klicken Sie auf die **Kopie** , um die primäre Verbindung zu kopieren. Eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-139">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="a6e1e-140">Geben Sie für das Lernprogramm für die Verbindungszeichenfolge in Ihrem Skript verwenden, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a6e1e-140">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="a6e1e-141">Dies ist jedoch **nicht empfohlen,** für tatsächliche Projekte.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-141">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="a6e1e-142">Schlüssel für das Speicherkonto ähnelt das Stammkennwort für Ihr Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-142">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="a6e1e-143">Achten Sie stets darauf zum Schützen der Schlüssel für das Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-143">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="a6e1e-144">Vermeiden Sie verteilen an andere Benutzer, die eine feste Programmierung, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-144">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="a6e1e-145">Sie können erneut zu generieren Ihres Schlüssels im Azure-Portal verwenden, wenn Sie glauben, dass er gefährdet sein kann.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-145">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="a6e1e-146">Für echten Anwendungen ist die beste Methode zum Verwalten Ihrer speicherverbindungs-Zeichenfolge in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-146">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="a6e1e-147">Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie dies tun:</span><span class="sxs-lookup"><span data-stu-id="a6e1e-147">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="a6e1e-148">Mit Azure-Konfigurations-Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-148">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="a6e1e-149">Sie können auch eine API wie das .NET Framework `ConfigurationManager` Typ.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-149">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="a6e1e-150">Analysieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="a6e1e-150">Parse the connection string</span></span>

<span data-ttu-id="a6e1e-151">Verwenden Sie, um die Verbindungszeichenfolge zu analysieren:</span><span class="sxs-lookup"><span data-stu-id="a6e1e-151">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="a6e1e-152">Dies gibt eine `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-152">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="a6e1e-153">Erstellen Sie den tabellendienstclient</span><span class="sxs-lookup"><span data-stu-id="a6e1e-153">Create the Table service client</span></span>

<span data-ttu-id="a6e1e-154">Die `CloudTableClient` -Klasse können Sie Tabellen und Entitäten im Tabellenspeicher abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-154">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="a6e1e-155">Dies ist eine Methode zum Erstellen des Service-Clients:</span><span class="sxs-lookup"><span data-stu-id="a6e1e-155">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="a6e1e-156">Jetzt können Sie Code schreiben, liest Daten aus und schreibt Daten in den Tabellenspeicher.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-156">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="a6e1e-157">Erstellen Sie eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="a6e1e-157">Create a table</span></span>

<span data-ttu-id="a6e1e-158">Dieses Beispiel zeigt, wie eine Tabelle erstellt, wenn sie nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="a6e1e-158">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="a6e1e-159">Hinzufügen einer Entität zu einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="a6e1e-159">Add an entity to a table</span></span>

<span data-ttu-id="a6e1e-160">Eine Entität muss einen Typ aufweisen, die von erben `TableEntity`.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-160">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="a6e1e-161">Sie erweitern können `TableEntity` in beliebig, aber Ihr Typ *müssen* einen parameterlosen Konstruktor aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-161">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="a6e1e-162">Nur Eigenschaften, die sowohl `get` und `set` in Ihrem Azure-Tabelle gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-162">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="a6e1e-163">Eine Entität Partitions- und Zeilenschlüssel ist die Entität in der Tabelle eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-163">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="a6e1e-164">Entitäten mit den gleichen Partitionsschlüssel können schneller als mit anderen Partitionsschlüssel abgefragt werden, jedoch mit unterschiedlichen Partitionsschlüssel für eine höhere Skalierbarkeit von parallelen Vorgängen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-164">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="a6e1e-165">Hier ist ein Beispiel für eine `Customer` , verwendet der `lastName` als Partitionsschlüssel und `firstName` als Zeilenschlüssel.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-165">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="a6e1e-166">Fügen Sie jetzt `Customer` der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-166">Now add `Customer` to the table.</span></span> <span data-ttu-id="a6e1e-167">Zu diesem Zweck erstellen Sie eine `TableOperation` , das für die Tabelle ausführt.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-167">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="a6e1e-168">In diesem Fall erstellen Sie ein `Insert` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-168">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="a6e1e-169">Einfügen eines entitätenbatches</span><span class="sxs-lookup"><span data-stu-id="a6e1e-169">Insert a batch of entities</span></span>

<span data-ttu-id="a6e1e-170">Sie können einen entitätenbatch in einer Tabelle mit einem einzelnen Schreibvorgang einfügen.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-170">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="a6e1e-171">Batchvorgänge ermöglichen es Ihnen, Vorgänge in eine einzelne Ausführung zu kombinieren, verfügen jedoch über einige Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="a6e1e-171">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="a6e1e-172">Sie können Updates ausführen löscht, und fügt Sie in einem Batchvorgang.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-172">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="a6e1e-173">Ein Batchvorgang kann bis zu 100 Entitäten enthalten.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-173">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="a6e1e-174">Alle Entitäten in einem Batchvorgang müssen den gleichen Partitionsschlüssel haben.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-174">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="a6e1e-175">Es ist, zwar möglich, eine Abfrage in einem Batchvorgang auszuführen muss es die einzige Vorgang im Batch sein.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-175">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="a6e1e-176">Hier ist Teil des Codes, die zwei einfügungen in einem Batchvorgang kombiniert:</span><span class="sxs-lookup"><span data-stu-id="a6e1e-176">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="a6e1e-177">Rufen Sie aller Entitäten in einer Partition ab</span><span class="sxs-lookup"><span data-stu-id="a6e1e-177">Retrieve all entities in a partition</span></span>

<span data-ttu-id="a6e1e-178">Verwenden Sie zum Abfragen einer Tabelle für alle Entitäten in einer Partition, eine `TableQuery` Objekt.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-178">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="a6e1e-179">Hier ist filtern Sie für Entitäten, wobei der Partitionsschlüssel ist "Smith".</span><span class="sxs-lookup"><span data-stu-id="a6e1e-179">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="a6e1e-180">Jetzt werden die Ergebnisse drucken:</span><span class="sxs-lookup"><span data-stu-id="a6e1e-180">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="a6e1e-181">Rufen Sie einen Bereich von Entitäten in einer partition</span><span class="sxs-lookup"><span data-stu-id="a6e1e-181">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="a6e1e-182">Wenn Sie nicht alle Entitäten in einer Partition abfragen möchten, können Sie einen Bereich angeben, durch die Kombination der Filter der Partition Schlüssel mit einem Schlüssel Zeilenfilter.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-182">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="a6e1e-183">Hier verwenden Sie zwei Filter alle Entitäten in der Partition "Smith" abgerufen, in der Zeilenschlüssel (Rufname) früher als "M" im Alphabet mit einem Buchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-183">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="a6e1e-184">Jetzt werden die Ergebnisse drucken:</span><span class="sxs-lookup"><span data-stu-id="a6e1e-184">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="a6e1e-185">Abrufen einer einzelnen Entität</span><span class="sxs-lookup"><span data-stu-id="a6e1e-185">Retrieve a single entity</span></span>

<span data-ttu-id="a6e1e-186">Sie können eine Abfrage zum Abrufen einer bestimmten Entität schreiben.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-186">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="a6e1e-187">Verwenden Sie hier eine `TableOperation` an den Kunden "Ben Smith".</span><span class="sxs-lookup"><span data-stu-id="a6e1e-187">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="a6e1e-188">Statt einer Auflistung erhalten Sie wieder eine `Customer`.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-188">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="a6e1e-189">Der Partitionsschlüssel und Zeilenschlüssel in einer Abfrage angegeben, ist die schnellste Möglichkeit zum Abrufen einer einzelnen Entität aus dem Tabellendienst.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-189">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="a6e1e-190">Jetzt werden die Ergebnisse drucken:</span><span class="sxs-lookup"><span data-stu-id="a6e1e-190">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


### <a name="replace-an-entity"></a><span data-ttu-id="a6e1e-191">Ersetzen einer Entität</span><span class="sxs-lookup"><span data-stu-id="a6e1e-191">Replace an entity</span></span>

<span data-ttu-id="a6e1e-192">Zum Aktualisieren einer Entität aus der Tabellendienst abrufen, das Entitätsobjekt ändern und speichern Sie die Änderungen an der Tabelle mit einer `Replace` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-192">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="a6e1e-193">Dies bewirkt, dass die Entität, die auf dem Server vollständig ersetzt werden, es sei denn, die Entität, auf dem Server geändert wurde, seit sie abgerufen wurde, in diesem Fall schlägt der Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-193">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="a6e1e-194">Dieser Fehler wird verhindert, dass die Anwendung von Änderungen aus anderen Quellen versehentlich überschrieben.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-194">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="a6e1e-195">INSERT-oder-Ersetzen einer Entität</span><span class="sxs-lookup"><span data-stu-id="a6e1e-195">Insert-or-replace an entity</span></span>

<span data-ttu-id="a6e1e-196">In einigen Fällen, wissen Sie nicht, ob eine Entität in der Tabelle vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-196">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="a6e1e-197">Und wenn dies der Fall ist, werden die aktuellen Werte, die darin gespeicherten nicht mehr benötigt.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-197">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="a6e1e-198">Sie können `InsertOrReplace` zum Erstellen der Entität oder Ersetzen Sie ihn, falls es vorhanden, unabhängig von ihrem Status ist.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-198">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="a6e1e-199">Die Abfrage eine Teilmenge von Entitätseigenschaften</span><span class="sxs-lookup"><span data-stu-id="a6e1e-199">Query a subset of entity properties</span></span>

<span data-ttu-id="a6e1e-200">Eine Table-Abfrage kann aus einer Entität anstelle aller Textknoten nur wenige Eigenschaften abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-200">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="a6e1e-201">Diese Technik mit dem Namen Projektion kann, insbesondere bei großen Entitäten verbessern.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-201">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="a6e1e-202">Hier ist Sie zurückkehren nur e-Mail-Adressen mit `DynamicTableEntity` und `EntityResolver`.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-202">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="a6e1e-203">Beachten Sie, dass die Projektion auf den lokalen Speicheremulator nicht unterstützt wird, sodass dieser Code ausgeführt wird, nur, wenn Sie ein Konto für den Tabellendienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-203">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="a6e1e-204">Abrufen von Entitäten in Seiten asynchron</span><span class="sxs-lookup"><span data-stu-id="a6e1e-204">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="a6e1e-205">Wenn Sie eine große Anzahl von Entitäten lesen gerade und verarbeiten sie abgerufen werden, sondern wartet, bis sie alle zurückgeben, können Sie eine Abfrage segmentierte werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-205">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="a6e1e-206">Hier geben Sie Ergebnisse in Seiten mit einem asynchronen Workflow, damit die Ausführung nicht blockiert wird, während für eine große Anzahl der zurückzugebenden Ergebnisseite warten, können Sie zurück.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-206">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="a6e1e-207">Sie nun diese Berechnung synchron ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="a6e1e-207">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="a6e1e-208">Löschen einer Entität</span><span class="sxs-lookup"><span data-stu-id="a6e1e-208">Delete an entity</span></span>

<span data-ttu-id="a6e1e-209">Sie können eine Entität löschen, nachdem Sie es abgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-209">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="a6e1e-210">Wie bei der Aktualisierung einer Entität Fehler dies, wenn die Entität geändert wurde, seit Sie sie abgerufen.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-210">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="a6e1e-211">Löschen einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="a6e1e-211">Delete a table</span></span>

<span data-ttu-id="a6e1e-212">Sie können eine Tabelle aus einem Speicherkonto löschen.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-212">You can delete a table from a storage account.</span></span> <span data-ttu-id="a6e1e-213">Eine Tabelle, die gelöscht wurde ist nicht verfügbar für eine bestimmte Zeitdauer nach dem Löschvorgang neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-213">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="a6e1e-214">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a6e1e-214">Next steps</span></span>

<span data-ttu-id="a6e1e-215">Nun, dass Sie die Grundlagen des tabellenspeichers gelernt haben, führen Sie die folgenden Links, um weitere Informationen zu komplexeren Speicheraufgaben und die Tabellendienst-API von Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="a6e1e-215">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="a6e1e-216">Einführung in Azure-Cosmos-DB-Tabellen-API</span><span class="sxs-lookup"><span data-stu-id="a6e1e-216">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="a6e1e-217">Speicherclientbibliothek für .NET-Referenz</span><span class="sxs-lookup"><span data-stu-id="a6e1e-217">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="a6e1e-218">Azure-Speicher-Typanbieter</span><span class="sxs-lookup"><span data-stu-id="a6e1e-218">Azure Storage Type Provider</span></span>](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="a6e1e-219">Azure-Speicher-Teamblog</span><span class="sxs-lookup"><span data-stu-id="a6e1e-219">Azure Storage Team Blog</span></span>](http://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="a6e1e-220">Konfigurieren von Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="a6e1e-220">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="a6e1e-221">Erste Schritte mit Azure-Tabellenspeicher in .NET</span><span class="sxs-lookup"><span data-stu-id="a6e1e-221">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
