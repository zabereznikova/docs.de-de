---
title: Bearbeiten von XML-Daten mit "XPathNavigator"
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b1f91616-3115-4264-9821-c66589d11d11
ms.openlocfilehash: 3b9225f1efcca0f4874a98f2b83d1964aacef735
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710959"
---
# <a name="editing-xml-data-using-xpathnavigator"></a><span data-ttu-id="034ba-102">Bearbeiten von XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="034ba-102">Editing XML Data using XPathNavigator</span></span>
<span data-ttu-id="034ba-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt Methoden zum Einfügen, Ändern oder Entfernen von Knoten und Werten aus einem XML-Dokument bereit, das in einem <xref:System.Xml.XmlDocument>-Objekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="034ba-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to insert, modify and remove nodes and values from an XML document contained in an <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="034ba-104">Um eine der Methoden zum Einfügen, Ändern oder Entfernen von Knoten und Werten verwenden zu können, muss das <xref:System.Xml.XPath.XPathNavigator>-Objekt editierbar sein, d. h., seine <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Eigenschaft muss auf true festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="034ba-104">In order to use any of these methods to insert, modify, and remove nodes and values, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be true.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="034ba-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="034ba-105">In This Section</span></span>  
 [<span data-ttu-id="034ba-106">Einfügen von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="034ba-106">Insert XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="034ba-107">In diesem Abschnitt wird beschrieben, wie gleichgeordnete Knoten, untergeordnete Knoten, Attributknoten und Werte mithilfe der <xref:System.Xml.XmlDocument>-Klasse in ein <xref:System.Xml.XPath.XPathNavigator>-Objekt eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="034ba-107">Describes how to insert sibling, child, attribute nodes and values in to an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="034ba-108">Ändern von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="034ba-108">Modify XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="034ba-109">In diesem Abschnitt wird beschrieben, wie Knoten und Werte in einem <xref:System.Xml.XmlDocument>-Objekt mithilfe der <xref:System.Xml.XPath.XPathNavigator>-Klasse geändert werden.</span><span class="sxs-lookup"><span data-stu-id="034ba-109">Describes how to modify nodes and values in an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="034ba-110">Entfernen von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="034ba-110">Remove XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="034ba-111">In diesem Abschnitt wird beschrieben, wie Knoten und Werte mithilfe der <xref:System.Xml.XmlDocument>-Klasse aus einem <xref:System.Xml.XPath.XPathNavigator>-Objekt entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="034ba-111">Describes how to remove nodes and values from an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="034ba-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="034ba-112">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="034ba-113">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="034ba-113">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="034ba-114">Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument</span><span class="sxs-lookup"><span data-stu-id="034ba-114">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)
- [<span data-ttu-id="034ba-115">Auswählen, Auswerten und Zuordnen von XML-Daten mithilfe von XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="034ba-115">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="034ba-116">Zugreifen auf XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="034ba-116">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="034ba-117">Schemavalidierung mithilfe von „XPathNavigator“</span><span class="sxs-lookup"><span data-stu-id="034ba-117">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
