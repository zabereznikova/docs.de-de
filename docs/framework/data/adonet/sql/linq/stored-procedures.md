---
title: Gespeicherte Prozeduren
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: 80ea105eef33ebb2a0e52d91a631258400ea3dff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792482"
---
# <a name="stored-procedures"></a><span data-ttu-id="0a7d0-102">Gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0a7d0-102">Stored Procedures</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="0a7d0-103">verwendet Methoden in Ihrem Objektmodell, um gespeicherte Prozeduren in der Datenbank darzustellen.</span><span class="sxs-lookup"><span data-stu-id="0a7d0-103">uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="0a7d0-104">Sie kennzeichnen Methoden als gespeicherte Prozeduren, indem Sie das <xref:System.Data.Linq.Mapping.FunctionAttribute>-Attribut und bei Bedarf das <xref:System.Data.Linq.Mapping.ParameterAttribute>-Attribut anwenden.</span><span class="sxs-lookup"><span data-stu-id="0a7d0-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="0a7d0-105">Weitere Informationen finden Sie [unter LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="0a7d0-105">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="0a7d0-106">Entwickler, die Visual Studio verwenden, verwenden normalerweise die objektrelationaler Designer, um gespeicherte Prozeduren zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="0a7d0-106">Developers using Visual Studio would typically use the Object Relational Designer to map stored procedures.</span></span> <span data-ttu-id="0a7d0-107">Dieser Abschnitt erläutert das Bilden und Aufrufen dieser Methoden in Ihrer Anwendung, wenn Sie den Code selbst schreiben.</span><span class="sxs-lookup"><span data-stu-id="0a7d0-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a7d0-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0a7d0-108">In This Section</span></span>  
 [<span data-ttu-id="0a7d0-109">Vorgehensweise: Rowsets zurückgeben</span><span class="sxs-lookup"><span data-stu-id="0a7d0-109">How to: Return Rowsets</span></span>](how-to-return-rowsets.md)  
 <span data-ttu-id="0a7d0-110">Beschreibt das Zurückgeben von Datenzeilen und zeigt, wie ein Eingabeparameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0a7d0-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="0a7d0-111">Vorgehensweise: Verwenden von gespeicherten Prozeduren, die Parameter annehmen</span><span class="sxs-lookup"><span data-stu-id="0a7d0-111">How to: Use Stored Procedures that Take Parameters</span></span>](how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="0a7d0-112">Beschreibt die Verwendung von Eingabe- und Ausgabeparametern.</span><span class="sxs-lookup"><span data-stu-id="0a7d0-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="0a7d0-113">Vorgehensweise: Verwenden gespeicherter Prozeduren für mehrere Ergebnis Formen</span><span class="sxs-lookup"><span data-stu-id="0a7d0-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="0a7d0-114">Beschreibt, wie in der gleichen gespeicherten Prozedur mehrere Formen zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="0a7d0-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="0a7d0-115">Vorgehensweise: Verwenden gespeicherter Prozeduren für sequenzielle Ergebnis Formen</span><span class="sxs-lookup"><span data-stu-id="0a7d0-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="0a7d0-116">Beschreibt, wie die Unterstützung für mehrere Formen gewährleistet werden kann, wenn die Rückgabesequenz bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="0a7d0-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="0a7d0-117">Anpassen von Operationen durch Verwendung von gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0a7d0-117">Customizing Operations By Using Stored Procedures</span></span>](customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="0a7d0-118">Beschreibt, wie gespeicherte Prozeduren zur Implementierung von Insert-, Update- und Delete-Operationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a7d0-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="0a7d0-119">Anpassen von Operationen durch ausschließliche Verwendung von gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0a7d0-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="0a7d0-120">Beschreibt, wie ausschließlich gespeicherte Prozeduren zur Implementierung von Insert-, Update- und Delete-Operationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a7d0-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0a7d0-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="0a7d0-121">Related Sections</span></span>  
 [<span data-ttu-id="0a7d0-122">Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0a7d0-122">Programming Guide</span></span>](programming-guide.md)  
 <span data-ttu-id="0a7d0-123">Stellt Informationen zur Erstellung und Nutzung Ihres [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Objektmodells bereit.</span><span class="sxs-lookup"><span data-stu-id="0a7d0-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="0a7d0-124">Exemplarische Vorgehensweise: Ausschließliche Verwendung von gespeicherten Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a7d0-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="0a7d0-125">Umfasst Prozeduren, die veranschaulichen, wie gespeicherte Prozeduren in Visual Basic verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a7d0-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="0a7d0-126">Exemplarische Vorgehensweise: Ausschließliche Verwendung von gespeicherten Prozeduren (C#)</span><span class="sxs-lookup"><span data-stu-id="0a7d0-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="0a7d0-127">Umfasst Prozeduren, die veranschaulichen, wie gespeicherte Prozeduren in C# verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a7d0-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
