---
title: Typisierte "DataSets"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a68d4a10b01285a7e1b33238409351ca04d0aeb4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="typed-datasets"></a><span data-ttu-id="2f20b-102">Typisierte "DataSets"</span><span class="sxs-lookup"><span data-stu-id="2f20b-102">Typed DataSets</span></span>
<span data-ttu-id="2f20b-103">Neben dem späten Bindungszugriff auf Werte mithilfe von schwach typisierten Variablen bietet das <xref:System.Data.DataSet> über eine stark typisierte Metapher Zugriff auf Daten.</span><span class="sxs-lookup"><span data-stu-id="2f20b-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="2f20b-104">Tabellen und Spalten, die Teil der **DataSet** mithilfe von benutzerfreundlichen Namen zugegriffen werden kann und stark typisierten Variablen.</span><span class="sxs-lookup"><span data-stu-id="2f20b-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="2f20b-105">Eine typisierte **DataSet** ist eine Klasse, die von abgeleitet ist ein **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="2f20b-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="2f20b-106">Es erbt alle Methoden, Ereignisse und Eigenschaften einer **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="2f20b-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="2f20b-107">Darüber hinaus eine typisierte **DataSet** stellt stark typisierte Methoden, Ereignisse und Eigenschaften bereit.</span><span class="sxs-lookup"><span data-stu-id="2f20b-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="2f20b-108">Das heißt, dass Sie auf Tabellen und Spalten anhand ihres Namens zugreifen können und keine auflistungsbasierten Methoden verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="2f20b-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="2f20b-109">Abgesehen von der verbesserten Lesbarkeit des Codes, eine typisierte **DataSet** können auch den Visual Studio .NET Code-Editor, um Zeilen während der Eingabe automatisch zu vervollständigen.</span><span class="sxs-lookup"><span data-stu-id="2f20b-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="2f20b-110">Darüber hinaus die stark typisierte **DataSet** ermöglicht den Zugriff auf Werte als richtigen Typ zum Zeitpunkt der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="2f20b-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="2f20b-111">Mit einem stark typisierten **DataSet**, Konflikt-Typfehler werden abgefangen, wenn der Code wird kompiliert statt zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="2f20b-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f20b-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2f20b-112">In This Section</span></span>  
 [<span data-ttu-id="2f20b-113">Generieren von stark typisierten DataSets</span><span class="sxs-lookup"><span data-stu-id="2f20b-113">Generating Strongly Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 <span data-ttu-id="2f20b-114">Beschreibt das Erstellen und Verwenden eines stark typisierten **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="2f20b-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="2f20b-115">Hinzufügen von Anmerkungen zu typisierten DataSets</span><span class="sxs-lookup"><span data-stu-id="2f20b-115">Annotating Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 <span data-ttu-id="2f20b-116">Beschreibt die Vorgehensweise zum Erstellen eines stark typisierten Schema der XML Schema Definition Language (XSD) mit Anmerkungen versehen **DataSet**, um **DataSet** -Elementen lange Namen ohne die zugrunde liegende Schema ändern.</span><span class="sxs-lookup"><span data-stu-id="2f20b-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f20b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f20b-117">See Also</span></span>  
 [<span data-ttu-id="2f20b-118">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="2f20b-118">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="2f20b-119">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="2f20b-119">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
