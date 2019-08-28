---
title: Vornehmen und Übergeben von Datenänderungen
ms.date: 03/30/2017
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
ms.openlocfilehash: 699a8730f21ff290ad15d1932f565ab7a2478fb5
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70043988"
---
# <a name="making-and-submitting-data-changes"></a><span data-ttu-id="6a267-102">Vornehmen und Übergeben von Datenänderungen</span><span class="sxs-lookup"><span data-stu-id="6a267-102">Making and Submitting Data Changes</span></span>

<span data-ttu-id="6a267-103">Die Themen in diesem Abschnitt erläutern das Vornehmen und Übergeben von Änderungen an die Datenbank sowie den Umgang mit Konflikten bei der vollständigen Parallelität.</span><span class="sxs-lookup"><span data-stu-id="6a267-103">The topics in this section describe how to make and transmit changes to the database and how to handle optimistic concurrency conflicts.</span></span>

> [!NOTE]
> <span data-ttu-id="6a267-104">Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6a267-104">You can override [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] default methods for `Insert`, `Update`, and `Delete` database operations.</span></span> <span data-ttu-id="6a267-105">Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update-und DELETE-Vorgängen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span><span class="sxs-lookup"><span data-stu-id="6a267-105">For more information, see [Customizing Insert, Update, and Delete Operations](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).</span></span>
>
> <span data-ttu-id="6a267-106">Entwickler, die Visual Studio verwenden, können den objektrelationaler Designer verwenden, um gespeicherte Prozeduren für denselben Zweck zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="6a267-106">Developers using Visual Studio can use the Object Relational Designer to develop stored procedures for the same purpose.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6a267-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6a267-107">In This Section</span></span>

<span data-ttu-id="6a267-108">[Vorgehensweise: Einfügen von Zeilen in die Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/how-to-insert-rows-into-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="6a267-108">[How to: Insert Rows Into the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-insert-rows-into-the-database.md) </span></span>\
<span data-ttu-id="6a267-109">Erläutert das Einfügen von Zeilen in die Datenbank durch Hinzufügen von Objekten in das Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="6a267-109">Describes how to insert rows in the database by adding objects to the object model.</span></span>

<span data-ttu-id="6a267-110">[Vorgehensweise: Aktualisieren von Zeilen in der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/how-to-update-rows-in-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="6a267-110">[How to: Update Rows in the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-update-rows-in-the-database.md) </span></span>\
<span data-ttu-id="6a267-111">Erläutert das Aktualisieren von Zeilen in der Datenbank durch Aktualisieren von Objekten im Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="6a267-111">Describes how to update rows in the database by updating objects in the object model.</span></span>

<span data-ttu-id="6a267-112">[Vorgehensweise: Zeilen aus der Datenbank löschen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="6a267-112">[How to: Delete Rows From the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md) </span></span>\
<span data-ttu-id="6a267-113">Erläutert das Löschen von Zeilen in der Datenbank durch Löschen von Objekten aus dem Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="6a267-113">Describes how to delete rows in the database by deleting objects in the object model.</span></span>

<span data-ttu-id="6a267-114">[Vorgehensweise: Übermitteln von Änderungen an die Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/how-to-submit-changes-to-the-database.md) </span><span class="sxs-lookup"><span data-stu-id="6a267-114">[How to: Submit Changes to the Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-submit-changes-to-the-database.md) </span></span>\
<span data-ttu-id="6a267-115">Beschreibt das Übergeben von Objektmodelländerungen an die Datenbank.</span><span class="sxs-lookup"><span data-stu-id="6a267-115">Describes how to send object-model changes to the database.</span></span>

<span data-ttu-id="6a267-116">[Vorgehensweise: Übermittlungen von Daten mithilfe von Transaktionen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md) </span><span class="sxs-lookup"><span data-stu-id="6a267-116">[How to: Bracket Data Submissions by Using Transactions](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md) </span></span>\
<span data-ttu-id="6a267-117">Beschreibt das Einschließen von Operationen in eine Transaktion.</span><span class="sxs-lookup"><span data-stu-id="6a267-117">Describes how to include operations in a transaction.</span></span>

<span data-ttu-id="6a267-118">[Vorgehensweise: Dynamisches Erstellen einer Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md) </span><span class="sxs-lookup"><span data-stu-id="6a267-118">[How to: Dynamically Create a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md) </span></span>\
<span data-ttu-id="6a267-119">Beschreibt das dynamische Erzeugen von Datenbanken und typische Szenarien für diesen Ansatz.</span><span class="sxs-lookup"><span data-stu-id="6a267-119">Describes how to generate databases dynamically, and typical scenarios for this approach.</span></span>

<span data-ttu-id="6a267-120">[Vorgehensweise: Verwalten von Änderungs Konflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md) </span><span class="sxs-lookup"><span data-stu-id="6a267-120">[How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md) </span></span>\
<span data-ttu-id="6a267-121">Beschreibt Techniken für den Umgang mit Problemen mit der vollständigen Parallelität.</span><span class="sxs-lookup"><span data-stu-id="6a267-121">Describes techniques for addressing optimistic concurrency issues.</span></span>
