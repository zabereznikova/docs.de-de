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
ms.openlocfilehash: 905374a60261b0c2a863edb956943d41ae80f04d
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-azure-table-storage-using-f"></a><span data-ttu-id="3b91b-104">Erste Schritte mit Azure-Tabellenspeicher mit f#</span><span class="sxs-lookup"><span data-stu-id="3b91b-104">Get started with Azure Table storage using F#</span></span> #

<span data-ttu-id="3b91b-105">Azure-Tabellenspeicher ist ein Dienst, der strukturierte NoSQL-Daten in der Cloud gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3b91b-105">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="3b91b-106">Tabellenspeicher ist ein Key-Attribut mit einem schemaless Entwurf.</span><span class="sxs-lookup"><span data-stu-id="3b91b-106">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="3b91b-107">Da Table Storage schemaless ist, ist es einfach, Daten von Ihrer Anwendung Evolve sich Anforderungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="3b91b-107">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="3b91b-108">Zugriff auf Daten ist schnell und kostengünstig für alle Arten von Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="3b91b-108">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="3b91b-109">Tabellenspeicher ist in der Regel deutlich niedriger Kosten als herkömmliche SQL für ähnliche Datenmengen.</span><span class="sxs-lookup"><span data-stu-id="3b91b-109">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="3b91b-110">Sie können Tabellenspeicher zum Speichern von flexible Datasets, wie z. B. Benutzerdaten für Webanwendungen, Adressbücher Geräteinformationen und andere Arten von Metadaten, die Ihr Dienst erfordert, verwenden.</span><span class="sxs-lookup"><span data-stu-id="3b91b-110">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="3b91b-111">Sie können eine beliebige Anzahl von Entitäten in einer Tabelle speichern, und ein Speicherkonto kann eine beliebige Anzahl von Tabellen, bis die Kapazitätsgrenze des Speicherkontos zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="3b91b-111">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="3b91b-112">Zu diesem Lernprogramm</span><span class="sxs-lookup"><span data-stu-id="3b91b-112">About this tutorial</span></span>

<span data-ttu-id="3b91b-113">Dieses Lernprogramm zeigt, wie F#-Code werden einige häufig auszuführende Aufgaben mithilfe von Azure-Tabellenspeicher, einschließlich erstellen und Löschen einer Tabelle und einfügen, aktualisieren, löschen und Abfragen von Daten aus Tabellen schreiben.</span><span class="sxs-lookup"><span data-stu-id="3b91b-113">This tutorial shows how to write F# code to do some common tasks using Azure Table storage, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

<span data-ttu-id="3b91b-114">Eine grundlegende Übersicht des tabellenspeichers finden Sie unter [.NET Guide für den Tabellenspeicher](/azure/storage/storage-dotnet-how-to-use-tables)</span><span class="sxs-lookup"><span data-stu-id="3b91b-114">For a conceptual overview of table storage, please see [the .NET guide for table storage](/azure/storage/storage-dotnet-how-to-use-tables)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3b91b-115">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="3b91b-115">Prerequisites</span></span>

