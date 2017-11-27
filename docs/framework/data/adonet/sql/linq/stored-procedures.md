---
title: Gespeicherte Prozeduren
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1cf8d155dd04cd4f7b3f860186428c14ce4e462e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="stored-procedures"></a><span data-ttu-id="a4842-102">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="a4842-102">Stored Procedures</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a4842-103">verwendet Methoden in Ihrem Objektmodell, um gespeicherte Prozeduren in der Datenbank darzustellen.</span><span class="sxs-lookup"><span data-stu-id="a4842-103"> uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="a4842-104">Sie kennzeichnen Methoden als gespeicherte Prozeduren, indem Sie das <xref:System.Data.Linq.Mapping.FunctionAttribute>-Attribut und bei Bedarf das <xref:System.Data.Linq.Mapping.ParameterAttribute>-Attribut anwenden.</span><span class="sxs-lookup"><span data-stu-id="a4842-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="a4842-105">Weitere Informationen finden Sie unter [das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="a4842-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="a4842-106">Entwickler mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] in der Regel die [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] gespeicherte Prozeduren zuordnen.</span><span class="sxs-lookup"><span data-stu-id="a4842-106">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map stored procedures.</span></span> <span data-ttu-id="a4842-107">Dieser Abschnitt erläutert das Bilden und Aufrufen dieser Methoden in Ihrer Anwendung, wenn Sie den Code selbst schreiben.</span><span class="sxs-lookup"><span data-stu-id="a4842-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a4842-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a4842-108">In This Section</span></span>  
 [<span data-ttu-id="a4842-109">Vorgehensweise: Zurückgeben von Rowsets</span><span class="sxs-lookup"><span data-stu-id="a4842-109">How to: Return Rowsets</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 <span data-ttu-id="a4842-110">Beschreibt das Zurückgeben von Datenzeilen und zeigt, wie ein Eingabeparameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a4842-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="a4842-111">Vorgehensweise: Verwenden von gespeicherten Prozeduren, die Parameter</span><span class="sxs-lookup"><span data-stu-id="a4842-111">How to: Use Stored Procedures that Take Parameters</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="a4842-112">Beschreibt die Verwendung von Eingabe- und Ausgabeparametern.</span><span class="sxs-lookup"><span data-stu-id="a4842-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="a4842-113">Vorgehensweise: Verwenden von gespeicherten Prozeduren, die mehrere Ergebnisformen zugeordnet</span><span class="sxs-lookup"><span data-stu-id="a4842-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="a4842-114">Beschreibt, wie in der gleichen gespeicherten Prozedur mehrere Formen zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="a4842-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="a4842-115">Vorgehensweise: Verwenden von gespeicherten Prozeduren, die sequenziellen Ergebnisformen zugeordnet</span><span class="sxs-lookup"><span data-stu-id="a4842-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="a4842-116">Beschreibt, wie die Unterstützung für mehrere Formen gewährleistet werden kann, wenn die Rückgabesequenz bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="a4842-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="a4842-117">Anpassen von Operationen durch Verwendung von gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="a4842-117">Customizing Operations By Using Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="a4842-118">Beschreibt, wie gespeicherte Prozeduren zur Implementierung von Insert-, Update- und Delete-Operationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4842-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="a4842-119">Anpassen von Operationen mit gespeicherten Prozeduren ausschließlich</span><span class="sxs-lookup"><span data-stu-id="a4842-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="a4842-120">Beschreibt, wie ausschließlich gespeicherte Prozeduren zur Implementierung von Insert-, Update- und Delete-Operationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4842-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a4842-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a4842-121">Related Sections</span></span>  
 [<span data-ttu-id="a4842-122">Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a4842-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="a4842-123">Stellt Informationen zur Erstellung und Nutzung Ihres [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Objektmodells bereit.</span><span class="sxs-lookup"><span data-stu-id="a4842-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="a4842-124">Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4842-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="a4842-125">Umfasst Prozeduren, die veranschaulichen, wie gespeicherte Prozeduren in Visual Basic verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4842-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="a4842-126">Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (c#)</span><span class="sxs-lookup"><span data-stu-id="a4842-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="a4842-127">Umfasst Prozeduren, die veranschaulichen, wie gespeicherte Prozeduren in C# verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4842-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
