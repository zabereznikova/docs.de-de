---
title: LINQ to XML-Annotations2
ms.date: 07/20/2015
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
ms.openlocfilehash: edf8e0126c632deae6b6d4c235c4880d7b8687e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831748"
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="cea36-102">LINQ to XML-Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="cea36-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="cea36-103">Mit Anmerkungen in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie Objekte eines beliebigen Typs mit jeder beliebigen XML-Komponente in einer XML-Struktur verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="cea36-103">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="cea36-104">Zum Hinzufügen einer Anmerkung zu einer XML-Komponente, wie einem <xref:System.Xml.Linq.XElement> oder einem <xref:System.Xml.Linq.XAttribute>, rufen Sie die <xref:System.Xml.Linq.XObject.AddAnnotation%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="cea36-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="cea36-105">Anmerkungen werden nach Typ abgerufen.</span><span class="sxs-lookup"><span data-stu-id="cea36-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="cea36-106">Beachten Sie, dass Anmerkungen nicht Teil des XML-Infosets sind; sie werden nicht serialisiert oder deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="cea36-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cea36-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="cea36-107">Methods</span></span>  
 <span data-ttu-id="cea36-108">Beim Arbeiten mit Anmerkungen können Sie die folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="cea36-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="cea36-109">Methode</span><span class="sxs-lookup"><span data-stu-id="cea36-109">Method</span></span>|<span data-ttu-id="cea36-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cea36-110">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="cea36-111">Fügt der Anmerkungsliste eines <xref:System.Xml.Linq.XObject> ein Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="cea36-111">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="cea36-112">Ruft das erste Anmerkungsobjekt des angegebenen Typs aus einem <xref:System.Xml.Linq.XObject> ab.</span><span class="sxs-lookup"><span data-stu-id="cea36-112">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="cea36-113">Ruft eine Auflistung von Anmerkungen des angegebenen Typs für ein <xref:System.Xml.Linq.XObject> ab.</span><span class="sxs-lookup"><span data-stu-id="cea36-113">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="cea36-114">Entfernt die Anmerkungen des angegebenen Typs aus einem <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="cea36-114">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cea36-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cea36-115">See also</span></span>

- [<span data-ttu-id="cea36-116">Erweiterte LINQ to XML-Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cea36-116">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
