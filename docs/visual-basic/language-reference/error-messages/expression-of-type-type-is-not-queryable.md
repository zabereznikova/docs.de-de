---
title: Ein Ausdruck vom Typ &lt;Typ&gt; kann nicht abgefragt werden
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: ce0831e0770e5733759c072b8d7c6f20b56f771b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521490"
---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a><span data-ttu-id="f75eb-102">Ein Ausdruck vom Typ &lt;Typ&gt; kann nicht abgefragt werden</span><span class="sxs-lookup"><span data-stu-id="f75eb-102">Expression of type &lt;type&gt; is not queryable</span></span>
<span data-ttu-id="f75eb-103">Ein Ausdruck vom Typ \<Typs > kann nicht abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="f75eb-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="f75eb-104">Stellen Sie sicher, dass eine Assembly und/oder Namespaceimport importieren keine für den LINQ-Anbieter fehlt.</span><span class="sxs-lookup"><span data-stu-id="f75eb-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="f75eb-105">Abfragbare Typen werden definiert, der <xref:System.Linq>, <xref:System.Data.Linq>, und <xref:System.Xml.Linq> Namespaces.</span><span class="sxs-lookup"><span data-stu-id="f75eb-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="f75eb-106">Importieren Sie eine oder mehrere dieser Namespaces zur LINQ-Abfragen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f75eb-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="f75eb-107">Die <xref:System.Linq> Namespace können Sie Abfrageobjekte wie z. B. Sammlungen und Arrays mithilfe von LINQ.</span><span class="sxs-lookup"><span data-stu-id="f75eb-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="f75eb-108">Die <xref:System.Data.Linq> -Namespace ermöglicht Ihnen, ADO.NET Datasets und SQL Server-Datenbanken mithilfe von LINQ abzufragen.</span><span class="sxs-lookup"><span data-stu-id="f75eb-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="f75eb-109">Die <xref:System.Xml.Linq> Namespace können Sie XML-Abfrage mithilfe von LINQ und XML-Features in Visual Basic verwenden.</span><span class="sxs-lookup"><span data-stu-id="f75eb-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="f75eb-110">**Fehler-ID:** BC36593</span><span class="sxs-lookup"><span data-stu-id="f75eb-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f75eb-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f75eb-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="f75eb-112">Hinzufügen einer `Import` -Anweisung für die <xref:System.Linq>, <xref:System.Data.Linq>, oder <xref:System.Xml.Linq> Namespace Ihrer Codedatei.</span><span class="sxs-lookup"><span data-stu-id="f75eb-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="f75eb-113">Sie können auch Namespaces für Ihr Projekt importieren, mit der **Verweise** auf der Seite im Projekt-Designer (**Mein Projekt**).</span><span class="sxs-lookup"><span data-stu-id="f75eb-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2.  <span data-ttu-id="f75eb-114">Stellen Sie sicher, dass des Typs, den Sie identifiziert haben, wie die Quelle der Abfrage ein abfragbarer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="f75eb-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="f75eb-115">D. h. einen Typ, der implementiert <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="f75eb-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f75eb-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f75eb-116">See also</span></span>
- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [<span data-ttu-id="f75eb-117">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f75eb-117">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f75eb-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="f75eb-118">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="f75eb-119">XML</span><span class="sxs-lookup"><span data-stu-id="f75eb-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="f75eb-120">Verweise und die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f75eb-120">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="f75eb-121">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="f75eb-121">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="f75eb-122">Seite „Verweise“, Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f75eb-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
