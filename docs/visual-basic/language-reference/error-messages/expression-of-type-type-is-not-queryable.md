---
title: Ein Ausdruck vom Typ <type> kann nicht abgefragt werden
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: e61b4dac109f714b5cf25226d1029237ca77032d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409477"
---
# <a name="expression-of-type-type-is-not-queryable"></a><span data-ttu-id="c1fd3-102">Ein Ausdruck vom Typ \<type> kann nicht abgefragt werden</span><span class="sxs-lookup"><span data-stu-id="c1fd3-102">Expression of type \<type> is not queryable</span></span>
<span data-ttu-id="c1fd3-103">Ein Ausdruck vom Typ kann nicht abgefragt werden \<type> .</span><span class="sxs-lookup"><span data-stu-id="c1fd3-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="c1fd3-104">Stellen Sie sicher, dass für den LINQ-Anbieter kein Assemblyverweis und/oder Namespace Import vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c1fd3-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="c1fd3-105">Abfragbare Typen werden in den <xref:System.Linq> <xref:System.Data.Linq> <xref:System.Xml.Linq> Namespaces, und definiert.</span><span class="sxs-lookup"><span data-stu-id="c1fd3-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="c1fd3-106">Sie müssen einen oder mehrere dieser Namespaces importieren, um LINQ-Abfragen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c1fd3-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="c1fd3-107">Mit dem- <xref:System.Linq> Namespace können Sie Objekte wie Auflistungen und Arrays mithilfe von LINQ Abfragen.</span><span class="sxs-lookup"><span data-stu-id="c1fd3-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="c1fd3-108">Der <xref:System.Data.Linq> -Namespace ermöglicht es Ihnen, ADO.NET-Datasets und SQL Server-Datenbanken mithilfe von LINQ abzufragen.</span><span class="sxs-lookup"><span data-stu-id="c1fd3-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="c1fd3-109">Der <xref:System.Xml.Linq> -Namespace ermöglicht Ihnen das Abfragen von XML mithilfe von LINQ und die Verwendung von XML-Funktionen in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c1fd3-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="c1fd3-110">**Fehler-ID:** BC36593</span><span class="sxs-lookup"><span data-stu-id="c1fd3-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c1fd3-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c1fd3-111">To correct this error</span></span>  
  
1. <span data-ttu-id="c1fd3-112">Fügen Sie `Import` der Codedatei eine-Anweisung für den- <xref:System.Linq> ,- <xref:System.Data.Linq> oder- <xref:System.Xml.Linq> Namespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="c1fd3-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="c1fd3-113">Sie können Namespaces für Ihr Projekt auch importieren, indem Sie die Seite **Verweise** des Projekt-Designers (**mein Projekt**) verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1fd3-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2. <span data-ttu-id="c1fd3-114">Stellen Sie sicher, dass der Typ, den Sie als Quelle der Abfrage identifiziert haben, ein abfragbarer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="c1fd3-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="c1fd3-115">Das heißt, ein Typ, der <xref:System.Collections.Generic.IEnumerable%601> oder implementiert <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="c1fd3-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1fd3-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1fd3-116">See also</span></span>

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [<span data-ttu-id="c1fd3-117">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1fd3-117">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="c1fd3-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="c1fd3-118">LINQ</span></span>](../../programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="c1fd3-119">XML</span><span class="sxs-lookup"><span data-stu-id="c1fd3-119">XML</span></span>](../../programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="c1fd3-120">Verweise und die Imports-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c1fd3-120">References and the Imports Statement</span></span>](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="c1fd3-121">Imports-Anweisung (.NET-Namespace und Typ)</span><span class="sxs-lookup"><span data-stu-id="c1fd3-121">Imports Statement (.NET Namespace and Type)</span></span>](../statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="c1fd3-122">Seite "Verweise", Projekt-Designer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1fd3-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
