---
title: "Vornehmen und Übergeben von Datenänderungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d2b121bdadcc231d2ea3a2c1d2ebdab40306c5ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="eac64-102">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="eac64-102">Making and Submitting Data Changes</span></span>
<span data-ttu-id="eac64-103">Die Themen in diesem Abschnitt erläutern das Vornehmen und Übergeben von Änderungen an die Datenbank sowie den Umgang mit Konflikten bei der vollständigen Parallelität.</span><span class="sxs-lookup"><span data-stu-id="eac64-103">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eac64-104">Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben.</span><span class="sxs-lookup"><span data-stu-id="eac64-104">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="eac64-105">Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="eac64-105">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>  
>   
>  <span data-ttu-id="eac64-106">Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, können mithilfe von [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] gespeicherte Prozeduren für denselben Zweck entwickeln.</span><span class="sxs-lookup"><span data-stu-id="eac64-106">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to develop stored procedures for the same purpose.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eac64-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="eac64-107">In This Section</span></span>  
 [<span data-ttu-id="eac64-108">Vorgehensweise: Einfügen von Zeilen in die Datenbank</span><span class="sxs-lookup"><span data-stu-id="eac64-108">How to: Insert Rows Into the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-insert-rows-into-the-database.md)  
 <span data-ttu-id="eac64-109">Erläutert das Einfügen von Zeilen in die Datenbank durch Hinzufügen von Objekten in das Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="eac64-109">Describes how to insert rows in the database by adding objects to the object model.</span></span>  
  
 [<span data-ttu-id="eac64-110">Vorgehensweise: Aktualisieren von Zeilen in der Datenbank</span><span class="sxs-lookup"><span data-stu-id="eac64-110">How to: Update Rows in the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-update-rows-in-the-database.md)  
 <span data-ttu-id="eac64-111">Erläutert das Aktualisieren von Zeilen in der Datenbank durch Aktualisieren von Objekten im Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="eac64-111">Describes how to update rows in the database by updating objects in the object model.</span></span>  
  
 [<span data-ttu-id="eac64-112">Vorgehensweise: Löschen von Zeilen aus der Datenbank</span><span class="sxs-lookup"><span data-stu-id="eac64-112">How to: Delete Rows From the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md)  
 <span data-ttu-id="eac64-113">Erläutert das Löschen von Zeilen in der Datenbank durch Löschen von Objekten aus dem Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="eac64-113">Describes how to delete rows in the database by deleting objects in the object model.</span></span>  
  
 [<span data-ttu-id="eac64-114">Vorgehensweise: Übergeben von Änderungen an die Datenbank</span><span class="sxs-lookup"><span data-stu-id="eac64-114">How to: Submit Changes to the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-submit-changes-to-the-database.md)  
 <span data-ttu-id="eac64-115">Beschreibt das Übergeben von Objektmodelländerungen an die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="eac64-115">Describes how to send object-model changes to the database.</span></span>  
  
 [<span data-ttu-id="eac64-116">Vorgehensweise: Einklammern von Datenübergaben durch das Verwenden von Transaktionen</span><span class="sxs-lookup"><span data-stu-id="eac64-116">How to: Bracket Data Submissions by Using Transactions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)  
 <span data-ttu-id="eac64-117">Beschreibt das Einschließen von Operationen in eine Transaktion.</span><span class="sxs-lookup"><span data-stu-id="eac64-117">Describes how to include operations in a transaction.</span></span>  
  
 [<span data-ttu-id="eac64-118">Vorgehensweise: Dynamisches Erstellen einer neuen Datenbank</span><span class="sxs-lookup"><span data-stu-id="eac64-118">How to: Dynamically Create a Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md)  
 <span data-ttu-id="eac64-119">Beschreibt das dynamische Erzeugen von Datenbanken und typische Szenarien für diesen Ansatz.</span><span class="sxs-lookup"><span data-stu-id="eac64-119">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>  
  
 [<span data-ttu-id="eac64-120">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="eac64-120">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 <span data-ttu-id="eac64-121">Beschreibt Techniken für den Umgang mit Problemen mit der vollständigen Parallelität.</span><span class="sxs-lookup"><span data-stu-id="eac64-121">Describes techniques for addressing optimistic concurrency issues.</span></span>