<span data-ttu-id="3b91b-116">Um dieser Anleitung zu verwenden, müssen Sie zuerst [Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="3b91b-116">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="3b91b-117">Sie benötigen auch Ihr speicherzugriffsschlüssel für dieses Konto.</span><span class="sxs-lookup"><span data-stu-id="3b91b-117">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="3b91b-118">Erstellen Sie ein f#-Skript und Start f# Interactive</span><span class="sxs-lookup"><span data-stu-id="3b91b-118">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="3b91b-119">Die Beispiele in diesem Artikel können in einer f#-Anwendung oder ein F#-Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3b91b-119">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="3b91b-120">Um ein F#-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `tables.fsx`, in der f#-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="3b91b-120">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="3b91b-121">Verwenden Sie als Nächstes eine [Paket-Manager](package-management.md) wie z. B. [Paket](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` Paket und Verweis `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="3b91b-121">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="3b91b-122">Führen Sie wieder für "Microsoft.WindowsAzure.ConfigurationManager", um den Namespace Microsoft.Azure zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3b91b-122">Do it again for \`Microsoft.WindowsAzure.ConfigurationManager' in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="3b91b-123">Fügen Sie Namespacedeklarationen hinzu</span><span class="sxs-lookup"><span data-stu-id="3b91b-123">Add namespace declarations</span></span>

<span data-ttu-id="3b91b-124">Fügen Sie die folgenden `open` Anweisungen am oberen Rand der `tables.fsx` Datei:</span><span class="sxs-lookup"><span data-stu-id="3b91b-124">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="3b91b-125">Abrufen der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3b91b-125">Get your connection string</span></span>

<span data-ttu-id="3b91b-126">Sie benötigen eine Azure-Speicher-Verbindungszeichenfolge für dieses Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="3b91b-126">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="3b91b-127">Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Speicherverbindungs-Zeichenfolgen konfigurieren](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="3b91b-127">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="3b91b-128">Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="3b91b-128">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="3b91b-129">Dies ist jedoch **nicht empfohlen,** für tatsächliche Projekte.</span><span class="sxs-lookup"><span data-stu-id="3b91b-129">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="3b91b-130">Schlüssel für das Speicherkonto ähnelt das Stammkennwort für Ihr Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="3b91b-130">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="3b91b-131">Achten Sie stets darauf zum Schützen der Schlüssel für das Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="3b91b-131">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="3b91b-132">Vermeiden Sie verteilen an andere Benutzer, die eine feste Programmierung, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="3b91b-132">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="3b91b-133">Sie können erneut zu generieren Ihres Schlüssels im Azure-Portal verwenden, wenn Sie glauben, dass er gefährdet sein kann.</span><span class="sxs-lookup"><span data-stu-id="3b91b-133">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="3b91b-134">Für echten Anwendungen ist die beste Methode zum Verwalten Ihrer speicherverbindungs-Zeichenfolge in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="3b91b-134">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="3b91b-135">Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie dies tun:</span><span class="sxs-lookup"><span data-stu-id="3b91b-135">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="3b91b-136">Mit Azure-Konfigurations-Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="3b91b-136">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="3b91b-137">Sie können auch eine API wie das .NET Framework `ConfigurationManager` Typ.</span><span class="sxs-lookup"><span data-stu-id="3b91b-137">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="3b91b-138">Analysieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3b91b-138">Parse the connection string</span></span>

<span data-ttu-id="3b91b-139">Verwenden Sie, um die Verbindungszeichenfolge zu analysieren:</span><span class="sxs-lookup"><span data-stu-id="3b91b-139">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="3b91b-140">Dadurch wird zurückgegeben, eine `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="3b91b-140">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="3b91b-141">Erstellen Sie den tabellendienstclient</span><span class="sxs-lookup"><span data-stu-id="3b91b-141">Create the Table service client</span></span>

<span data-ttu-id="3b91b-142">Die `CloudTableClient` -Klasse ermöglicht es Ihnen, zum Abrufen von Tabellen und Entitäten im Tabellenspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3b91b-142">The `CloudTableClient` class enables you to retrieve tables and entities stored in Table storage.</span></span> <span data-ttu-id="3b91b-143">Dies ist eine Methode zum Erstellen des Service-Clients:</span><span class="sxs-lookup"><span data-stu-id="3b91b-143">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="3b91b-144">Jetzt können Sie Code schreiben, liest Daten aus und schreibt Daten in den Tabellenspeicher.</span><span class="sxs-lookup"><span data-stu-id="3b91b-144">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

## <a name="create-a-table"></a><span data-ttu-id="3b91b-145">Erstellen Sie eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="3b91b-145">Create a table</span></span>

<span data-ttu-id="3b91b-146">Dieses Beispiel zeigt, wie eine Tabelle erstellt, wenn sie nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="3b91b-146">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

## <a name="add-an-entity-to-a-table"></a><span data-ttu-id="3b91b-147">Hinzufügen einer Entität zu einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="3b91b-147">Add an entity to a table</span></span>

<span data-ttu-id="3b91b-148">Eine Entität muss einen Typ aufweisen, die von erben `TableEntity`.</span><span class="sxs-lookup"><span data-stu-id="3b91b-148">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="3b91b-149">Sie erweitern können `TableEntity` in beliebig, aber Ihr Typ *müssen* einen parameterlosen Konstruktor aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3b91b-149">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="3b91b-150">Nur Eigenschaften, die sowohl `get` und `set` in Ihrem Azure-Tabelle gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="3b91b-150">Only properties that have both `get` and `set` will be stored in your Azure Table.</span></span>

<span data-ttu-id="3b91b-151">Eine Entität Partitions- und Zeilenschlüssel ist die Entität in der Tabelle eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="3b91b-151">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="3b91b-152">Entitäten mit den gleichen Partitionsschlüssel können schneller als mit anderen Partitionsschlüssel abgefragt werden, jedoch mit unterschiedlichen Partitionsschlüssel für eine höhere Skalierbarkeit von parallelen Vorgängen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3b91b-152">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="3b91b-153">Hier ist ein Beispiel für eine `Customer` , verwendet der `lastName` als Partitionsschlüssel und `firstName` als Zeilenschlüssel.</span><span class="sxs-lookup"><span data-stu-id="3b91b-153">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="3b91b-154">Nachdem wir hinzufügen unsere `Customer` der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3b91b-154">Now we'll add our `Customer` to the table.</span></span> <span data-ttu-id="3b91b-155">Zu diesem Zweck erstellen Sie eine `TableOperation` , die für die Tabelle ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3b91b-155">To do so, you create a `TableOperation` that will execute on the table.</span></span> <span data-ttu-id="3b91b-156">In diesem Fall erstellen Sie ein `Insert` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="3b91b-156">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

## <a name="insert-a-batch-of-entities"></a><span data-ttu-id="3b91b-157">Einfügen eines entitätenbatches</span><span class="sxs-lookup"><span data-stu-id="3b91b-157">Insert a batch of entities</span></span>

<span data-ttu-id="3b91b-158">Sie können einen entitätenbatch in einer Tabelle mit einem einzelnen Schreibvorgang einfügen.</span><span class="sxs-lookup"><span data-stu-id="3b91b-158">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="3b91b-159">Batchvorgänge ermöglichen es Ihnen, Vorgänge in eine einzelne Ausführung zu kombinieren, verfügen jedoch über einige Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="3b91b-159">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="3b91b-160">Sie können Updates ausführen löscht, und fügt Sie in einem Batchvorgang.</span><span class="sxs-lookup"><span data-stu-id="3b91b-160">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="3b91b-161">Ein Batchvorgang kann bis zu 100 Entitäten enthalten.</span><span class="sxs-lookup"><span data-stu-id="3b91b-161">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="3b91b-162">Alle Entitäten in einem Batchvorgang müssen den gleichen Partitionsschlüssel haben.</span><span class="sxs-lookup"><span data-stu-id="3b91b-162">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="3b91b-163">Es ist, zwar möglich, eine Abfrage in einem Batchvorgang auszuführen muss es die einzige Vorgang im Batch sein.</span><span class="sxs-lookup"><span data-stu-id="3b91b-163">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="3b91b-164">Hier ist Teil des Codes, die zwei einfügungen in einem Batchvorgang kombiniert:</span><span class="sxs-lookup"><span data-stu-id="3b91b-164">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

## <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="3b91b-165">Rufen Sie aller Entitäten in einer Partition ab</span><span class="sxs-lookup"><span data-stu-id="3b91b-165">Retrieve all entities in a partition</span></span>

<span data-ttu-id="3b91b-166">Verwenden Sie zum Abfragen einer Tabelle für alle Entitäten in einer Partition, eine `TableQuery` Objekt.</span><span class="sxs-lookup"><span data-stu-id="3b91b-166">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="3b91b-167">Hier ist filtern Sie für Entitäten, wobei der Partitionsschlüssel ist "Buster".</span><span class="sxs-lookup"><span data-stu-id="3b91b-167">Here, you filter for entities where "Buster" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L80)]

<span data-ttu-id="3b91b-168">Jetzt werden die Ergebnisse drucken:</span><span class="sxs-lookup"><span data-stu-id="3b91b-168">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


## <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="3b91b-169">Rufen Sie einen Bereich von Entitäten in einer partition</span><span class="sxs-lookup"><span data-stu-id="3b91b-169">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="3b91b-170">Wenn Sie nicht alle Entitäten in einer Partition abfragen möchten, können Sie einen Bereich angeben, durch die Kombination der Filter der Partition Schlüssel mit einem Schlüssel Zeilenfilter.</span><span class="sxs-lookup"><span data-stu-id="3b91b-170">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="3b91b-171">Hier verwenden Sie zwei Filter auf alle Entitäten in der Partition "Buster" abrufen, wo der Zeilenschlüssel (Rufname) früher als "M" im Alphabet mit einem Buchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="3b91b-171">Here, you use two filters to get all entities in the "Buster" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="3b91b-172">Jetzt werden die Ergebnisse drucken:</span><span class="sxs-lookup"><span data-stu-id="3b91b-172">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

## <a name="retrieve-a-single-entity"></a><span data-ttu-id="3b91b-173">Abrufen einer einzelnen Entität</span><span class="sxs-lookup"><span data-stu-id="3b91b-173">Retrieve a single entity</span></span>

<span data-ttu-id="3b91b-174">Sie können eine Abfrage zum Abrufen einer bestimmten Entität schreiben.</span><span class="sxs-lookup"><span data-stu-id="3b91b-174">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="3b91b-175">Verwenden Sie hier eine `TableOperation` an den Kunden "Larry Buster".</span><span class="sxs-lookup"><span data-stu-id="3b91b-175">Here, you use a `TableOperation` to specify the customer "Larry Buster".</span></span> <span data-ttu-id="3b91b-176">Statt einer Auflistung erhalten Sie wieder eine `Customer`.</span><span class="sxs-lookup"><span data-stu-id="3b91b-176">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="3b91b-177">Der Partitionsschlüssel und Zeilenschlüssel in einer Abfrage angegeben, ist die schnellste Möglichkeit zum Abrufen einer einzelnen Entität aus dem Tabellendienst.</span><span class="sxs-lookup"><span data-stu-id="3b91b-177">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="3b91b-178">Jetzt werden die Ergebnisse drucken:</span><span class="sxs-lookup"><span data-stu-id="3b91b-178">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


## <a name="replace-an-entity"></a><span data-ttu-id="3b91b-179">Ersetzen einer Entität</span><span class="sxs-lookup"><span data-stu-id="3b91b-179">Replace an entity</span></span>

<span data-ttu-id="3b91b-180">Zum Aktualisieren einer Entität aus der Tabellendienst abrufen, das Entitätsobjekt ändern und speichern Sie die Änderungen an der Tabelle mit einer `Replace` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="3b91b-180">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="3b91b-181">Dies bewirkt, dass die Entität, die auf dem Server vollständig ersetzt werden, es sei denn, die Entität, auf dem Server geändert wurde, seit sie abgerufen wurde, in diesem Fall schlägt der Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="3b91b-181">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation will fail.</span></span> <span data-ttu-id="3b91b-182">Dieser Fehler wird verhindert, dass die Anwendung von Änderungen aus anderen Quellen versehentlich überschrieben.</span><span class="sxs-lookup"><span data-stu-id="3b91b-182">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

## <a name="insert-or-replace-an-entity"></a><span data-ttu-id="3b91b-183">INSERT-oder-Ersetzen einer Entität</span><span class="sxs-lookup"><span data-stu-id="3b91b-183">Insert-or-replace an entity</span></span>

<span data-ttu-id="3b91b-184">In einigen Fällen, wissen Sie nicht, wenn die Entität in der Tabelle oder nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3b91b-184">Sometimes, you don't know if the entity exists in the table or not.</span></span> <span data-ttu-id="3b91b-185">Und wenn dies der Fall ist, werden die aktuellen Werte, die darin gespeicherten nicht mehr benötigt.</span><span class="sxs-lookup"><span data-stu-id="3b91b-185">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="3b91b-186">Sie können `InsertOrReplace` zum Erstellen der Entität oder Ersetzen Sie ihn, falls es vorhanden, unabhängig von ihrem Status ist.</span><span class="sxs-lookup"><span data-stu-id="3b91b-186">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L140)]

## <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="3b91b-187">Die Abfrage eine Teilmenge von Entitätseigenschaften</span><span class="sxs-lookup"><span data-stu-id="3b91b-187">Query a subset of entity properties</span></span>

<span data-ttu-id="3b91b-188">Eine Table-Abfrage kann aus einer Entität anstelle aller Textknoten nur wenige Eigenschaften abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3b91b-188">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="3b91b-189">Diese Technik mit dem Namen Projektion kann, insbesondere bei großen Entitäten verbessern.</span><span class="sxs-lookup"><span data-stu-id="3b91b-189">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="3b91b-190">Hier ist Sie zurückkehren nur e-Mail-Adressen mit `DynamicTableEntity` und `EntityResolver`.</span><span class="sxs-lookup"><span data-stu-id="3b91b-190">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="3b91b-191">Beachten Sie, dass die Projektion auf den lokalen Speicheremulator nicht unterstützt wird, sodass dieser Code ausgeführt wird, nur, wenn Sie ein Konto für den Tabellendienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="3b91b-191">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L146-L157)]

## <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="3b91b-192">Abrufen von Entitäten in Seiten asynchron</span><span class="sxs-lookup"><span data-stu-id="3b91b-192">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="3b91b-193">Wenn Sie eine große Anzahl von Entitäten lesen gerade und verarbeiten sie abgerufen werden, sondern wartet, bis sie alle zurückgeben, können Sie eine Abfrage segmentierte werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3b91b-193">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="3b91b-194">Hier geben Sie Ergebnisse in Seiten mit einem asynchronen Workflow, damit die Ausführung nicht blockiert wird, während für eine große Anzahl der zurückzugebenden Ergebnisseite warten, können Sie zurück.</span><span class="sxs-lookup"><span data-stu-id="3b91b-194">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L177)]

<span data-ttu-id="3b91b-195">Sie nun diese Berechnung synchron ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="3b91b-195">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L179-L179)]

## <a name="delete-an-entity"></a><span data-ttu-id="3b91b-196">Löschen einer Entität</span><span class="sxs-lookup"><span data-stu-id="3b91b-196">Delete an entity</span></span>

<span data-ttu-id="3b91b-197">Sie können eine Entität löschen, nachdem Sie es abgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="3b91b-197">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="3b91b-198">Wie bei der Aktualisierung einer Entität, schlägt dies fehl, wenn die Entität geändert wurde, seit Sie sie abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3b91b-198">As with updating an entity, this will fail if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L185-L186)]

## <a name="delete-a-table"></a><span data-ttu-id="3b91b-199">Löschen einer Tabelle</span><span class="sxs-lookup"><span data-stu-id="3b91b-199">Delete a table</span></span>

<span data-ttu-id="3b91b-200">Sie können eine Tabelle aus einem Speicherkonto löschen.</span><span class="sxs-lookup"><span data-stu-id="3b91b-200">You can delete a table from a storage account.</span></span> <span data-ttu-id="3b91b-201">Eine Tabelle, die gelöscht wurde ist nicht verfügbar für eine bestimmte Zeitdauer nach dem Löschvorgang neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3b91b-201">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L192-L192)]

## <a name="next-steps"></a><span data-ttu-id="3b91b-202">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3b91b-202">Next steps</span></span>

<span data-ttu-id="3b91b-203">Nun, dass Sie die Grundlagen des tabellenspeichers gelernt haben, führen Sie die folgenden Links, um weitere Informationen zu komplexeren Speicheraufgaben:</span><span class="sxs-lookup"><span data-stu-id="3b91b-203">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks:</span></span>

- [<span data-ttu-id="3b91b-204">Azure-Speicher-APIs für .NET</span><span class="sxs-lookup"><span data-stu-id="3b91b-204">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="3b91b-205">Azure-Speicher-Typanbieter</span><span class="sxs-lookup"><span data-stu-id="3b91b-205">Azure Storage Type Provider</span></span>](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="3b91b-206">Azure-Speicher-Teamblog</span><span class="sxs-lookup"><span data-stu-id="3b91b-206">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/b/windowsazurestorage/)
- [<span data-ttu-id="3b91b-207">Konfigurieren von Verbindungszeichenfolgen für Azure-Speicher</span><span class="sxs-lookup"><span data-stu-id="3b91b-207">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="3b91b-208">Erste Schritte mit Azure-Tabellenspeicher in .NET</span><span class="sxs-lookup"><span data-stu-id="3b91b-208">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/documentation/samples/storage-table-dotnet-getting-started/)
