---
title: 'Beginnen Sie mit der Verwendung von Azure Table Storage mit F #'
description: Speichern Sie strukturierte Daten in der Cloud mithilfe von Azure Table Storage oder Azure Cosmos DB.
author: sylvanc
ms.date: 03/26/2018
ms.custom: devx-track-fsharp
ms.openlocfilehash: bc8e111636013930f7c7d4f59d1ef0720298cb9f
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899281"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="6e5e2-103">Beginnen Sie mit der Verwendung von Azure Table Storage und der Azure Cosmos DB Tabellen-API mit F\#</span><span class="sxs-lookup"><span data-stu-id="6e5e2-103">Get started with Azure Table Storage and the Azure Cosmos DB Table API using F\#</span></span>

<span data-ttu-id="6e5e2-104">Bei Azure Table Storage handelt es sich um einen Dienst, der strukturierte nosql-Daten in der Cloud speichert.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-104">Azure Table Storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="6e5e2-105">Bei Table Storage handelt es sich um einen Schlüssel-/Attributspeicher mit einem schemalosen Design.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="6e5e2-106">Aufgrund der Schemalosigkeit von Table Storage ist es einfach, Ihre Daten an die Entwicklung Ihrer Anwendungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="6e5e2-107">Der Datenzugriff ist für alle Arten von Anwendungen schnell und kostengünstig.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="6e5e2-108">Table Storage ist in der Regel erheblich günstiger als herkömmliche SQL-Lösungen für ähnliche Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="6e5e2-109">Mit Table Storage können Sie flexible Datasets wie Benutzerdaten für Webanwendungen, Adressbücher, Geräteinformationen und jegliche Art von Metadaten speichern, die Ihr Dienst erfordert.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="6e5e2-110">Sie können eine beliebige Anzahl von Entitäten in einer Tabelle speichern, und ein Speicherkonto kann eine beliebige Anzahl von Tabellen enthalten (bis zur Speicherkapazitätsgrenze eines Speicherkontos).</span><span class="sxs-lookup"><span data-stu-id="6e5e2-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="6e5e2-111">Azure Cosmos DB stellt die Tabellen-API für Anwendungen bereit, die für Azure Table Storage geschrieben wurden und für die Premium-Funktionen erforderlich sind, wie z.b.:</span><span class="sxs-lookup"><span data-stu-id="6e5e2-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table Storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="6e5e2-112">Globale, sofort einsatzbereite Verteilung</span><span class="sxs-lookup"><span data-stu-id="6e5e2-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="6e5e2-113">Dedizierter Durchsatz weltweit.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="6e5e2-114">Einstellige Latenzzeiten im Millisekundenbereich im 99. Perzentil.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="6e5e2-115">Garantierte Hochverfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="6e5e2-116">Automatische sekundäre Indizierung</span><span class="sxs-lookup"><span data-stu-id="6e5e2-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="6e5e2-117">Anwendungen, die für Azure Table Storage geschrieben wurden, können mithilfe der Tabellen-API ohne Codeänderungen zu Azure Cosmos DB migrieren und die Vorteile von Premium-Funktionen nutzen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-117">Applications written for Azure Table Storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="6e5e2-118">Die Tabellen-API verfügt über Client-SDKs, die für .NET, Java, Python und Node.js verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="6e5e2-119">Weitere Informationen finden Sie unter [Einführung in Azure Cosmos DB Tabellen-API](/azure/cosmos-db/table-introduction).</span><span class="sxs-lookup"><span data-stu-id="6e5e2-119">For more information, see [Introduction to Azure Cosmos DB Table API](/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="6e5e2-120">Informationen zu diesem Tutorial</span><span class="sxs-lookup"><span data-stu-id="6e5e2-120">About this tutorial</span></span>

<span data-ttu-id="6e5e2-121">In diesem Tutorial wird gezeigt, wie Sie F #-Code schreiben, um einige gängige Aufgaben mithilfe von Azure Table Storage oder der Azure Cosmos DB Tabellen-API auszuführen, einschließlich dem Erstellen und Löschen einer Tabelle sowie dem Einfügen, aktualisieren, löschen und Abfragen von Tabellendaten.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-121">This tutorial shows how to write F# code to do some common tasks using Azure Table Storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6e5e2-122">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6e5e2-122">Prerequisites</span></span>

<span data-ttu-id="6e5e2-123">Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure-Speicherkonto](/azure/storage/storage-create-storage-account) oder [Azure Cosmos DB Konto](https://azure.microsoft.com/try/cosmosdb/)erstellen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="6e5e2-124">Erstellen eines F #-Skripts und starten F# Interactive</span><span class="sxs-lookup"><span data-stu-id="6e5e2-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="6e5e2-125">Die Beispiele in diesem Artikel können in einer f #-Anwendung oder einem f #-Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="6e5e2-126">Um ein F #-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z `tables.fsx` . b. in ihrer F #-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="6e5e2-127">Verwenden Sie als nächstes einen [Paket-Manager](package-management.md) , z. b. [Paket](https://fsprojects.github.io/Paket/) oder [nuget](https://www.nuget.org/) , um das Paket zu installieren, `WindowsAzure.Storage` und verweisen `WindowsAzure.Storage.dll` Sie mithilfe einer-Anweisung in Ihrem Skript `#r`</span><span class="sxs-lookup"><span data-stu-id="6e5e2-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="6e5e2-128">Führen Sie es erneut aus `Microsoft.WindowsAzure.ConfigurationManager` , um den Microsoft. Azure-Namespace zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="6e5e2-129">Hinzufügen von Namespace-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="6e5e2-129">Add namespace declarations</span></span>

<span data-ttu-id="6e5e2-130">Fügen Sie am Anfang der Datei `tables.fsx` die folgenden `open`-Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="6e5e2-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="6e5e2-131">Azure Storage Verbindungs Zeichenfolge erhalten</span><span class="sxs-lookup"><span data-stu-id="6e5e2-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="6e5e2-132">Wenn Sie eine Verbindung mit Azure Storage Tabellen Dienst herstellen, benötigen Sie die Verbindungs Zeichenfolge für dieses Tutorial.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="6e5e2-133">Sie können die Verbindungs Zeichenfolge aus der Azure-Portal kopieren.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="6e5e2-134">Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="6e5e2-135">Azure Cosmos DB Verbindungs Zeichenfolge erhalten</span><span class="sxs-lookup"><span data-stu-id="6e5e2-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="6e5e2-136">Wenn Sie eine Verbindung mit Azure Cosmos DB herstellen, benötigen Sie die Verbindungs Zeichenfolge für dieses Tutorial.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="6e5e2-137">Sie können die Verbindungs Zeichenfolge aus der Azure-Portal kopieren.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="6e5e2-138">Wechseln Sie in der Azure-Portal in Ihrem Cosmos DB Konto zu **Einstellungen**  >  **Verbindungs Zeichenfolge**, und klicken Sie auf die Schaltfläche **Kopieren** , um die primäre Verbindungs Zeichenfolge zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and select the **Copy** button to copy your Primary Connection String.</span></span>

<span data-ttu-id="6e5e2-139">Geben Sie für das Tutorial die Verbindungs Zeichenfolge in Ihrem Skript ein, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6e5e2-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="6e5e2-140">Dies wird jedoch nicht für echte Projekte **empfohlen** .</span><span class="sxs-lookup"><span data-stu-id="6e5e2-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="6e5e2-141">Ihr Speicherkontoschlüssel ähnelt dem Stammkennwort für das Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="6e5e2-142">Achten Sie darauf, den Speicherkontoschlüssel immer gut zu schützen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="6e5e2-143">Geben Sie ihn nicht an andere Benutzer weiter, vermeiden Sie das Hartcodieren, und speichern Sie ihn nicht in einer Klartextdatei, auf die andere Benutzer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="6e5e2-144">Wenn Sie der Meinung sind, dass der Schlüssel möglicherweise kompromittiert wurde, können Sie den Schlüssel mit dem Azure-Portal neu generieren</span><span class="sxs-lookup"><span data-stu-id="6e5e2-144">You can regenerate your key using the Azure portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="6e5e2-145">Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="6e5e2-146">Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="6e5e2-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="6e5e2-147">Die Verwendung von Azure Configuration Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="6e5e2-148">Sie können auch eine API verwenden, z. b. den Typ der .NET Framework `ConfigurationManager` .</span><span class="sxs-lookup"><span data-stu-id="6e5e2-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="6e5e2-149">Analysieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6e5e2-149">Parse the connection string</span></span>

<span data-ttu-id="6e5e2-150">Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6e5e2-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="6e5e2-151">Gibt einen zurück `CloudStorageAccount` .</span><span class="sxs-lookup"><span data-stu-id="6e5e2-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="6e5e2-152">Erstellen des Tabellenspeicherdienst-Clients</span><span class="sxs-lookup"><span data-stu-id="6e5e2-152">Create the Table service client</span></span>

<span data-ttu-id="6e5e2-153">Mit der- `CloudTableClient` Klasse können Sie Tabellen und Entitäten im Tabellen Speicher abrufen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="6e5e2-154">Hier sehen Sie eine Möglichkeit zum Erstellen des Dienstclients:</span><span class="sxs-lookup"><span data-stu-id="6e5e2-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="6e5e2-155">Jetzt können Sie Code schreiben, der Daten aus dem Tabellenspeicher liest und Daten in den Tabellenspeicher schreibt.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="6e5e2-156">Erstellen einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="6e5e2-156">Create a table</span></span>

<span data-ttu-id="6e5e2-157">Dieses Beispiel zeigt, wie Sie eine Tabelle erstellen, falls sie nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="6e5e2-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="6e5e2-158">Hinzufügen einer Entität zu einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="6e5e2-158">Add an entity to a table</span></span>

<span data-ttu-id="6e5e2-159">Eine Entität muss über einen Typ verfügen, der von erbt `TableEntity` .</span><span class="sxs-lookup"><span data-stu-id="6e5e2-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="6e5e2-160">Sie können `TableEntity` in beliebig erweitern, aber der Typ *muss* über einen Parameter losen Konstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="6e5e2-161">Nur Eigenschaften, die sowohl `get` als auch aufweisen, `set` werden in der Azure-Tabelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="6e5e2-162">Mit dem Partitions-und Zeilen Schlüssel einer Entität wird die Entität in der Tabelle eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="6e5e2-163">Entitäten mit demselben Partitionsschlüssel können schneller abgerufen werden als Entitäten mit unterschiedlichen Partitionsschlüsseln, die Verwendung verschiedener Partitionsschlüssel ermöglicht jedoch eine größere Skalierbarkeit paralleler Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="6e5e2-164">Im folgenden finden Sie ein Beispiel für einen `Customer` , der `lastName` als Partitions Schlüssel und `firstName` als Zeilen Schlüssel verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="6e5e2-165">Fügen Sie nun `Customer` der Tabelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="6e5e2-166">Erstellen Sie hierzu einen `TableOperation` , der für die Tabelle ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="6e5e2-167">In diesem Fall erstellen Sie einen `Insert` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="6e5e2-168">Einfügen eines Entitätsbatchs</span><span class="sxs-lookup"><span data-stu-id="6e5e2-168">Insert a batch of entities</span></span>

<span data-ttu-id="6e5e2-169">Sie können einen Batch von Entitäten in eine Tabelle einfügen, indem Sie einen einzelnen Schreibvorgang verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="6e5e2-170">Mit Batch Vorgängen können Sie Vorgänge in einer einzelnen Ausführung kombinieren, aber Sie haben einige Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="6e5e2-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="6e5e2-171">Sie können Updates, Löschungen und Einfügungen im gleichen Batch Vorgang ausführen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="6e5e2-172">Ein Batch Vorgang kann bis zu 100 Entitäten umfassen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="6e5e2-173">Alle Entitäten in einem Batch Vorgang müssen über denselben Partitions Schlüssel verfügen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="6e5e2-174">Obwohl es möglich ist, eine Abfrage in einem Batch Vorgang auszuführen, muss dies der einzige Vorgang im Batch sein.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="6e5e2-175">Hier ist ein Code, der zwei Einfügungen in einem Batch Vorgang kombiniert:</span><span class="sxs-lookup"><span data-stu-id="6e5e2-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="6e5e2-176">Abrufen aller Entitäten einer Partition</span><span class="sxs-lookup"><span data-stu-id="6e5e2-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="6e5e2-177">Verwenden Sie ein `TableQuery`-Objekt, um für eine Tabelle alle Entitäten einer Partition abzufragen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="6e5e2-178">Hier Filtern Sie nach Entitäten, bei denen "Smith" der Partitions Schlüssel ist.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="6e5e2-179">Sie drucken nun die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="6e5e2-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="6e5e2-180">Abrufen eines Entitätsbereichs in einer Partition</span><span class="sxs-lookup"><span data-stu-id="6e5e2-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="6e5e2-181">Wenn Sie nicht alle Entitäten in einer Partition abrufen möchten, können Sie einen Bereich angeben, indem Sie den Partitionsschlüsselfilter mit einem Zeilenschlüsselfilter kombinieren.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="6e5e2-182">Hier verwenden Sie zwei Filter, um alle Entitäten in der "Smith"-Partition zu erhalten, wobei der Zeilen Schlüssel (Vorname) mit einem Buchstaben vor "M" im Alphabet beginnt.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="6e5e2-183">Sie drucken nun die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="6e5e2-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="6e5e2-184">Abrufen einer einzelnen Entität</span><span class="sxs-lookup"><span data-stu-id="6e5e2-184">Retrieve a single entity</span></span>

<span data-ttu-id="6e5e2-185">Sie können eine Abfrage schreiben, um eine einzelne bestimmte Entität abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="6e5e2-186">Hier verwenden Sie einen `TableOperation` , um den Kunden "Ben Smith" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="6e5e2-187">Anstelle einer Auflistung erhalten Sie eine `Customer` .</span><span class="sxs-lookup"><span data-stu-id="6e5e2-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="6e5e2-188">Das Angeben von Partitions Schlüssel und Zeilen Schlüssel in einer Abfrage ist die schnellste Möglichkeit, um eine einzelne Entität aus dem Tabellen Dienst abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="6e5e2-189">Sie drucken nun die Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="6e5e2-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a><span data-ttu-id="6e5e2-190">Ersetzen einer Entität</span><span class="sxs-lookup"><span data-stu-id="6e5e2-190">Replace an entity</span></span>

<span data-ttu-id="6e5e2-191">Um eine Entität zu aktualisieren, rufen Sie Sie aus dem Tabellen Dienst ab, ändern Sie das Entitäts Objekt, und speichern Sie die Änderungen dann mit einem-Vorgang im Tabellen Dienst `Replace` .</span><span class="sxs-lookup"><span data-stu-id="6e5e2-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="6e5e2-192">Dadurch wird die Entität auf dem Server vollständig ersetzt, es sei denn, die Entität auf dem Server wurde seit dem Abrufen geändert. in diesem Fall schlägt der Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="6e5e2-193">Dieser Fehler soll verhindern, dass Ihre Anwendung versehentlich Änderungen aus anderen Quellen überschreibt.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="6e5e2-194">Einfügen-oder-Ersetzen einer Entität</span><span class="sxs-lookup"><span data-stu-id="6e5e2-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="6e5e2-195">Manchmal wissen Sie nicht, ob eine Entität in der Tabelle vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="6e5e2-196">Wenn dies der Fall ist, werden die darin gespeicherten aktuellen Werte nicht mehr benötigt.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="6e5e2-197">Sie können verwenden, `InsertOrReplace` um die Entität zu erstellen oder zu ersetzen, wenn Sie vorhanden ist, unabhängig von Ihrem Zustand.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="6e5e2-198">Abfragen einer Teilmenge von Entitätseigenschaften</span><span class="sxs-lookup"><span data-stu-id="6e5e2-198">Query a subset of entity properties</span></span>

<span data-ttu-id="6e5e2-199">Eine Tabellen Abfrage kann nur einige wenige Eigenschaften aus einer Entität abrufen, anstatt Sie zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="6e5e2-200">Diese Technik, die als Projektion bezeichnet wird, kann die Abfrageleistung verbessern, insbesondere bei großen Entitäten.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="6e5e2-201">Hier geben Sie nur e-Mail-Adressen mit `DynamicTableEntity` und zurück `EntityResolver` .</span><span class="sxs-lookup"><span data-stu-id="6e5e2-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="6e5e2-202">Die Projektion wird auf dem lokalen Speicher Emulator nicht unterstützt, daher wird dieser Code nur ausgeführt, wenn Sie ein Konto für den Tabellen Speicherdienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-202">Projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="6e5e2-203">Asynchrones Abrufen von Entitäten in Seiten</span><span class="sxs-lookup"><span data-stu-id="6e5e2-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="6e5e2-204">Wenn Sie eine große Anzahl von Entitäten lesen und diese beim Abrufen verarbeiten möchten, anstatt darauf zu warten, dass alle zurückgegeben werden, können Sie eine segmentierte Abfrage verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="6e5e2-205">Hier geben Sie die Ergebnisse in Seiten zurück, indem Sie einen asynchronen Workflow verwenden, sodass die Ausführung nicht blockiert wird, während Sie auf die Rückgabe eines großen Ergebnissatzes warten.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="6e5e2-206">Sie führen diese Berechnung nun synchron aus:</span><span class="sxs-lookup"><span data-stu-id="6e5e2-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="6e5e2-207">Löschen einer Entität</span><span class="sxs-lookup"><span data-stu-id="6e5e2-207">Delete an entity</span></span>

<span data-ttu-id="6e5e2-208">Sie können eine Entität löschen, nachdem Sie sie abgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="6e5e2-209">Wie beim Aktualisieren einer Entität schlägt dies fehl, wenn sich die Entität seit dem Abruf geändert hat.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="6e5e2-210">Löschen einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="6e5e2-210">Delete a table</span></span>

<span data-ttu-id="6e5e2-211">Sie können eine Tabelle aus einem Speicherkonto löschen.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="6e5e2-212">Eine gelöschte Tabelle kann für eine bestimmte Zeitdauer nach dem Löschvorgang nicht neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="6e5e2-213">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6e5e2-213">Next steps</span></span>

<span data-ttu-id="6e5e2-214">Nachdem Sie sich nun mit den Grundlagen von Table Storage vertraut gemacht haben, folgen Sie diesen Links, um mehr über komplexere Speicher Aufgaben und die Azure Cosmos DB Tabellen-API zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="6e5e2-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="6e5e2-215">Einführung in Azure Cosmos DB Tabellen-API</span><span class="sxs-lookup"><span data-stu-id="6e5e2-215">Introduction to Azure Cosmos DB Table API</span></span>](/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="6e5e2-216">Referenz zur Storage-Clientbibliothek für .NET</span><span class="sxs-lookup"><span data-stu-id="6e5e2-216">Storage Client Library for .NET reference</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="6e5e2-217">Azure Storage Typanbieter</span><span class="sxs-lookup"><span data-stu-id="6e5e2-217">Azure Storage Type Provider</span></span>](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="6e5e2-218">Azure Storage-Teamblog</span><span class="sxs-lookup"><span data-stu-id="6e5e2-218">Azure Storage Team Blog</span></span>](/archive/blogs/windowsazurestorage/)
- [<span data-ttu-id="6e5e2-219">Konfigurieren von Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="6e5e2-219">Configuring Connection Strings</span></span>](/azure/storage/common/storage-configure-connection-string)
