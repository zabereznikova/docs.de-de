---
title: Bearbeiten von XML-Daten mit XPathNavigator
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1f91616-3115-4264-9821-c66589d11d11
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 488651181aaec34c52f368d8829b1c556e6e746e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="editing-xml-data-using-xpathnavigator"></a><span data-ttu-id="6511f-102">Bearbeiten von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="6511f-102">Editing XML Data using XPathNavigator</span></span>
<span data-ttu-id="6511f-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt Methoden zum Einfügen, Ändern oder Entfernen von Knoten und Werten aus einem XML-Dokument bereit, das in einem <xref:System.Xml.XmlDocument>-Objekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="6511f-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to insert, modify and remove nodes and values from an XML document contained in an <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="6511f-104">Um eine der Methoden zum Einfügen, Ändern oder Entfernen von Knoten und Werten verwenden zu können, muss das <xref:System.Xml.XPath.XPathNavigator>-Objekt editierbar sein, d. h., seine <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Eigenschaft muss auf true festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="6511f-104">In order to use any of these methods to insert, modify, and remove nodes and values, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be true.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6511f-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6511f-105">In This Section</span></span>  
 [<span data-ttu-id="6511f-106">Einfügen von XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="6511f-106">Insert XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="6511f-107">In diesem Abschnitt wird beschrieben, wie gleichgeordnete Knoten, untergeordnete Knoten, Attributknoten und Werte mithilfe der <xref:System.Xml.XmlDocument>-Klasse in ein <xref:System.Xml.XPath.XPathNavigator>-Objekt eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6511f-107">Describes how to insert sibling, child, attribute nodes and values in to an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="6511f-108">Ändern von XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="6511f-108">Modify XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="6511f-109">In diesem Abschnitt wird beschrieben, wie Knoten und Werte in einem <xref:System.Xml.XmlDocument>-Objekt mithilfe der <xref:System.Xml.XPath.XPathNavigator>-Klasse geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6511f-109">Describes how to modify nodes and values in an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="6511f-110">Entfernen von XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="6511f-110">Remove XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="6511f-111">In diesem Abschnitt wird beschrieben, wie Knoten und Werte mithilfe der <xref:System.Xml.XmlDocument>-Klasse aus einem <xref:System.Xml.XPath.XPathNavigator>-Objekt entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="6511f-111">Describes how to remove nodes and values from an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6511f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6511f-112">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="6511f-113">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="6511f-113">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="6511f-114">Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument</span><span class="sxs-lookup"><span data-stu-id="6511f-114">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 [<span data-ttu-id="6511f-115">Auswählen, auswerten und Zuordnen von XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="6511f-115">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="6511f-116">Zugreifen auf XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="6511f-116">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="6511f-117">Schema-Validierung mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="6511f-117">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
