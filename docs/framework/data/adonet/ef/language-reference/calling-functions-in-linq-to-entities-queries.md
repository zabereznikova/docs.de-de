---
title: Aufrufen von Funktionen in LINQ to Entities-Abfragen
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 6fa1a7204a91a62c30e8683c449cc2be44132b4f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312084"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="bcebb-102">Aufrufen von Funktionen in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="bcebb-102">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="bcebb-103">In den Themen in diesem Abschnitt wird beschrieben, wie Funktionen in LINQ to Entities-Abfragen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bcebb-103">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="bcebb-104">Die <xref:System.Data.Objects.EntityFunctions>-Klasse und die <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse bieten im Rahmen des Entity Framework Zugriff auf kanonische Funktionen und Datenbankfunktionen.</span><span class="sxs-lookup"><span data-stu-id="bcebb-104">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="bcebb-105">Weitere Informationen finden Sie unter [Vorgehensweise: Aufrufen von kanonischen Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) und [Vorgehensweise: Aufrufen von Datenbankfunktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span><span class="sxs-lookup"><span data-stu-id="bcebb-105">For more information, see [How to: Call Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) and [How to: Call Database Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="bcebb-106">Zum Aufrufen einer benutzerdefinierten Funktion sind drei grundlegende Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="bcebb-106">The process for calling a custom function requires three basic steps:</span></span>  
  
1. <span data-ttu-id="bcebb-107">Definieren Sie im konzeptionellen Modell eine Funktion, oder deklarieren Sie im Speichermodell eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="bcebb-107">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2. <span data-ttu-id="bcebb-108">Fügen Sie der Anwendung eine Methode hinzu, und ordnen Sie es mit einem <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> der Funktion im Modell zu.</span><span class="sxs-lookup"><span data-stu-id="bcebb-108">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3. <span data-ttu-id="bcebb-109">Rufen Sie die Funktion in einer LINQ to Entities-Abfrage auf.</span><span class="sxs-lookup"><span data-stu-id="bcebb-109">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="bcebb-110">Weitere Informationen hierzu finden Sie in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="bcebb-110">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bcebb-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="bcebb-111">In This Section</span></span>  
 [<span data-ttu-id="bcebb-112">Vorgehensweise: Aufrufen kanonischer Funktionen</span><span class="sxs-lookup"><span data-stu-id="bcebb-112">How to: Call Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="bcebb-113">Vorgehensweise: Aufrufen von Datenbankfunktionen</span><span class="sxs-lookup"><span data-stu-id="bcebb-113">How to: Call Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [<span data-ttu-id="bcebb-114">Vorgehensweise: Aufrufen benutzerdefinierter Datenbankfunktionen</span><span class="sxs-lookup"><span data-stu-id="bcebb-114">How to: Call Custom Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="bcebb-115">Vorgehensweise: Aufrufen modelldefinierter Funktionen in Abfragen</span><span class="sxs-lookup"><span data-stu-id="bcebb-115">How to: Call Model-Defined Functions in Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="bcebb-116">Vorgehensweise: Aufrufen modelldefinierter Funktionen als Objektmethoden</span><span class="sxs-lookup"><span data-stu-id="bcebb-116">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="bcebb-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcebb-117">See also</span></span>

- [<span data-ttu-id="bcebb-118">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="bcebb-118">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
- [<span data-ttu-id="bcebb-119">Kanonische Funktionen</span><span class="sxs-lookup"><span data-stu-id="bcebb-119">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
- [<span data-ttu-id="bcebb-120">Übersicht über die EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="bcebb-120">.edmx File Overview</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [<span data-ttu-id="bcebb-121">Vorgehensweise: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell</span><span class="sxs-lookup"><span data-stu-id="bcebb-121">How to: Define Custom Functions in the Conceptual Model</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))
