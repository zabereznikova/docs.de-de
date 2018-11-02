---
title: Erste Schritte mit Azure Table Storage mit F#
description: Store strukturierte Daten in der Cloud mit Azure Table Storage oder Azure Cosmos DB.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: 2d793ba8653833ff384f1824e303b08e05aba69b
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "43519534"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="7017d-103">Erste Schritte mit Azure Table Storage und Azure Cosmos DB Table API mit F#</span><span class="sxs-lookup"><span data-stu-id="7017d-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F#</span></span> # 

<span data-ttu-id="7017d-104">Azure Table Storage ist ein Dienst, der strukturierte NoSQL-Daten in der Cloud gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7017d-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="7017d-105">Table Storage ist ein Schlüssel-/Attributspeicher mit einem schemalosen Design.</span><span class="sxs-lookup"><span data-stu-id="7017d-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="7017d-106">Da der Tabellenspeicher schemalos ist, ist es einfach, Daten anzupassen, wenn sich die Anforderungen Ihrer Anwendung ändern.</span><span class="sxs-lookup"><span data-stu-id="7017d-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="7017d-107">Zugriff auf Daten ist schnell und kostengünstig für alle Arten von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="7017d-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="7017d-108">Table Storage ist in der Regel deutlich niedriger Kosten als herkömmliche SQL für ähnliche Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="7017d-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="7017d-109">Sie können Table Storage verwenden, um flexible Datasets wie Benutzerdaten für Webanwendungen, Adressbücher, Geräteinformationen und andere Typen von Metadaten, die Ihr Dienst erfordert, zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7017d-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="7017d-110">Sie können eine beliebige Anzahl von Entitäten in einer Tabelle speichern, und ein Speicherkonto kann eine beliebige Anzahl von Tabellen, die bis zur speicherkapazitätsgrenze des Speicherkontos enthalten.</span><span class="sxs-lookup"><span data-stu-id="7017d-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="7017d-111">Azure Cosmos DB bietet die Table-API für Anwendungen, die für Azure Table Storage geschrieben sind und, wie z. B. Premium-Funktionen erfordern:</span><span class="sxs-lookup"><span data-stu-id="7017d-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="7017d-112">Sofort einsatzbereite globale Verteilung.</span><span class="sxs-lookup"><span data-stu-id="7017d-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="7017d-113">Dedizierter Durchsatz, die weltweit.</span><span class="sxs-lookup"><span data-stu-id="7017d-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="7017d-114">Latenzen im einstelligen Millisekundenbereich im 99. Perzentil.</span><span class="sxs-lookup"><span data-stu-id="7017d-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="7017d-115">Garantierte hochverfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="7017d-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="7017d-116">Automatische sekundäre Indizierung.</span><span class="sxs-lookup"><span data-stu-id="7017d-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="7017d-117">Anwendungen für Azure Table Storage geschrieben wurden, können in Azure Cosmos DB mithilfe der Table-API ohne codeänderungen migrieren und profitieren Sie von Premium-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="7017d-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="7017d-118">Die Table-API enthält verfügbaren Client-SDKs für .NET, Java, Python und Node.js.</span><span class="sxs-lookup"><span data-stu-id="7017d-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="7017d-119">Weitere Informationen finden Sie unter [Einführung in die Table-API von Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span><span class="sxs-lookup"><span data-stu-id="7017d-119">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="7017d-120">Informationen zu diesem Lernprogramm</span><span class="sxs-lookup"><span data-stu-id="7017d-120">About this tutorial</span></span>

<span data-ttu-id="7017d-121">In diesem Tutorial veranschaulicht, wie F#-Code dazu durchführen allgemeinen Aufgaben mit Azure Table Storage oder Azure Cosmos DB Table API, einschließlich erstellen und Löschen einer Tabelle und einfügen, aktualisieren, löschen und Abfragen von Tabellendaten zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="7017d-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7017d-122">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7017d-122">Prerequisites</span></span>

