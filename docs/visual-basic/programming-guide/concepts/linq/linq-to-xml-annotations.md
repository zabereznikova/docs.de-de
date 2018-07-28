---
title: LINQ to XML-Annotations2
ms.date: 07/20/2015
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
ms.openlocfilehash: a7b81b8c1856c11cb0c5e777f31986a330cf115f
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332921"
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="742ca-102">LINQ to XML-Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="742ca-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="742ca-103">Mit Anmerkungen in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie Objekte eines beliebigen Typs mit jeder beliebigen XML-Komponente in einer XML-Struktur verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="742ca-103">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="742ca-104">Zum Hinzufügen einer Anmerkung zu einer XML-Komponente, wie einem <xref:System.Xml.Linq.XElement> oder einem <xref:System.Xml.Linq.XAttribute>, rufen Sie die <xref:System.Xml.Linq.XObject.AddAnnotation%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="742ca-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="742ca-105">Anmerkungen werden nach Typ abgerufen.</span><span class="sxs-lookup"><span data-stu-id="742ca-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="742ca-106">Beachten Sie, dass Anmerkungen nicht Teil des XML-Infosets sind; sie werden nicht serialisiert oder deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="742ca-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="742ca-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="742ca-107">Methods</span></span>  
 <span data-ttu-id="742ca-108">Beim Arbeiten mit Anmerkungen können Sie die folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="742ca-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="742ca-109">Methode</span><span class="sxs-lookup"><span data-stu-id="742ca-109">Method</span></span>|<span data-ttu-id="742ca-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="742ca-110">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="742ca-111">Fügt der Anmerkungsliste eines <xref:System.Xml.Linq.XObject> ein Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="742ca-111">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="742ca-112">Ruft das erste Anmerkungsobjekt des angegebenen Typs aus einem <xref:System.Xml.Linq.XObject> ab.</span><span class="sxs-lookup"><span data-stu-id="742ca-112">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="742ca-113">Ruft eine Auflistung von Anmerkungen des angegebenen Typs für ein <xref:System.Xml.Linq.XObject> ab.</span><span class="sxs-lookup"><span data-stu-id="742ca-113">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="742ca-114">Entfernt die Anmerkungen des angegebenen Typs aus einem <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="742ca-114">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="742ca-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="742ca-115">See Also</span></span>  
 [<span data-ttu-id="742ca-116">Erweiterte LINQ to XML-Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="742ca-116">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
