---
title: Serialisieren von Objektdiagrammen, die XElement-Objekte enthalten (C#)
ms.date: 07/20/2015
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
ms.openlocfilehash: f51a026642563e1c1690d9a49220aae462840211
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a><span data-ttu-id="6d975-102">Serialisieren von Objektdiagrammen, die XElement-Objekte enthalten (C#)</span><span class="sxs-lookup"><span data-stu-id="6d975-102">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>
<span data-ttu-id="6d975-103">Dieses Thema bietet eine Einführung in das Serialisieren von Objektdiagrammen, die Verweise auf Objekte vom Typ <xref:System.Xml.Linq.XElement> enthalten.</span><span class="sxs-lookup"><span data-stu-id="6d975-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="6d975-104">Um diese Art der Serialisierung zu ermöglichen, implementiert <xref:System.Xml.Linq.XElement> die <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6d975-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="6d975-105">Beachten Sie, dass nur die <xref:System.Xml.Linq.XElement>-Klasse die Serialisierung implementiert.</span><span class="sxs-lookup"><span data-stu-id="6d975-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d975-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6d975-106">In This Section</span></span>  
  
|<span data-ttu-id="6d975-107">Thema</span><span class="sxs-lookup"><span data-stu-id="6d975-107">Topic</span></span>|<span data-ttu-id="6d975-108">description</span><span class="sxs-lookup"><span data-stu-id="6d975-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6d975-109">How to: Serialize Using XmlSerializer (C#) (Vorgehensweise: Serialisieren mit XmlSerializer (C#))</span><span class="sxs-lookup"><span data-stu-id="6d975-109">How to: Serialize Using XmlSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="6d975-110">Zeigt die Vorgehensweise beim Serialisieren mit <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6d975-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="6d975-111">How to: Serialize Using DataContractSerializer (C#) (Vorgehensweise: Serialisieren mit DataContractSerializer (C#))</span><span class="sxs-lookup"><span data-stu-id="6d975-111">How to: Serialize Using DataContractSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="6d975-112">Zeigt die Vorgehensweise beim Serialisieren mit <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6d975-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d975-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d975-113">See Also</span></span>  
 [<span data-ttu-id="6d975-114">Advanced LINQ to XML Programming (C#) (Erweiterte LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="6d975-114">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
