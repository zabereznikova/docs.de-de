---
title: LINQ to XML-Annotations2 | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 97f5386630ba687e4401ee0cfb70f7170e273a53
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017


---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="96632-102">LINQ to XML-Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="96632-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="96632-103">Anmerkungen in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] ermöglichen es Ihnen, alle Objekte eines beliebigen Typs mit einer XML-Komponente in eine XML-Struktur verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="96632-103">Annotations in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="96632-104">Zum Hinzufügen einer Anmerkung zu einer XML-Komponente, wie z. B. ein <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XAttribute>, rufen Sie die <xref:System.Xml.Linq.XObject.AddAnnotation%2A>-Methode.</xref:System.Xml.Linq.XObject.AddAnnotation%2A> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="96632-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="96632-105">Anmerkungen werden nach Typ abgerufen.</span><span class="sxs-lookup"><span data-stu-id="96632-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="96632-106">Beachten Sie, dass Anmerkungen nicht Teil des XML-Infosets sind; sie werden nicht serialisiert oder deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="96632-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96632-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="96632-107">Methods</span></span>  
 <span data-ttu-id="96632-108">Beim Arbeiten mit Anmerkungen können Sie die folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="96632-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="96632-109">Methode</span><span class="sxs-lookup"><span data-stu-id="96632-109">Method</span></span>|<span data-ttu-id="96632-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96632-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="96632-111"><xref:System.Xml.Linq.XObject.AddAnnotation%2A></xref:System.Xml.Linq.XObject.AddAnnotation%2A></span><span class="sxs-lookup"><span data-stu-id="96632-111"><xref:System.Xml.Linq.XObject.AddAnnotation%2A></span></span>|<span data-ttu-id="96632-112">Fügt ein Objekt auf der Anmerkungsliste eine <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="96632-112">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="96632-113"><xref:System.Xml.Linq.XObject.Annotation%2A></xref:System.Xml.Linq.XObject.Annotation%2A></span><span class="sxs-lookup"><span data-stu-id="96632-113"><xref:System.Xml.Linq.XObject.Annotation%2A></span></span>|<span data-ttu-id="96632-114">Ruft das erste Anmerkungsobjekt des angegebenen Typs aus einer <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="96632-114">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="96632-115"><xref:System.Xml.Linq.XObject.Annotations%2A></xref:System.Xml.Linq.XObject.Annotations%2A></span><span class="sxs-lookup"><span data-stu-id="96632-115"><xref:System.Xml.Linq.XObject.Annotations%2A></span></span>|<span data-ttu-id="96632-116">Ruft eine Auflistung von Anmerkungen des angegebenen Typs für eine <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="96632-116">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="96632-117"><xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></span><span class="sxs-lookup"><span data-stu-id="96632-117"><xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></span></span>|<span data-ttu-id="96632-118">Entfernt die Anmerkungen des angegebenen Typs aus einer <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="96632-118">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96632-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96632-119">See Also</span></span>  
 [<span data-ttu-id="96632-120">Erweiterte LINQ to XML-Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96632-120">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
