---
title: LINQ to XML-Anmerkungen 3
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3fa8715deac8776f7a512439ee055be6faf4649f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="d4983-102">LINQ to XML-Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="d4983-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="d4983-103">Mit Anmerkungen in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie Objekte eines beliebigen Typs mit jeder beliebigen XML-Komponente in einer XML-Struktur verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="d4983-103">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="d4983-104">Zum Hinzufügen einer Anmerkung zu einer XML-Komponente, wie einem <xref:System.Xml.Linq.XElement> oder einem <xref:System.Xml.Linq.XAttribute>, rufen Sie die <xref:System.Xml.Linq.XObject.AddAnnotation%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="d4983-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="d4983-105">Anmerkungen werden nach Typ abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d4983-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="d4983-106">Beachten Sie, dass Anmerkungen nicht Teil des XML-Infosets sind; sie werden nicht serialisiert oder deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="d4983-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4983-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="d4983-107">Methods</span></span>  
 <span data-ttu-id="d4983-108">Beim Arbeiten mit Anmerkungen können Sie die folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="d4983-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="d4983-109">Methode</span><span class="sxs-lookup"><span data-stu-id="d4983-109">Method</span></span>|<span data-ttu-id="d4983-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4983-110">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="d4983-111">Fügt der Anmerkungsliste eines <xref:System.Xml.Linq.XObject> ein Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="d4983-111">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="d4983-112">Ruft das erste Anmerkungsobjekt des angegebenen Typs aus einem <xref:System.Xml.Linq.XObject> ab.</span><span class="sxs-lookup"><span data-stu-id="d4983-112">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="d4983-113">Ruft eine Auflistung von Anmerkungen des angegebenen Typs für ein <xref:System.Xml.Linq.XObject> ab.</span><span class="sxs-lookup"><span data-stu-id="d4983-113">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="d4983-114">Entfernt die Anmerkungen des angegebenen Typs aus einem <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="d4983-114">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4983-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4983-115">See Also</span></span>  
 [<span data-ttu-id="d4983-116">Advanced LINQ to XML Programming (C#) (Erweiterte LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="d4983-116">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

