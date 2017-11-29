---
title: Aufrufen von Funktionen in LINQ to Entities-Abfragen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6e50147d356ad9e389a87868205bb9b8b6b3e7b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="dd2df-102">Aufrufen von Funktionen in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="dd2df-102">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="dd2df-103">In den Themen in diesem Abschnitt wird beschrieben, wie Funktionen in LINQ to Entities-Abfragen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dd2df-103">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="dd2df-104">Die <xref:System.Data.Objects.EntityFunctions>-Klasse und die <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse bieten im Rahmen des Entity Framework Zugriff auf kanonische Funktionen und Datenbankfunktionen.</span><span class="sxs-lookup"><span data-stu-id="dd2df-104">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="dd2df-105">Weitere Informationen finden Sie unter [Vorgehensweise: Aufrufen von kanonischen Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) und [Vorgehensweise: Aufrufen von Datenbankfunktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span><span class="sxs-lookup"><span data-stu-id="dd2df-105">For more information, see [How to: Call Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) and [How to: Call Database Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="dd2df-106">Zum Aufrufen einer benutzerdefinierten Funktion sind drei grundlegende Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="dd2df-106">The process for calling a custom function requires three basic steps:</span></span>  
  
1.  <span data-ttu-id="dd2df-107">Definieren Sie im konzeptionellen Modell eine Funktion, oder deklarieren Sie im Speichermodell eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="dd2df-107">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2.  <span data-ttu-id="dd2df-108">Fügen Sie der Anwendung eine Methode hinzu, und ordnen Sie es mit einem <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> der Funktion im Modell zu.</span><span class="sxs-lookup"><span data-stu-id="dd2df-108">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3.  <span data-ttu-id="dd2df-109">Rufen Sie die Funktion in einer LINQ to Entities-Abfrage auf.</span><span class="sxs-lookup"><span data-stu-id="dd2df-109">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="dd2df-110">Weitere Informationen hierzu finden Sie in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="dd2df-110">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd2df-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dd2df-111">In This Section</span></span>  
 [<span data-ttu-id="dd2df-112">Vorgehensweise: Aufrufen von kanonischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="dd2df-112">How to: Call Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="dd2df-113">Vorgehensweise: Aufrufen von Datenbankfunktionen</span><span class="sxs-lookup"><span data-stu-id="dd2df-113">How to: Call Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [<span data-ttu-id="dd2df-114">Vorgehensweise: Aufrufen benutzerdefinierter Datenbankfunktionen</span><span class="sxs-lookup"><span data-stu-id="dd2df-114">How to: Call Custom Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="dd2df-115">Vorgehensweise: Aufrufen Modelldefinierter Funktionen in Abfragen</span><span class="sxs-lookup"><span data-stu-id="dd2df-115">How to: Call Model-Defined Functions in Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="dd2df-116">Vorgehensweise: Aufrufen Modelldefinierter Funktionen als Objektmethoden</span><span class="sxs-lookup"><span data-stu-id="dd2df-116">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="dd2df-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd2df-117">See Also</span></span>  
 [<span data-ttu-id="dd2df-118">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="dd2df-118">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [<span data-ttu-id="dd2df-119">Canonical Functions (Kanonische Funktionen)</span><span class="sxs-lookup"><span data-stu-id="dd2df-119">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)  
 [<span data-ttu-id="dd2df-120">Übersicht über die EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="dd2df-120">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="dd2df-121">Vorgehensweise: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell</span><span class="sxs-lookup"><span data-stu-id="dd2df-121">How to: Define Custom Functions in the Conceptual Model</span></span>](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)
