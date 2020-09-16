---
title: Aufrufen von Funktionen in LINQ to Entities-Abfragen
description: Verwenden Sie diese Artikel, um zu erfahren, wie die Klassen EntityFunctions und SqlFunctions Zugriff auf kanonische Funktionen und Datenbankfunktionen als Teil der Entity Framework bereitstellen.
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: eb206e9b331da1ae442c1f310e78fec5c6b57e82
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546047"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="cd164-103">Aufrufen von Funktionen in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="cd164-103">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="cd164-104">In den Themen in diesem Abschnitt wird beschrieben, wie Funktionen in LINQ to Entities-Abfragen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cd164-104">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="cd164-105">Die <xref:System.Data.Objects.EntityFunctions>-Klasse und die <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse bieten im Rahmen des Entity Framework Zugriff auf kanonische Funktionen und Datenbankfunktionen.</span><span class="sxs-lookup"><span data-stu-id="cd164-105">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="cd164-106">Weitere Informationen finden Sie unter Gewusst [wie: Abrufen von kanonischen Funktionen](how-to-call-canonical-functions.md) und Gewusst [wie: Abrufen von Datenbankfunktionen](how-to-call-database-functions.md).</span><span class="sxs-lookup"><span data-stu-id="cd164-106">For more information, see [How to: Call Canonical Functions](how-to-call-canonical-functions.md) and [How to: Call Database Functions](how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="cd164-107">Zum Aufrufen einer benutzerdefinierten Funktion sind drei grundlegende Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="cd164-107">The process for calling a custom function requires three basic steps:</span></span>  
  
1. <span data-ttu-id="cd164-108">Definieren Sie im konzeptionellen Modell eine Funktion, oder deklarieren Sie im Speichermodell eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="cd164-108">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2. <span data-ttu-id="cd164-109">Fügen Sie der Anwendung eine Methode hinzu, und ordnen Sie es mit einem <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> der Funktion im Modell zu.</span><span class="sxs-lookup"><span data-stu-id="cd164-109">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3. <span data-ttu-id="cd164-110">Rufen Sie die Funktion in einer LINQ to Entities-Abfrage auf.</span><span class="sxs-lookup"><span data-stu-id="cd164-110">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="cd164-111">Weitere Informationen hierzu finden Sie in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="cd164-111">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd164-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cd164-112">In This Section</span></span>  
 [<span data-ttu-id="cd164-113">Vorgehensweise: Aufrufen kanonischer Funktionen</span><span class="sxs-lookup"><span data-stu-id="cd164-113">How to: Call Canonical Functions</span></span>](how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="cd164-114">Vorgehensweise: Aufrufen von Datenbankfunktionen</span><span class="sxs-lookup"><span data-stu-id="cd164-114">How to: Call Database Functions</span></span>](how-to-call-database-functions.md)  
  
 [<span data-ttu-id="cd164-115">Vorgehensweise: Aufrufen benutzerdefinierter Datenbankfunktionen</span><span class="sxs-lookup"><span data-stu-id="cd164-115">How to: Call Custom Database Functions</span></span>](how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="cd164-116">Vorgehensweise: Aufrufen modelldefinierter Funktionen in Abfragen</span><span class="sxs-lookup"><span data-stu-id="cd164-116">How to: Call Model-Defined Functions in Queries</span></span>](how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="cd164-117">Vorgehensweise: Aufrufen modelldefinierter Funktionen als Objektmethoden</span><span class="sxs-lookup"><span data-stu-id="cd164-117">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="cd164-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd164-118">See also</span></span>

- [<span data-ttu-id="cd164-119">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="cd164-119">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="cd164-120">Kanonische Funktionen</span><span class="sxs-lookup"><span data-stu-id="cd164-120">Canonical Functions</span></span>](canonical-functions.md)
- <span data-ttu-id="cd164-121">[Übersicht über die EDMX-Datei](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cd164-121">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- <span data-ttu-id="cd164-122">[Gewusst wie: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cd164-122">[How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span></span>