<span data-ttu-id="7017d-123">Um dieses Handbuch verwenden zu können, müssen Sie zuerst [erstellen Sie ein Azure Storage-Konto](/azure/storage/storage-create-storage-account) oder [Azure Cosmos DB-Konto](https://azure.microsoft.com/try/cosmosdb/).</span><span class="sxs-lookup"><span data-stu-id="7017d-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>


## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="7017d-124">Erstellen Sie einen F#-Skript, und starten F# Interactive</span><span class="sxs-lookup"><span data-stu-id="7017d-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="7017d-125">In die Beispielen in diesem Artikel können in einer F#-Anwendung oder ein F#-Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7017d-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="7017d-126">Um ein F#-Skript zu erstellen, erstellen Sie eine Datei mit den `.fsx` Erweiterung, z. B. `tables.fsx`, in der F#-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="7017d-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="7017d-127">Verwenden Sie als Nächstes eine [-Paket-Manager](package-management.md) wie z. B. [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` Paket und Verweis `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="7017d-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="7017d-128">Führen Sie es noch mal `Microsoft.WindowsAzure.ConfigurationManager` um den Microsoft.Azure-Namespace zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7017d-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="7017d-129">Hinzufügen von Namespacedeklarationen</span><span class="sxs-lookup"><span data-stu-id="7017d-129">Add namespace declarations</span></span>

<span data-ttu-id="7017d-130">Fügen Sie die folgenden `open` Anweisungen am Anfang der `tables.fsx` Datei:</span><span class="sxs-lookup"><span data-stu-id="7017d-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="7017d-131">Die Azure Storage-Verbindungszeichenfolge abzurufen</span><span class="sxs-lookup"><span data-stu-id="7017d-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="7017d-132">Wenn Sie mit Azure Table Storage-Dienst verbinden, benötigen Sie die Verbindungszeichenfolge für dieses Tutorial.</span><span class="sxs-lookup"><span data-stu-id="7017d-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="7017d-133">Sie können die Verbindungszeichenfolge aus dem Azure-Portal kopieren.</span><span class="sxs-lookup"><span data-stu-id="7017d-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="7017d-134">Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Konfigurieren von Speicher-Verbindungszeichenfolgen](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="7017d-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="7017d-135">Die Azure Cosmos DB-Verbindungszeichenfolge abzurufen</span><span class="sxs-lookup"><span data-stu-id="7017d-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="7017d-136">Wenn Sie mit Azure Cosmos DB verbinden, benötigen Sie die Verbindungszeichenfolge für dieses Tutorial.</span><span class="sxs-lookup"><span data-stu-id="7017d-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="7017d-137">Sie können die Verbindungszeichenfolge aus dem Azure-Portal kopieren.</span><span class="sxs-lookup"><span data-stu-id="7017d-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="7017d-138">Navigieren Sie im Azure-Portal in Ihrem Cosmos DB-Konto zu **Einstellungen** > **Verbindungszeichenfolge**, und klicken Sie auf die **Kopie** , um die primäre Verbindung zu kopieren. Eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7017d-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="7017d-139">Geben Sie Ihre Verbindungszeichenfolge für das Tutorial in Ihrem Skript verwenden, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7017d-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="7017d-140">Dies ist jedoch **nicht empfohlen,** für echte Projekte.</span><span class="sxs-lookup"><span data-stu-id="7017d-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="7017d-141">Ihr speicherkontoschlüssel ähnelt das Stammkennwort für Ihr Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="7017d-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="7017d-142">Achten Sie immer darauf zum Schützen der Schlüssel Ihres Speicherkontos.</span><span class="sxs-lookup"><span data-stu-id="7017d-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="7017d-143">Vermeiden sie zu anderen Benutzern oder fest zu programmieren, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="7017d-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="7017d-144">Sie können Ihren Schlüssel mithilfe von Azure-Portal, wenn Sie glauben, dass es unter Umständen kompromittiert wurden neu generieren.</span><span class="sxs-lookup"><span data-stu-id="7017d-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="7017d-145">Für reale Anwendungen, ist die beste Methode zum Verwalten Ihrer Speicher-Verbindungszeichenfolge in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7017d-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="7017d-146">Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie so vorgehen:</span><span class="sxs-lookup"><span data-stu-id="7017d-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="7017d-147">Verwenden von Azure Configuration Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="7017d-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="7017d-148">Sie können auch eine API wie die .NET Framework `ConfigurationManager` Typ.</span><span class="sxs-lookup"><span data-stu-id="7017d-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="7017d-149">Analysieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7017d-149">Parse the connection string</span></span>

<span data-ttu-id="7017d-150">Um die Verbindungszeichenfolge zu analysieren, verwenden Sie:</span><span class="sxs-lookup"><span data-stu-id="7017d-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="7017d-151">Dies gibt eine `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="7017d-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="7017d-152">Erstellen des Tabellenspeicherdienst-Clients</span><span class="sxs-lookup"><span data-stu-id="7017d-152">Create the Table service client</span></span>

<span data-ttu-id="7017d-153">Die `CloudTableClient` -Klasse ermöglicht es Ihnen, Tabellen und Entitäten im Tabellenspeicher abrufen.</span><span class="sxs-lookup"><span data-stu-id="7017d-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="7017d-154">Hier ist eine Möglichkeit zum Erstellen des Dienstclients:</span><span class="sxs-lookup"><span data-stu-id="7017d-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="7017d-155">Jetzt können Sie Code schreiben, liest Daten aus und schreibt Daten in Table Storage.</span><span class="sxs-lookup"><span data-stu-id="7017d-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="7017d-156">Erstellen einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="7017d-156">Create a table</span></span>

<span data-ttu-id="7017d-157">Dieses Beispiel zeigt, wie Sie eine Tabelle zu erstellen, wenn es nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="7017d-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="7017d-158">Hinzufügen einer Entität zu einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="7017d-158">Add an entity to a table</span></span>

<span data-ttu-id="7017d-159">Eine Entität muss einen Typ aufweisen, die von erbt `TableEntity`.</span><span class="sxs-lookup"><span data-stu-id="7017d-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="7017d-160">Sie können die erweitern `TableEntity` beliebig, aber der Typ *müssen* einen parameterlosen Konstruktor aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7017d-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="7017d-161">Nur Eigenschaften, die sowohl `get` und `set` in Ihrem Azure-Tabelle gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="7017d-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="7017d-162">Eine Entität des Partitions- und Zeilenschlüssel identifiziert eindeutig die Entität in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7017d-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="7017d-163">Entitäten mit demselben Partitionsschlüssel können schneller abgerufen werden als Entitäten mit verschiedenen partitionsschlüsseln, aber die Verwendung verschiedener Partitionsschlüssel ermöglicht größere Skalierbarkeit paralleler Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="7017d-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="7017d-164">Hier ist ein Beispiel für eine `Customer` , verwendet der `lastName` als Partitionsschlüssel und die `firstName` als Zeilenschlüssel.</span><span class="sxs-lookup"><span data-stu-id="7017d-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="7017d-165">Fügen Sie jetzt hinzu `Customer` in die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7017d-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="7017d-166">Zu diesem Zweck erstellen Sie eine `TableOperation` , für die Tabelle ausführt.</span><span class="sxs-lookup"><span data-stu-id="7017d-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="7017d-167">In diesem Fall erstellen Sie eine `Insert` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="7017d-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="7017d-168">Einfügen eines entitätsbatchs</span><span class="sxs-lookup"><span data-stu-id="7017d-168">Insert a batch of entities</span></span>

<span data-ttu-id="7017d-169">Sie können einen entitätsbatch in einer Tabelle mit einem einzelnen Schreibvorgang einfügen.</span><span class="sxs-lookup"><span data-stu-id="7017d-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="7017d-170">Batch-Vorgänge ermöglichen es Ihnen, Vorgänge in eine einzelne Ausführung zu kombinieren, verfügen jedoch über einige Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="7017d-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="7017d-171">Sie können Updates ausführen Lösch- und Einfügevorgänge in einem Batchvorgang.</span><span class="sxs-lookup"><span data-stu-id="7017d-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="7017d-172">Ein Batchvorgang kann bis zu 100 Entitäten enthalten.</span><span class="sxs-lookup"><span data-stu-id="7017d-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="7017d-173">Alle Entitäten in einem Batchvorgang müssen den gleichen Partitionsschlüssel aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7017d-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="7017d-174">Es ist, zwar möglich, eine Abfrage in einem Batchvorgang auszuführen muss es der einzige Vorgang im Batch sein.</span><span class="sxs-lookup"><span data-stu-id="7017d-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="7017d-175">Hier ist Code, der zwei Einfügevorgänge in einem Batchvorgang kombiniert:</span><span class="sxs-lookup"><span data-stu-id="7017d-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="7017d-176">Rufen Sie aller Entitäten in einer Partition ab</span><span class="sxs-lookup"><span data-stu-id="7017d-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="7017d-177">Um eine Tabelle für alle Entitäten in einer Partition abzufragen, verwenden eine `TableQuery` Objekt.</span><span class="sxs-lookup"><span data-stu-id="7017d-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="7017d-178">Hier filtern Sie Entitäten, wobei "Smith" der Partitionsschlüssel ist.</span><span class="sxs-lookup"><span data-stu-id="7017d-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="7017d-179">Sie werden nun die Ergebnisse drucken:</span><span class="sxs-lookup"><span data-stu-id="7017d-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="7017d-180">Abrufen eines entitätsbereichs in einer partition</span><span class="sxs-lookup"><span data-stu-id="7017d-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="7017d-181">Wenn Sie nicht alle Entitäten in einer Partition abrufen möchten, können Sie einen Bereich angeben, indem Sie den partitionsschlüsselfilter mit einem zeilenschlüsselfilter kombinieren.</span><span class="sxs-lookup"><span data-stu-id="7017d-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="7017d-182">Hier verwenden Sie zwei Filter auf alle Entitäten in der Partition "Smith" abzurufen, in dem der Zeilenschlüssel (Vorname) mit einem Buchstaben vor "M" im Alphabet beginnt.</span><span class="sxs-lookup"><span data-stu-id="7017d-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="7017d-183">Sie werden nun die Ergebnisse drucken:</span><span class="sxs-lookup"><span data-stu-id="7017d-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="7017d-184">Abrufen einer einzelnen Entität</span><span class="sxs-lookup"><span data-stu-id="7017d-184">Retrieve a single entity</span></span>

<span data-ttu-id="7017d-185">Sie können eine Abfrage zum Abrufen einer bestimmten Entität schreiben.</span><span class="sxs-lookup"><span data-stu-id="7017d-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="7017d-186">Hier ein `TableOperation` um den Kunden "Ben Smith" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7017d-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="7017d-187">Anstatt einer Sammlung, erhalten Sie wieder eine `Customer`.</span><span class="sxs-lookup"><span data-stu-id="7017d-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="7017d-188">Sowohl der Partitionsschlüssel und Zeilenschlüssel angeben, in einer Abfrage ist die schnellste Möglichkeit, eine einzelne Entität aus dem Tabellendienst abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7017d-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="7017d-189">Sie werden nun die Ergebnisse drucken:</span><span class="sxs-lookup"><span data-stu-id="7017d-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


### <a name="replace-an-entity"></a><span data-ttu-id="7017d-190">Ersetzen einer Entität</span><span class="sxs-lookup"><span data-stu-id="7017d-190">Replace an entity</span></span>

<span data-ttu-id="7017d-191">Um eine Entität zu aktualisieren, rufen Sie sie aus dem Tabellendienst, ändern Sie das Entitätsobjekt und speichern Sie die Änderungen an den Tabellenspeicherdienst mit einem `Replace` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="7017d-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="7017d-192">Dies bewirkt, dass die Entität, die auf dem Server vollständig ersetzt werden, es sei denn, der die Entität, auf dem Server geändert wurde, seit sie abgerufen wurde, in diesem Fall schlägt der Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="7017d-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="7017d-193">Um zu verhindern, dass Ihre Anwendung von versehentlich überschriebenen Änderungen aus anderen Quellen für diesen Fehler ist.</span><span class="sxs-lookup"><span data-stu-id="7017d-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="7017d-194">Einfügen-oder-Ersetzen einer Entität</span><span class="sxs-lookup"><span data-stu-id="7017d-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="7017d-195">In einigen Fällen wissen Sie nicht, ob eine Entität in der Tabelle vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7017d-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="7017d-196">Und wenn dies der Fall ist, werden die aktuellen Werte, die darin gespeicherten nicht mehr benötigt.</span><span class="sxs-lookup"><span data-stu-id="7017d-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="7017d-197">Sie können `InsertOrReplace` zum Erstellen der Entitäts oder Ersetzen Sie ihn, falls es vorhanden, unabhängig von ihrem Status ist.</span><span class="sxs-lookup"><span data-stu-id="7017d-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="7017d-198">Abfragen einer Teilmenge von Entitätseigenschaften</span><span class="sxs-lookup"><span data-stu-id="7017d-198">Query a subset of entity properties</span></span>

<span data-ttu-id="7017d-199">Eine Tabellenabfrage kann nur einige Eigenschaften aus einer Entität anstelle aller Textknoten abrufen.</span><span class="sxs-lookup"><span data-stu-id="7017d-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="7017d-200">Diese Technik, die sogenannten Projektion, kann die abfrageleistung, besonders bei großen Entitäten verbessern.</span><span class="sxs-lookup"><span data-stu-id="7017d-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="7017d-201">Hier ist Sie zurückkehren, nur e-Mail-Adressen, mit `DynamicTableEntity` und `EntityResolver`.</span><span class="sxs-lookup"><span data-stu-id="7017d-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="7017d-202">Beachten Sie, dass Projektion nicht auf dem lokalen Speicheremulator unterstützt wird, damit dieser Code ausgeführt wird, nur, wenn Sie ein Konto für den Tabellendienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="7017d-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="7017d-203">Abrufen von Entitäten in Seiten asynchron</span><span class="sxs-lookup"><span data-stu-id="7017d-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="7017d-204">Wenn Sie eine große Anzahl von Entitäten lesen und für die Verarbeitung warten, bis sie alle zurückgeben, können Sie eine segmentierte Abfrage verwenden, anstatt sie abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7017d-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="7017d-205">Hier ist zurückgeben Sie Ergebnisse seitenweise mithilfe eines asynchronen Workflows, damit die Ausführung nicht blockiert wird, während Sie für eine große Anzahl zurückzugebender Ergebnisse warten.</span><span class="sxs-lookup"><span data-stu-id="7017d-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="7017d-206">Sie führen Sie nun diese Berechnung synchron:</span><span class="sxs-lookup"><span data-stu-id="7017d-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="7017d-207">Löschen einer Entität</span><span class="sxs-lookup"><span data-stu-id="7017d-207">Delete an entity</span></span>

<span data-ttu-id="7017d-208">Sie können eine Entität löschen, nachdem Sie es abgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="7017d-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="7017d-209">Wie bei der Aktualisierung einer Entitätstyps Fehler dies, wenn die Entität geändert wurde, seitdem Sie abgerufen.</span><span class="sxs-lookup"><span data-stu-id="7017d-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="7017d-210">Löschen einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="7017d-210">Delete a table</span></span>

<span data-ttu-id="7017d-211">Sie können eine Tabelle aus einem Speicherkonto löschen.</span><span class="sxs-lookup"><span data-stu-id="7017d-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="7017d-212">Eine Tabelle, die gelöscht wurde, werden als nicht verfügbar für eine bestimmte Zeitdauer nach dem Löschvorgang neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7017d-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="7017d-213">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7017d-213">Next steps</span></span>

<span data-ttu-id="7017d-214">Nun, da Sie die Grundlagen von Table Storage vertraut gemacht haben, führen Sie diesen Links Weitere Informationen zu komplexeren Speicheraufgaben und der Azure Cosmos DB-Tabellen-API.</span><span class="sxs-lookup"><span data-stu-id="7017d-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="7017d-215">Einführung in Azure Cosmos DB-Tabellen-API</span><span class="sxs-lookup"><span data-stu-id="7017d-215">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="7017d-216">Storage-Clientbibliothek für .NET-Referenz</span><span class="sxs-lookup"><span data-stu-id="7017d-216">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="7017d-217">Azure-Speicher-Typanbieter</span><span class="sxs-lookup"><span data-stu-id="7017d-217">Azure Storage Type Provider</span></span>](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="7017d-218">Azure Storage-Teamblog</span><span class="sxs-lookup"><span data-stu-id="7017d-218">Azure Storage Team Blog</span></span>](https://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="7017d-219">Konfigurieren von Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="7017d-219">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="7017d-220">Erste Schritte mit Azure Table Storage in .NET</span><span class="sxs-lookup"><span data-stu-id="7017d-220">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
