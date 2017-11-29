---
title: 'Gewusst wie: Aufrufen modelldefinierter Funktionen in Abfragen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 179c00def6b5a810806d536a8728cbbc544b1084
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-model-defined-functions-in-queries"></a><span data-ttu-id="2d86c-102">Gewusst wie: Aufrufen modelldefinierter Funktionen in Abfragen</span><span class="sxs-lookup"><span data-stu-id="2d86c-102">How to: Call Model-Defined Functions in Queries</span></span>
<span data-ttu-id="2d86c-103">In diesem Thema wird beschrieben, wie Funktionen, die im konzeptionellen Modell definiert sind, aus [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfragen heraus aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2d86c-103">This topic describes how to call functions that are defined in the conceptual model from within [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="2d86c-104">Das nachfolgende Verfahren bietet einen allgemeinen Überblick über den Aufruf einer im Modell definierten Funktion aus einer [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfrage heraus.</span><span class="sxs-lookup"><span data-stu-id="2d86c-104">The procedure below provides a high-level outline for calling a model-defined function from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="2d86c-105">Das folgende Beispiel enthält weitere Details zu den Schritten in der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2d86c-105">The example that follows provides more detail about the steps in the procedure.</span></span> <span data-ttu-id="2d86c-106">In dem Verfahren wird davon ausgegangen, dass eine Funktion im konzeptionellen Modell definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2d86c-106">The procedure assumes that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="2d86c-107">Weitere Informationen finden Sie unter [wie: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).</span><span class="sxs-lookup"><span data-stu-id="2d86c-107">For more information, see [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).</span></span>  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a><span data-ttu-id="2d86c-108">So rufen Sie eine im konzeptionellen Modell definierte Funktion auf</span><span class="sxs-lookup"><span data-stu-id="2d86c-108">To call a function defined in the conceptual model</span></span>  
  
1.  <span data-ttu-id="2d86c-109">Fügen Sie der Anwendung, die der im konzeptionellen Modell definierten Funktion zugeordnet ist, eine Common Language Runtime (CLR)-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="2d86c-109">Add a common language runtime (CLR) method to your application that maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="2d86c-110">Zum Zuordnen der Methode müssen Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> für die Methode übernehmen.</span><span class="sxs-lookup"><span data-stu-id="2d86c-110">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="2d86c-111">Beachten Sie, dass der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A>-Parameter und der <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A>-Parameter des Attributs den Namespacenamen bzw. den Funktionsnamen im konzeptionellen Modell darstellen.</span><span class="sxs-lookup"><span data-stu-id="2d86c-111">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="2d86c-112">Bei der Funktionsnamenauflösung für LINQ wird die Groß-/Kleinschreibung berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="2d86c-112">Function name resolution for LINQ is case sensitive.</span></span>  
  
2.  <span data-ttu-id="2d86c-113">Rufen Sie die Funktion in einer [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfrage auf.</span><span class="sxs-lookup"><span data-stu-id="2d86c-113">Call the function in a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d86c-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2d86c-114">Example</span></span>  
 <span data-ttu-id="2d86c-115">Im folgenden Beispiel wird veranschaulicht, wie eine Funktion, die im konzeptionellen Modell definiert wird, aus einer [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfrage heraus aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2d86c-115">The following example demonstrates how to call a function that is defined in the conceptual model from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="2d86c-116">Im Beispiel wird das Modell "School" verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d86c-116">The example uses the School model.</span></span> <span data-ttu-id="2d86c-117">Informationen über das Modell "School" finden Sie unter [Erstellen der Beispieldatenbank "School"](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) und [der Schule EDMX-Datei generieren](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758).</span><span class="sxs-lookup"><span data-stu-id="2d86c-117">For information about the School model, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) and [Generating the School .edmx File](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758).</span></span>  
  
 <span data-ttu-id="2d86c-118">Die folgende konzeptionelle Modellfunktion gibt die Anzahl der Jahre zurück, die seit der Einstellung einer Lehrkraft vergangen sind.</span><span class="sxs-lookup"><span data-stu-id="2d86c-118">The following conceptual model function returns the number of years since an instructor was hired.</span></span> <span data-ttu-id="2d86c-119">Informationen zum Hinzufügen von der Funktion mit einem konzeptionellen Modell finden Sie unter [wie: Definieren von benutzerdefinierten Funktionen im konzeptionellen Modell](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).)</span><span class="sxs-lookup"><span data-stu-id="2d86c-119">For information about adding the function to a conceptual model, see [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).)</span></span>  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="2d86c-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2d86c-120">Example</span></span>  
 <span data-ttu-id="2d86c-121">Fügen Sie der Anwendung danach die folgende Methode hinzu, und verwenden Sie ein <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>, um sie der Funktion im konzeptionellen Modell zuzuordnen:</span><span class="sxs-lookup"><span data-stu-id="2d86c-121">Next, add the following method to your application and use an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to map it to the conceptual model function:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="2d86c-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2d86c-122">Example</span></span>  
 <span data-ttu-id="2d86c-123">Jetzt können Sie die im konzeptionellen Modell definierte Funktion aus einer [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfrage heraus aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2d86c-123">Now you can call the conceptual model function from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="2d86c-124">Im folgenden Code wird die Methode aufgerufen, um alle Lehrkräfte anzuzeigen, die vor mehr als zehn Jahren eingestellt wurden:</span><span class="sxs-lookup"><span data-stu-id="2d86c-124">The following code calls the method to display all instructors that were hired more than ten years ago:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="2d86c-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d86c-125">See Also</span></span>  
 [<span data-ttu-id="2d86c-126">Übersicht über die EDMX-Datei</span><span class="sxs-lookup"><span data-stu-id="2d86c-126">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="2d86c-127">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="2d86c-127">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [<span data-ttu-id="2d86c-128">Aufrufen von Funktionen in LINQ to Entities-Abfragen</span><span class="sxs-lookup"><span data-stu-id="2d86c-128">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [<span data-ttu-id="2d86c-129">Vorgehensweise: Aufrufen Modelldefinierter Funktionen als Objektmethoden</span><span class="sxs-lookup"><span data-stu-id="2d86c-129">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)
