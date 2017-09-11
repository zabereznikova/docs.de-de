---
title: Ein Ausdruck vom Typ &lt;Typ&gt; kann nicht abgefragt werden | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36593
- vbc36593
dev_langs:
- VB
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 84563c7339ffe7415017280d74a13d6501236da5
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a><span data-ttu-id="f1e14-102">Ein Ausdruck vom Typ &lt;Typ&gt; kann nicht abgefragt werden</span><span class="sxs-lookup"><span data-stu-id="f1e14-102">Expression of type &lt;type&gt; is not queryable</span></span>
<span data-ttu-id="f1e14-103">Ein Ausdruck vom Typ \<Typ > kann nicht abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="f1e14-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="f1e14-104">Sicherstellen Sie, dass einen Assembly und/oder Namespaceimport Import nicht für die LINQ-Anbieter fehlt.</span><span class="sxs-lookup"><span data-stu-id="f1e14-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="f1e14-105">Abfragbare Typen werden definiert die <xref:System.Linq>, <xref:System.Data.Linq>, und <xref:System.Xml.Linq>Namespaces.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="f1e14-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="f1e14-106">Importieren Sie eine oder mehrere dieser Namespaces zur LINQ-Abfragen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f1e14-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="f1e14-107">Die <xref:System.Linq>Namespaces können Sie Abfragen von Objekten wie z. B. Sammlungen und Arrays mithilfe von LINQ.</xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="f1e14-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="f1e14-108">Der <xref:System.Data.Linq>-Namespace ermöglicht es Ihnen, ADO.NET-Datasets und SQL Server-Datenbanken mithilfe von LINQ Abfragen.</xref:System.Data.Linq></span><span class="sxs-lookup"><span data-stu-id="f1e14-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="f1e14-109">Die <xref:System.Xml.Linq>Namespaces können Sie XML-Abfrage mithilfe von LINQ und XML-Features in Visual Basic verwenden.</xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="f1e14-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="f1e14-110">**Fehler-ID:** BC36593</span><span class="sxs-lookup"><span data-stu-id="f1e14-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f1e14-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f1e14-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="f1e14-112">Hinzufügen einer `Import` -Anweisung für die <xref:System.Linq>, <xref:System.Data.Linq>, oder <xref:System.Xml.Linq>Namespace zur Codedatei.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="f1e14-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="f1e14-113">Sie können auch Namespaces für das Projekt importieren, mit dem **Verweise** Seite im Projekt-Designer (**Mein Projekt**).</span><span class="sxs-lookup"><span data-stu-id="f1e14-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2.  <span data-ttu-id="f1e14-114">Stellen Sie sicher, dass des Typs, den Sie identifiziert haben, wie die Quelle der Abfrage ein abfragbarer Typ ist.</span><span class="sxs-lookup"><span data-stu-id="f1e14-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="f1e14-115">D. h. ein Typ, <xref:System.Collections.Generic.IEnumerable%601>oder <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> implementiert,</span><span class="sxs-lookup"><span data-stu-id="f1e14-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e14-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1e14-116">See Also</span></span>  
 <span data-ttu-id="f1e14-117"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="f1e14-117"><xref:System.Linq></span></span>   
 <span data-ttu-id="f1e14-118"><xref:System.Data.Linq></xref:System.Data.Linq></span><span class="sxs-lookup"><span data-stu-id="f1e14-118"><xref:System.Data.Linq></span></span>   
 <span data-ttu-id="f1e14-119"><xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="f1e14-119"><xref:System.Xml.Linq></span></span>   
<span data-ttu-id="f1e14-120"> [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="f1e14-120"> [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="f1e14-121"> [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="f1e14-121"> [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="f1e14-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="f1e14-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="f1e14-123"> [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f1e14-123"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="f1e14-124"> [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="f1e14-124"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="f1e14-125"> [Seite „Verweise“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="f1e14-125"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span></span>
