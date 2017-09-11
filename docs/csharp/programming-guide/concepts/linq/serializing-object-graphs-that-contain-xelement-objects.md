---
title: Serialisieren von Objektdiagrammen, die XElement-Objekte enthalten (C#)
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
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4e7b1d6365eb27596477de39577caa4144aa3501
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a><span data-ttu-id="8ef40-102">Serialisieren von Objektdiagrammen, die XElement-Objekte enthalten (C#)</span><span class="sxs-lookup"><span data-stu-id="8ef40-102">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>
<span data-ttu-id="8ef40-103">Dieses Thema bietet eine Einführung in das Serialisieren von Objektdiagrammen, die Verweise auf Objekte vom Typ <xref:System.Xml.Linq.XElement> enthalten.</span><span class="sxs-lookup"><span data-stu-id="8ef40-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="8ef40-104">Um diese Art der Serialisierung zu ermöglichen, implementiert <xref:System.Xml.Linq.XElement> die <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="8ef40-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="8ef40-105">Beachten Sie, dass nur die <xref:System.Xml.Linq.XElement>-Klasse die Serialisierung implementiert.</span><span class="sxs-lookup"><span data-stu-id="8ef40-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ef40-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8ef40-106">In This Section</span></span>  
  
|<span data-ttu-id="8ef40-107">Thema</span><span class="sxs-lookup"><span data-stu-id="8ef40-107">Topic</span></span>|<span data-ttu-id="8ef40-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8ef40-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8ef40-109">How to: Serialize Using XmlSerializer (C#) (Vorgehensweise: Serialisieren mit XmlSerializer (C#))</span><span class="sxs-lookup"><span data-stu-id="8ef40-109">How to: Serialize Using XmlSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="8ef40-110">Zeigt die Vorgehensweise beim Serialisieren mit <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8ef40-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="8ef40-111">How to: Serialize Using DataContractSerializer (C#) (Vorgehensweise: Serialisieren mit DataContractSerializer (C#))</span><span class="sxs-lookup"><span data-stu-id="8ef40-111">How to: Serialize Using DataContractSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="8ef40-112">Zeigt die Vorgehensweise beim Serialisieren mit <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8ef40-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ef40-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ef40-113">See Also</span></span>  
 [<span data-ttu-id="8ef40-114">Advanced LINQ to XML Programming (C#) (Erweiterte LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="8ef40-114">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

