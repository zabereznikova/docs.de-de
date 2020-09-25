---
title: 'Vorgehensweise: Verwalten von Änderungskonflikten'
ms.date: 03/30/2017
ms.assetid: cd292c51-a3d1-4c6f-8d8e-04323c36054e
ms.openlocfilehash: 496971a99522c2547759905833ce2e89ea00826b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173405"
---
# <a name="how-to-manage-change-conflicts"></a><span data-ttu-id="480f6-102">Vorgehensweise: Verwalten von Änderungskonflikten</span><span class="sxs-lookup"><span data-stu-id="480f6-102">How to: Manage Change Conflicts</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="480f6-103">stellt eine Sammlung von APIs bereit, mit deren Hilfe Sie Parallelitäts Konflikte ermitteln, auswerten und beheben können.</span><span class="sxs-lookup"><span data-stu-id="480f6-103">provides a collection of APIs to help you discover, evaluate, and resolve concurrency conflicts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="480f6-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="480f6-104">In This Section</span></span>  

 [<span data-ttu-id="480f6-105">Vorgehensweise: Erkennen und Auflösen von Übergabekonflikten</span><span class="sxs-lookup"><span data-stu-id="480f6-105">How to: Detect and Resolve Conflicting Submissions</span></span>](how-to-detect-and-resolve-conflicting-submissions.md)  
 <span data-ttu-id="480f6-106">Beschreibt die Erkennung und Behebung von Parallelitätskonflikten.</span><span class="sxs-lookup"><span data-stu-id="480f6-106">Describes how to detect and resolve concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="480f6-107">Vorgehensweise: Angeben, wann Parallelitätsausnahmen ausgelöst werden</span><span class="sxs-lookup"><span data-stu-id="480f6-107">How to: Specify When Concurrency Exceptions are Thrown</span></span>](how-to-specify-when-concurrency-exceptions-are-thrown.md)  
 <span data-ttu-id="480f6-108">Beschreibt das Festlegen des Zeitpunkts für Informationen zu Parallelitätskonflikten.</span><span class="sxs-lookup"><span data-stu-id="480f6-108">Describes how to specify when you should be informed of concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="480f6-109">Vorgehensweise: Angeben, welche Member auf Parallelitätskonflikte getestet werden</span><span class="sxs-lookup"><span data-stu-id="480f6-109">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 <span data-ttu-id="480f6-110">Beschreibt, wie Sie festlegen, dass Attributmember auf Parallelitätskonflikte überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="480f6-110">Describes how to attribute members to specify whether they are checked for concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="480f6-111">Vorgehensweise: Abrufen von Entitätskonfliktinformationen</span><span class="sxs-lookup"><span data-stu-id="480f6-111">How to: Retrieve Entity Conflict Information</span></span>](how-to-retrieve-entity-conflict-information.md)  
 <span data-ttu-id="480f6-112">Beschreibt, wie Informationen über Entitätskonflikte erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="480f6-112">Describes how to gather information about entity conflicts.</span></span>  
  
 [<span data-ttu-id="480f6-113">Vorgehensweise: Abrufen von Memberkonfliktinformationen</span><span class="sxs-lookup"><span data-stu-id="480f6-113">How to: Retrieve Member Conflict Information</span></span>](how-to-retrieve-member-conflict-information.md)  
 <span data-ttu-id="480f6-114">Beschreibt, wie Informationen über Memberkonflikte erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="480f6-114">Describes how to gather information about member conflicts.</span></span>  
  
 [<span data-ttu-id="480f6-115">Vorgehensweise: Auflösen von Parallelitätskonflikten durch Beibehalten von Datenbankwerten</span><span class="sxs-lookup"><span data-stu-id="480f6-115">How to: Resolve Conflicts by Retaining Database Values</span></span>](how-to-resolve-conflicts-by-retaining-database-values.md)  
 <span data-ttu-id="480f6-116">Beschreibt, wie aktuelle Werte mit Datenbankwerten überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="480f6-116">Describes how to overwrite current values with database values.</span></span>  
  
 [<span data-ttu-id="480f6-117">Vorgehensweise: Auflösen von Parallelitätskonflikten durch Überschreiben von Datenbankwerten</span><span class="sxs-lookup"><span data-stu-id="480f6-117">How to: Resolve Conflicts by Overwriting Database Values</span></span>](how-to-resolve-conflicts-by-overwriting-database-values.md)  
 <span data-ttu-id="480f6-118">Beschreibt, wie aktuelle Werte durch Überschreiben von Datenbankwerten erhalten bleiben.</span><span class="sxs-lookup"><span data-stu-id="480f6-118">Describes how to keep current values by overwriting database values.</span></span>  
  
 [<span data-ttu-id="480f6-119">Vorgehensweise: Auflösen von Parallelitätskonflikten durch Zusammenführen von Datenbankwerten</span><span class="sxs-lookup"><span data-stu-id="480f6-119">How to: Resolve Conflicts by Merging with Database Values</span></span>](how-to-resolve-conflicts-by-merging-with-database-values.md)  
 <span data-ttu-id="480f6-120">Beschreibt, wie ein Konflikt durch Zusammenführen von Datenbanken und aktuellen Werten gelöst wird.</span><span class="sxs-lookup"><span data-stu-id="480f6-120">Describes how to resolve a conflict by merging database and current values.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="480f6-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="480f6-121">Related Sections</span></span>  

 [<span data-ttu-id="480f6-122">Optimistische Nebenläufigkeit: Übersicht</span><span class="sxs-lookup"><span data-stu-id="480f6-122">Optimistic Concurrency: Overview</span></span>](optimistic-concurrency-overview.md)  
 <span data-ttu-id="480f6-123">Erläutert die Begriffe, die sich in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] auf vollständige Parallelität beziehen.</span><span class="sxs-lookup"><span data-stu-id="480f6-123">Explains the terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
