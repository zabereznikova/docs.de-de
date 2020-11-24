---
title: Einfügen von XML-Daten mit "XPathNavigator"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 2ed8c28b-b88d-4be7-9c87-92df01f0821f
ms.openlocfilehash: 1a0fa96c0fc4db1ab005961728e81b6940cd00e6
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822711"
---
# <a name="insert-xml-data-using-xpathnavigator"></a><span data-ttu-id="2d67e-102">Einfügen von XML-Daten mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="2d67e-102">Insert XML Data using XPathNavigator</span></span>
<span data-ttu-id="2d67e-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt eine Gruppe von Methoden bereit, die zum Einfügen von nebengeordneten und untergeordneten Knoten sowie von Attributknoten in ein XML-Dokument verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d67e-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to insert sibling, child, and attribute nodes in an XML document.</span></span> <span data-ttu-id="2d67e-104">Diese Methoden können nur dann verwendet werden, wenn das <xref:System.Xml.XPath.XPathNavigator>-Objekt bearbeitet werden kann, d. h. seine <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Eigenschaft muss `true` sein.</span><span class="sxs-lookup"><span data-stu-id="2d67e-104">In order to use these methods, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be `true`.</span></span>  
  
 <span data-ttu-id="2d67e-105"><xref:System.Xml.XPath.XPathNavigator>-Objekte, die ein XML-Dokument bearbeiten können, werden von der <xref:System.Xml.XmlDocument.CreateNavigator%2A>-Methode der <xref:System.Xml.XmlDocument>-Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-105"><xref:System.Xml.XPath.XPathNavigator> objects that can edit an XML document are created by the <xref:System.Xml.XmlDocument.CreateNavigator%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="2d67e-106"><xref:System.Xml.XPath.XPathNavigator>-Objekte, die von der <xref:System.Xml.XPath.XPathDocument>-Klasse erstellt werden, sind schreibgeschützt. Der Versuch, die Bearbeitungsmethoden eines <xref:System.Xml.XPath.XPathNavigator>-Objekts anzuwenden, das von einem <xref:System.Xml.XPath.XPathDocument>-Objekt erstellt wurde, führt zu einer <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="2d67e-106"><xref:System.Xml.XPath.XPathNavigator> objects created by the <xref:System.Xml.XPath.XPathDocument> class are read-only and any attempt to use the editing methods of an <xref:System.Xml.XPath.XPathNavigator> object created by an <xref:System.Xml.XPath.XPathDocument> object results in a <xref:System.NotSupportedException>.</span></span>  
  
 <span data-ttu-id="2d67e-107">Weitere Informationen zum Erstellen bearbeitbarer <xref:System.Xml.XPath.XPathNavigator>-Objekte finden Sie unter [Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).</span><span class="sxs-lookup"><span data-stu-id="2d67e-107">For more information about creating editable <xref:System.Xml.XPath.XPathNavigator> objects, see [Reading XML Data using XPathDocument and XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).</span></span>  
  
## <a name="inserting-nodes"></a><span data-ttu-id="2d67e-108">Einfügen von Knoten</span><span class="sxs-lookup"><span data-stu-id="2d67e-108">Inserting Nodes</span></span>  
 <span data-ttu-id="2d67e-109">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt Methoden zum Einfügen von nebengeordneten und untergeordneten Knoten sowie von Attributknoten in ein XML-Dokument bereit.</span><span class="sxs-lookup"><span data-stu-id="2d67e-109">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to insert sibling, child, and attribute nodes in an XML document.</span></span> <span data-ttu-id="2d67e-110">Mit diesen Methoden können Sie Knoten und Attribute an verschiedenen Stellen entsprechend der aktuellen Position eines <xref:System.Xml.XPath.XPathNavigator>-Objekts einfügen. Diese Methoden werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2d67e-110">These methods allow you to insert nodes and attributes in different locations in relation to the current position of an <xref:System.Xml.XPath.XPathNavigator> object and are described in the following sections.</span></span>  
  
### <a name="inserting-sibling-nodes"></a><span data-ttu-id="2d67e-111">Einfügen von nebengeordneten Knoten</span><span class="sxs-lookup"><span data-stu-id="2d67e-111">Inserting Sibling Nodes</span></span>  
 <span data-ttu-id="2d67e-112">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die folgenden Methoden zum Einfügen von nebengeordneten Knoten bereit.</span><span class="sxs-lookup"><span data-stu-id="2d67e-112">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert sibling nodes.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A>  
  
 <span data-ttu-id="2d67e-113">Diese Methoden fügen vor und nach dem Knoten, auf dem gerade ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, nebengeordnete Knoten ein.</span><span class="sxs-lookup"><span data-stu-id="2d67e-113">These methods insert sibling nodes before and after the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="2d67e-114">Die <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>-Methode sind überladen und verwenden als Parameter einen `string`, ein <xref:System.Xml.XmlReader>-Objekt oder ein <xref:System.Xml.XPath.XPathNavigator>-Objekt, in dem der hinzuzufügende nebengeordnete Knoten enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="2d67e-114">The <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> methods are overloaded and accept a `string`, <xref:System.Xml.XmlReader> object, or <xref:System.Xml.XPath.XPathNavigator> object containing the sibling node to add as parameters.</span></span> <span data-ttu-id="2d67e-115">Beide Methoden geben ein <xref:System.Xml.XmlWriter>-Objekt zurück, das zum Einfügen von nebengeordneten Knoten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d67e-115">Both methods also return an <xref:System.Xml.XmlWriter> object used to insert sibling nodes.</span></span>  
  
 <span data-ttu-id="2d67e-116">Die <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A>-Methode fügen vor und nach dem Knoten, auf dem gerade ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, nebengeordnete Knoten ein. Dabei werden das angegebene Namespacepräfix und der angegebene lokale Name, der Namespace-URI und der Wert als Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d67e-116">The <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> methods insert a single sibling node before and after the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span>  
  
 <span data-ttu-id="2d67e-117">Im folgenden Beispiel wird vor dem untergeordneten `pages`-Element des ersten `price`-Element in der Datei `book` ein neues `contosoBooks.xml`-Element eingefügt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-117">In the following example a new `pages` element is inserted before the `price` child element of the first `book` element in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#19](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#19)]
 [!code-csharp[XPathNavigatorMethods#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#19)]
 [!code-vb[XPathNavigatorMethods#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#19)]  
  
 <span data-ttu-id="2d67e-118">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d67e-118">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="2d67e-119">Weitere Informationen zu den Methoden <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> und <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> finden Sie in der Referenzdokumentation der <xref:System.Xml.XPath.XPathNavigator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2d67e-119">For more information about the <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
### <a name="inserting-child-nodes"></a><span data-ttu-id="2d67e-120">Einfügen von untergeordneten Knoten</span><span class="sxs-lookup"><span data-stu-id="2d67e-120">Inserting Child Nodes</span></span>  
 <span data-ttu-id="2d67e-121">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die folgenden Methoden zum Einfügen von untergeordneten Knoten bereit.</span><span class="sxs-lookup"><span data-stu-id="2d67e-121">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert child nodes.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A>  
  
 <span data-ttu-id="2d67e-122">Diese Methoden fügen untergeordnete Knoten an das Ende und an den Anfang der Liste untergeordneter Knoten des Knotens an, auf dem gegenwärtig ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist.</span><span class="sxs-lookup"><span data-stu-id="2d67e-122">These methods append and prepend child nodes to the end of and the beginning of the list of child nodes of the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="2d67e-123">Genau wie die Methoden im Abschnitt "Einfügen von nebengeordneten Knoten" verwenden die <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>-Methode als Parameter einen `string`, ein <xref:System.Xml.XmlReader>-Objekt oder ein <xref:System.Xml.XPath.XPathNavigator>-Objekt, in dem der hinzuzufügende nebengeordnete Knoten enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="2d67e-123">Like the methods in the "Inserting Sibling Nodes" section, the <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> methods accept a `string`, <xref:System.Xml.XmlReader> object, or <xref:System.Xml.XPath.XPathNavigator> object containing the child node to add as parameters.</span></span> <span data-ttu-id="2d67e-124">Beide Methoden geben ein <xref:System.Xml.XmlWriter>-Objekt zurück, das zum Einfügen von untergeordneten Knoten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d67e-124">Both methods also return an <xref:System.Xml.XmlWriter> object used to insert child nodes.</span></span>  
  
 <span data-ttu-id="2d67e-125">Genau wie die Methoden im Abschnitt "Einfügen von nebengeordneten Knoten" fügen die <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A>-Methode einen untergeordneten Knoten an das Ende und an den Anfang der Liste untergeordneter Knoten des Knotens an, auf dem gegenwärtig ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist. Dabei werden das angegebene Namespacepräfix und der angegebene lokale Name, der Namespace-URI und der Wert als Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d67e-125">Also like the methods in the "Inserting Sibling Nodes" section, the <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> methods insert a single child node to the end of and the beginning of the list of child nodes of the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span>  
  
 <span data-ttu-id="2d67e-126">Im folgenden Beispiel wird der Liste mit untergeordneten Elementen des ersten `pages`-Elements in der Datei `book` ein neues untergeordnetes `contosoBooks.xml`-Element angefügt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-126">In the following example, a new `pages` child element is appended to the list of child elements of the first `book` element in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#2)]
 [!code-csharp[XPathNavigatorMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#2)]
 [!code-vb[XPathNavigatorMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#2)]  
  
 <span data-ttu-id="2d67e-127">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d67e-127">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="2d67e-128">Weitere Informationen zu den Methoden <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> und <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> finden Sie in der Referenzdokumentation der <xref:System.Xml.XPath.XPathNavigator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2d67e-128">For more information about the <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
### <a name="inserting-attribute-nodes"></a><span data-ttu-id="2d67e-129">Einfügen von Attributknoten</span><span class="sxs-lookup"><span data-stu-id="2d67e-129">Inserting Attribute Nodes</span></span>  
 <span data-ttu-id="2d67e-130">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die folgenden Methoden zum Einfügen von Attributknoten bereit.</span><span class="sxs-lookup"><span data-stu-id="2d67e-130">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert attribute nodes.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>  
  
 <span data-ttu-id="2d67e-131">Diese Methoden fügen in dem Elementknoten, auf dem gerade ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, Attributknoten ein.</span><span class="sxs-lookup"><span data-stu-id="2d67e-131">These methods insert attribute nodes on the element node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="2d67e-132">Die <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>-Methode erstellt in dem Elementknoten, auf dem gerade ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, einen Attributknoten. Dabei werden das angegebene Namespacepräfix und der angegebene lokale Name, der Namespace-URI und der Wert als Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d67e-132">The <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> method creates an attribute node on the element node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span> <span data-ttu-id="2d67e-133">Die <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>-Methode gibt ein <xref:System.Xml.XmlWriter>-Objekt zurück, das zum Einfügen von Attributknoten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d67e-133">The <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> method returns an <xref:System.Xml.XmlWriter> object used to insert attribute nodes.</span></span>  
  
 <span data-ttu-id="2d67e-134">Im folgenden Beispiel werden mit dem von der `discount`-Methode zurückgegebenen `currency`-Objekt im untergeordneten `price`-Element des ersten `book`-Elements in der Datei `contosoBooks.xml` ein neues <xref:System.Xml.XmlWriter>-Attribut und ein neues <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>-Attribut erstellt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-134">In the following example, new `discount` and `currency` attributes are created on the `price` child element of the first `book` element in the `contosoBooks.xml` file using the <xref:System.Xml.XmlWriter> object returned from the <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> method.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#8](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#8)]
 [!code-csharp[XPathNavigatorMethods#8](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#8)]
 [!code-vb[XPathNavigatorMethods#8](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#8)]  
  
 <span data-ttu-id="2d67e-135">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d67e-135">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="2d67e-136">Weitere Informationen zur <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>-Methode und zur <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.XPath.XPathNavigator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2d67e-136">For more information about the <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> and <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
## <a name="copying-nodes"></a><span data-ttu-id="2d67e-137">Kopieren von Knoten</span><span class="sxs-lookup"><span data-stu-id="2d67e-137">Copying Nodes</span></span>  
 <span data-ttu-id="2d67e-138">In bestimmten Fällen möchten Sie möglicherweise ein XML-Dokument mit dem Inhalt eines anderen XML-Dokuments füllen.</span><span class="sxs-lookup"><span data-stu-id="2d67e-138">In certain cases you may want to populate an XML document with the contents from another XML document.</span></span> <span data-ttu-id="2d67e-139">Sowohl die <xref:System.Xml.XPath.XPathNavigator>-Klasse als auch die <xref:System.Xml.XmlWriter>-Klasse können Knoten aus einem vorhandenen <xref:System.Xml.XmlDocument>-Objekt oder <xref:System.Xml.XmlReader>-Objekt in ein <xref:System.Xml.XPath.XPathNavigator>-Objekt kopieren.</span><span class="sxs-lookup"><span data-stu-id="2d67e-139">Both the <xref:System.Xml.XPath.XPathNavigator> class and the <xref:System.Xml.XmlWriter> class can copy nodes to an <xref:System.Xml.XmlDocument> object from an existing <xref:System.Xml.XmlReader> object or <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
 <span data-ttu-id="2d67e-140">Die Methoden <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, die <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> und <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> der <xref:System.Xml.XPath.XPathNavigator>-Klasse verfügen alle über Überladungen, die ein <xref:System.Xml.XPath.XPathNavigator>-Objekt oder ein <xref:System.Xml.XmlReader>-Objekt als Parameter annehmen können.</span><span class="sxs-lookup"><span data-stu-id="2d67e-140">The <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class all have overloads that can accept an <xref:System.Xml.XPath.XPathNavigator> object or an <xref:System.Xml.XmlReader> object as a parameter.</span></span>  
  
 <span data-ttu-id="2d67e-141">Die <xref:System.Xml.XmlWriter.WriteNode%2A>-Methode der <xref:System.Xml.XmlWriter>-Klasse verfügt über Überladungen, die ein <xref:System.Xml.XmlNode>-Objekt, ein <xref:System.Xml.XmlReader>-Objekt oder ein <xref:System.Xml.XPath.XPathNavigator>-Objekt annehmen können.</span><span class="sxs-lookup"><span data-stu-id="2d67e-141">The <xref:System.Xml.XmlWriter.WriteNode%2A> method of the <xref:System.Xml.XmlWriter> class has overloads that can accept an <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlReader>, or <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
 <span data-ttu-id="2d67e-142">Im folgenden Beispiel werden alle `book`-Elemente aus einem Dokument in ein anderes kopiert.</span><span class="sxs-lookup"><span data-stu-id="2d67e-142">The following example copies all the `book` elements from one document to another.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", String.Empty)  
  
Dim newBooks As XPathDocument = New XPathDocument("newBooks.xml")  
Dim newBooksNavigator As XPathNavigator = newBooks.CreateNavigator()  
  
Dim nav As XPathNavigator  
For Each nav in newBooksNavigator.SelectDescendants("book", "", false)  
    navigator.AppendChild(nav)  
Next  
  
document.Save("newBooks.xml");  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", String.Empty);  
  
XPathDocument newBooks = new XPathDocument("newBooks.xml");  
XPathNavigator newBooksNavigator = newBooks.CreateNavigator();  
  
foreach (XPathNavigator nav in newBooksNavigator.SelectDescendants("book", "", false))  
{  
    navigator.AppendChild(nav);  
}  
  
document.Save("newBooks.xml");  
```  
  
## <a name="inserting-values"></a><span data-ttu-id="2d67e-143">Einfügen von Werten</span><span class="sxs-lookup"><span data-stu-id="2d67e-143">Inserting Values</span></span>  
 <span data-ttu-id="2d67e-144">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode und die <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode zum Einfügen von Werten für einen Knoten in ein <xref:System.Xml.XmlDocument>-Objekt bereit.</span><span class="sxs-lookup"><span data-stu-id="2d67e-144">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods to insert values for a node into an <xref:System.Xml.XmlDocument> object.</span></span>  
  
### <a name="inserting-untyped-values"></a><span data-ttu-id="2d67e-145">Einfügen von nicht typisierten Werten</span><span class="sxs-lookup"><span data-stu-id="2d67e-145">Inserting Untyped Values</span></span>  
 <span data-ttu-id="2d67e-146">Die <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Methode fügt einfach den als Parameter übergebenen nicht typisierten `string`-Wert als Wert des Knotens ein, auf dem das <xref:System.Xml.XPath.XPathNavigator>-Objekt gerade positioniert ist.</span><span class="sxs-lookup"><span data-stu-id="2d67e-146">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method simply inserts the untyped `string` value passed as a parameter as the value of the node the <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="2d67e-147">Der Wert wird ohne Typ bzw. (falls Schemainformationen verfügbar sind) ohne Prüfung der Gültigkeit des neuen Werts bezüglich des Knotentyps eingefügt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-147">The value is inserted without any type or without verifying that the new value is valid according to the type of the node if schema information is available.</span></span>  
  
 <span data-ttu-id="2d67e-148">Im folgenden Beispiel werden alle <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>-Elemente in der Datei `price` mit der `contosoBooks.xml`-Methode aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="2d67e-148">In the following example, the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method is used to update all `price` elements in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 <span data-ttu-id="2d67e-149">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d67e-149">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="inserting-typed-values"></a><span data-ttu-id="2d67e-150">Einfügen von typisierten Werten</span><span class="sxs-lookup"><span data-stu-id="2d67e-150">Inserting Typed Values</span></span>  
 <span data-ttu-id="2d67e-151">Wenn der Typ ein einfacher W3C-XML-Schematyp ist, wird der neue mit der <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>-Methode eingefügte Wert anhand aller Facets des einfachen Typs überprüft, bevor er festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="2d67e-151">When the type of a node is a W3C XML Schema simple type, the new value inserted by the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method is checked against the facets of the simple type before the value is set.</span></span> <span data-ttu-id="2d67e-152">Wenn der neue Wert bezüglich des Knotentyps nicht gültig ist (z. B. der Wert `-1` für ein Element vom Typ `xs:positiveInteger`), wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="2d67e-152">If the new value is not valid according to the type of the node (for example, setting a value of `-1` on an element whose type is `xs:positiveInteger`), it results in an exception.</span></span>  
  
 <span data-ttu-id="2d67e-153">Im folgenden Beispiel wird versucht, den Wert des `price`-Elements des ersten `book`-Elements der Datei `contosoBooks.xml` in einen <xref:System.DateTime>-Wert zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2d67e-153">The following example attempts to change the value of the `price` element of the first `book` element in the `contosoBooks.xml` file to a <xref:System.DateTime> value.</span></span> <span data-ttu-id="2d67e-154">Da der XML-Schematyp des `price`-Elements in den `xs:decimal`-Dateien als `contosoBooks.xsd` definiert ist, führt dies zu einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="2d67e-154">Because the XML Schema type of the `price` element is defined as `xs:decimal` in the `contosoBooks.xsd` files, this results in an exception.</span></span>  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetTypedValue(DateTime.Now)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetTypedValue(DateTime.Now);  
```  
  
 <span data-ttu-id="2d67e-155">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d67e-155">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="2d67e-156">In diesem Beispiel wird auch `contosoBooks.xsd` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="2d67e-156">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
## <a name="the-innerxml-and-outerxml-properties"></a><span data-ttu-id="2d67e-157">Die Eigenschaften "InnerXml" und "OuterXml"</span><span class="sxs-lookup"><span data-stu-id="2d67e-157">The InnerXml and OuterXml Properties</span></span>  
 <span data-ttu-id="2d67e-158">Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse ändern das XML-Markup der Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist.</span><span class="sxs-lookup"><span data-stu-id="2d67e-158">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class change the XML markup of the nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="2d67e-159">Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft ändert das XML-Markup der untergeordneten Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, mit den analysierten Inhalten des angegebenen XML-`string`.</span><span class="sxs-lookup"><span data-stu-id="2d67e-159">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on with the parsed contents of the given XML `string`.</span></span> <span data-ttu-id="2d67e-160">Ebenso ändert die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft das XML-Markup der untergeordneten Knoten, auf denen derzeit ein <xref:System.Xml.XPath.XPathNavigator>-Objekt positioniert ist, sowie den aktuellen Knoten selbst.</span><span class="sxs-lookup"><span data-stu-id="2d67e-160">Similarly, the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on as well as the current node itself.</span></span>  
  
 <span data-ttu-id="2d67e-161">Neben den in diesem Thema beschriebenen Methoden können die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft zum Einfügen von Knoten und Werten in ein XML-Dokument verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d67e-161">In addition to the methods described in this topic, the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties can be used to insert nodes and values in an XML document.</span></span> <span data-ttu-id="2d67e-162">Weitere Informationen zum Verwenden der Eigenschaften <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> und <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> zum Einfügen von Knoten und Werten finden Sie im Thema [Ändern von XML-Daten mit XPathNavigator](modify-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="2d67e-162">For more information about using the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties to insert nodes and values, see the [Modify XML Data using XPathNavigator](modify-xml-data-using-xpathnavigator.md) topic.</span></span>  
  
## <a name="namespace-and-xmllang-conflicts"></a><span data-ttu-id="2d67e-163">Konflikte bei Namespaces und "xml:lang"</span><span class="sxs-lookup"><span data-stu-id="2d67e-163">Namespace and xml:lang Conflicts</span></span>  
 <span data-ttu-id="2d67e-164">Beim Einfügen von XML-Daten mit der Methoden `xml:lang`, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> und <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> der <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>-Klasse, die <xref:System.Xml.XPath.XPathNavigator>-Objekte als Parameter verwenden, können bestimmte Konflikte bezüglich des Gültigkeitsbereichs von Namespaces und <xref:System.Xml.XmlReader>-Deklarationen auftreten.</span><span class="sxs-lookup"><span data-stu-id="2d67e-164">Certain conflicts related to the scope of namespace and `xml:lang` declarations can occur when inserting XML data using the <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class that take <xref:System.Xml.XmlReader> objects as parameters.</span></span>  
  
 <span data-ttu-id="2d67e-165">Nachfolgend werden alle möglicherweise auftretenden Konflikte bei Namespaces dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-165">The following are the possible namespace conflicts.</span></span>  
  
- <span data-ttu-id="2d67e-166">Wenn sich ein Namespace innerhalb des Kontextbereichs des <xref:System.Xml.XmlReader>-Objekts befindet, bei dem sich das Präfix zur Zuordnung des Namespace-URI nicht im Kontext des <xref:System.Xml.XPath.XPathNavigator>-Objekts befindet, wird dem neu eingefügten Knoten eine neue Namespacedeklaration hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-166">If there is a namespace in-scope within the <xref:System.Xml.XmlReader> object's context, where the prefix to namespace URI mapping is not in the <xref:System.Xml.XPath.XPathNavigator> object's context, a new namespace declaration is added to the newly inserted node.</span></span>  
  
- <span data-ttu-id="2d67e-167">Wenn sich der gleiche Namespace-URI innerhalb des Kontextbereichs des <xref:System.Xml.XmlReader>-Objekts und des <xref:System.Xml.XPath.XPathNavigator>-Objekts befindet, aber wenn ihm in beiden Kontexten ein anderes Präfix zugeordnet wurde, wird dem neu eingefügten Knoten eine neue Namespacedeklaration hinzugefügt, wobei das Präfix und der Namespace-URI des <xref:System.Xml.XmlReader>-Objekts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d67e-167">If the same namespace URI is in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but has a different prefix mapped to it in both contexts, a new namespace declaration is added to the newly inserted node, with the prefix and namespace URI taken from the <xref:System.Xml.XmlReader> object.</span></span>  
  
- <span data-ttu-id="2d67e-168">Wenn sich das gleiche Namespacepräfix innerhalb des Kontextbereichs des <xref:System.Xml.XmlReader>-Objekts und des <xref:System.Xml.XPath.XPathNavigator>-Objekts befindet, aber wenn ihm in beiden Kontexten ein anderer Namespace-URI zugeordnet wurde, wird dem neu eingefügten Knoten eine neue Namespacedeklaration hinzugefügt,. Dabei wird das Präfix mit dem Namespace-URI des <xref:System.Xml.XmlReader>-Objekts erneut deklariert.</span><span class="sxs-lookup"><span data-stu-id="2d67e-168">If the same namespace prefix is in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but has a different namespace URI mapped to it in both contexts, a new namespace declaration is added to the newly inserted node which re-declares that prefix with the namespace URI taken from <xref:System.Xml.XmlReader> object.</span></span>  
  
- <span data-ttu-id="2d67e-169">Wenn das Präfix sowie der Namespace-URI im Kontext des <xref:System.Xml.XmlReader>-Objekts und im Kontext des <xref:System.Xml.XPath.XPathNavigator>-Objekts gleich sind, wird dem neu eingefügten Knoten keine neue Namespacedeklaration hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-169">If the prefix as well as the namespace URI in both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context is the same, no new namespace declaration is added to the newly inserted node.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d67e-170">Die oben genannte Beschreibung gilt auch für Namespacedeklarationen mit einem leeren `string` als Präfix (z. B. die Standardnamespacedeklaration).</span><span class="sxs-lookup"><span data-stu-id="2d67e-170">The description above also applies to namespace declarations with the empty `string` as a prefix (for example, the default namespace declaration).</span></span>  
  
 <span data-ttu-id="2d67e-171">Nachfolgend werden alle möglicherweise auftretenden Konflikte bei `xml:lang` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-171">The following are the possible `xml:lang` conflicts.</span></span>  
  
- <span data-ttu-id="2d67e-172">Wenn sich ein `xml:lang`-Attribut im Kontextbereich des <xref:System.Xml.XmlReader>-Objekts, aber nicht im Kontext des <xref:System.Xml.XPath.XPathNavigator>-Objekts befindet, wird dem neu eingefügten Knoten ein `xml:lang`-Attribut hinzugefügt, dessen Wert aus dem <xref:System.Xml.XmlReader>-Objekt entnommen wird.</span><span class="sxs-lookup"><span data-stu-id="2d67e-172">If there is an `xml:lang` attribute in-scope within the <xref:System.Xml.XmlReader> object's context but not in the <xref:System.Xml.XPath.XPathNavigator> object's context, an `xml:lang` attribute whose value is taken from the <xref:System.Xml.XmlReader> object is added to the newly inserted node.</span></span>  
  
- <span data-ttu-id="2d67e-173">Wenn sich ein `xml:lang`-Attribut im Kontextbereich des <xref:System.Xml.XmlReader>-Objekts und des <xref:System.Xml.XPath.XPathNavigator>-Objekts befindet, aber jedes Attribut einen anderen Wert besitzt, wird dem neu eingefügten Knoten ein `xml:lang`-Attribut hinzugefügt, dessen Wert aus dem <xref:System.Xml.XmlReader>-Objekt entnommen wird.</span><span class="sxs-lookup"><span data-stu-id="2d67e-173">If there is an `xml:lang` attribute in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but each has a different value, an `xml:lang` attribute whose value is taken from the <xref:System.Xml.XmlReader> object is added to the newly inserted node.</span></span>  
  
- <span data-ttu-id="2d67e-174">Wenn sich ein `xml:lang`-Attribut im Kontextbereich des <xref:System.Xml.XmlReader>-Objekts und des <xref:System.Xml.XPath.XPathNavigator>-Objekts befindet, aber beide Attribute den gleichen Wert besitzen, wird dem neu eingefügten Knoten kein neues `xml:lang`-Attribut hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-174">If there is an `xml:lang` attribute in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but each with the same value, no new `xml:lang` attribute is added on the newly inserted node.</span></span>  
  
- <span data-ttu-id="2d67e-175">Wenn sich ein `xml:lang`-Attribut im Kontextbereich des <xref:System.Xml.XPath.XPathNavigator>-Objekts, aber nicht im Kontextbereich des <xref:System.Xml.XmlReader>-Objekts befindet, wird dem neu eingefügten Knoten kein `xml:lang`-Attribut hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-175">If there is an `xml:lang` attribute in-scope within the <xref:System.Xml.XPath.XPathNavigator> object's context, but none existing in the <xref:System.Xml.XmlReader> object's context, no `xml:lang` attribute is added to the newly inserted node.</span></span>  
  
## <a name="inserting-nodes-with-xmlwriter"></a><span data-ttu-id="2d67e-176">Einfügen von Knoten mit "XmlWriter"</span><span class="sxs-lookup"><span data-stu-id="2d67e-176">Inserting Nodes with XmlWriter</span></span>  
 <span data-ttu-id="2d67e-177">Die im Abschnitt zum Einfügen von Knoten und Werten beschriebenen Methoden zum Einfügen von nebengeordneten und untergeordneten Knoten sowie von Attributknoten sind überladen.</span><span class="sxs-lookup"><span data-stu-id="2d67e-177">The methods used to insert sibling, child and attribute nodes described in the "Inserting Nodes and Values" section are overloaded.</span></span> <span data-ttu-id="2d67e-178">Die Methoden <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> und <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> der <xref:System.Xml.XPath.XPathNavigator>-Klasse geben ein <xref:System.Xml.XmlWriter>-Objekt zurück, das zum Einfügen von Knoten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d67e-178">The <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> and <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class return an <xref:System.Xml.XmlWriter> object used to insert nodes.</span></span>  
  
### <a name="unsupported-xmlwriter-methods"></a><span data-ttu-id="2d67e-179">Nicht unterstützte XmlWriter-Methoden</span><span class="sxs-lookup"><span data-stu-id="2d67e-179">Unsupported XmlWriter Methods</span></span>  
 <span data-ttu-id="2d67e-180">Nicht alle Methoden, mit denen unter Verwendung der <xref:System.Xml.XmlWriter>-Klasse Informationen in ein XML-Dokument geschrieben werden, werden aufgrund des Unterschieds zwischen dem XPath-Datenmodell und dem DOM (Dokumentobjektmodell) von der <xref:System.Xml.XPath.XPathNavigator>-Klasse unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-180">Not all of the methods used for writing information to an XML document using the <xref:System.Xml.XmlWriter> class are supported by the <xref:System.Xml.XPath.XPathNavigator> class due to difference between the XPath data model and the Document Object Model (DOM).</span></span>  
  
 <span data-ttu-id="2d67e-181">In der folgenden Tabelle werden die Methoden der <xref:System.Xml.XmlWriter>-Klasse beschrieben, die nicht von der <xref:System.Xml.XPath.XPathNavigator>-Klasse unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2d67e-181">The following table describes the <xref:System.Xml.XmlWriter> class methods not supported by the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
|<span data-ttu-id="2d67e-182">Methode</span><span class="sxs-lookup"><span data-stu-id="2d67e-182">Method</span></span>|<span data-ttu-id="2d67e-183">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d67e-183">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.XmlWriter.WriteEntityRef%2A>|<span data-ttu-id="2d67e-184">Löst eine <xref:System.NotSupportedException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="2d67e-184">Throws a <xref:System.NotSupportedException> exception.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteDocType%2A>|<span data-ttu-id="2d67e-185">Wird auf der Stammebene ignoriert und löst beim Aufrufen auf einer anderen Ebene im XML-Dokument eine <xref:System.NotSupportedException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="2d67e-185">Ignored at the root level and throws a <xref:System.NotSupportedException> exception if called at any other level in the XML document.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteCData%2A>|<span data-ttu-id="2d67e-186">Wird wie ein Aufruf der <xref:System.Xml.XmlWriter.WriteString%2A>-Methode für die entsprechenden Zeichen behandelt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-186">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteCharEntity%2A>|<span data-ttu-id="2d67e-187">Wird wie ein Aufruf der <xref:System.Xml.XmlWriter.WriteString%2A>-Methode für die entsprechenden Zeichen behandelt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-187">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteSurrogateCharEntity%2A>|<span data-ttu-id="2d67e-188">Wird wie ein Aufruf der <xref:System.Xml.XmlWriter.WriteString%2A>-Methode für die entsprechenden Zeichen behandelt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-188">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
  
 <span data-ttu-id="2d67e-189">Weitere Informationen zur <xref:System.Xml.XmlWriter>-Klasse finden Sie in der Referenzdokumentation der <xref:System.Xml.XmlWriter>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2d67e-189">For more information about the <xref:System.Xml.XmlWriter> class, see the <xref:System.Xml.XmlWriter> class reference documentation.</span></span>  
  
### <a name="multiple-xmlwriter-objects"></a><span data-ttu-id="2d67e-190">Mehrere XmlWriter-Objekte</span><span class="sxs-lookup"><span data-stu-id="2d67e-190">Multiple XmlWriter Objects</span></span>  
 <span data-ttu-id="2d67e-191">Es ist möglich, über mehrere <xref:System.Xml.XPath.XPathNavigator>-Objekte zu verfügen, die auf verschiedene Teile eines XML-Dokuments mit einem oder mehreren offenen <xref:System.Xml.XmlWriter>-Objekten zeigen.</span><span class="sxs-lookup"><span data-stu-id="2d67e-191">It is possible to have multiple <xref:System.Xml.XPath.XPathNavigator> objects pointing to different parts of an XML document with one or more open <xref:System.Xml.XmlWriter> objects.</span></span> <span data-ttu-id="2d67e-192">In Szenarios mit einfachen Threads sind mehrere <xref:System.Xml.XmlWriter>-Objekte zulässig und werden dort unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d67e-192">Multiple <xref:System.Xml.XmlWriter> objects are allowed and supported in single-threaded scenarios.</span></span>  
  
 <span data-ttu-id="2d67e-193">Die folgenden beiden Anmerkungen sollten bei der Verwendung mehrerer <xref:System.Xml.XmlWriter>-Objekte unbedingt beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="2d67e-193">The following are important notes to consider when using multiple <xref:System.Xml.XmlWriter> objects.</span></span>  
  
- <span data-ttu-id="2d67e-194">Dem XML-Dokument werden von <xref:System.Xml.XmlWriter>-Objekten geschriebene XML-Fragmente hinzugefügt, wenn die <xref:System.Xml.XmlWriter.Close%2A>-Methode eines jeden <xref:System.Xml.XmlWriter>-Objekts aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2d67e-194">XML fragments written by <xref:System.Xml.XmlWriter> objects are added to the XML document when the <xref:System.Xml.XmlWriter.Close%2A> method of each <xref:System.Xml.XmlWriter> object is called.</span></span> <span data-ttu-id="2d67e-195">Bis zu diesem Zeitpunkt schreibt das <xref:System.Xml.XmlWriter>-Objekt ein nicht verbundenes Fragment.</span><span class="sxs-lookup"><span data-stu-id="2d67e-195">Until that point, the <xref:System.Xml.XmlWriter> object is writing a disconnected fragment.</span></span> <span data-ttu-id="2d67e-196">Das Ausführen eines Vorgangs für das XML-Dokument wirkt sich nicht auf Fragmente aus, die vor dem Aufrufen von <xref:System.Xml.XmlWriter> von einem <xref:System.Xml.XmlWriter.Close%2A>-Objekt geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="2d67e-196">If an operation is performed on the XML document, any fragments being written by an <xref:System.Xml.XmlWriter> object, before the <xref:System.Xml.XmlWriter.Close%2A> has been called, are not affected.</span></span>  
  
- <span data-ttu-id="2d67e-197">Wenn sich auf einer bestimmten XML-Unterstruktur ein offenes <xref:System.Xml.XmlWriter>-Objekt befindet und diese Unterstruktur gelöscht wird, könnte das <xref:System.Xml.XmlWriter>-Objekt der Unterstruktur noch hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2d67e-197">If there is an open <xref:System.Xml.XmlWriter> object on a particular XML subtree and that subtree is deleted, the <xref:System.Xml.XmlWriter> object may still add to the sub-tree.</span></span> <span data-ttu-id="2d67e-198">Aus der Teilstruktur wird einfach ein gelöschtes Fragment.</span><span class="sxs-lookup"><span data-stu-id="2d67e-198">The subtree simply becomes a deleted fragment.</span></span>  
  
- <span data-ttu-id="2d67e-199">Wenn an der gleichen Stelle im XML-Dokument mehrere <xref:System.Xml.XmlWriter>-Objekte geöffnet sind, werden sie dem XML-Dokument in der Reihenfolge hinzugefügt, in der die <xref:System.Xml.XmlWriter>-Objekte geschlossen werden, und nicht in der Reihenfolge, in der sie geöffnet wurden.</span><span class="sxs-lookup"><span data-stu-id="2d67e-199">If multiple <xref:System.Xml.XmlWriter> objects are opened at the same point in the XML document, they are added to the XML document in the order in which the <xref:System.Xml.XmlWriter> objects are closed, not in the order in which they were opened.</span></span>  
  
 <span data-ttu-id="2d67e-200">Im folgenden Beispiel werden ein <xref:System.Xml.XmlDocument>-Objekt sowie ein <xref:System.Xml.XPath.XPathNavigator>-Objekt erstellt und anschließend ein von der <xref:System.Xml.XmlWriter>-Methode zurückgegebenes <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>-Objekt verwendet, um die Struktur des ersten Buchs in der Datei `books.xml` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d67e-200">The following example creates an <xref:System.Xml.XmlDocument> object, creates an <xref:System.Xml.XPath.XPathNavigator> object, and then uses the <xref:System.Xml.XmlWriter> object returned by the <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> method to create the structure of the first book in the `books.xml` file.</span></span> <span data-ttu-id="2d67e-201">Anschließend wird sie im Beispiel als die Datei `book.xml` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d67e-201">The example then saves it as the `book.xml` file.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
Using writer As XmlWriter = navigator.PrependChild()  
  
    writer.WriteStartElement("bookstore")  
    writer.WriteStartElement("book")  
    writer.WriteAttributeString("genre", "autobiography")  
    writer.WriteAttributeString("publicationdate", "1981-03-22")  
    writer.WriteAttributeString("ISBN", "1-861003-11-0")  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin")  
    writer.WriteStartElement("author")  
    writer.WriteElementString("first-name", "Benjamin")  
    writer.WriteElementString("last-name", "Franklin")  
    writer.WriteElementString("price", "8.99")  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
  
End Using  
  
document.Save("book.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
XPathNavigator navigator = document.CreateNavigator();  
  
using (XmlWriter writer = navigator.PrependChild())  
{  
    writer.WriteStartElement("bookstore");  
    writer.WriteStartElement("book");  
    writer.WriteAttributeString("genre", "autobiography");  
    writer.WriteAttributeString("publicationdate", "1981-03-22");  
    writer.WriteAttributeString("ISBN", "1-861003-11-0");  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin");  
    writer.WriteStartElement("author");  
    writer.WriteElementString("first-name", "Benjamin");  
    writer.WriteElementString("last-name", "Franklin");  
    writer.WriteElementString("price", "8.99");  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
}  
document.Save("book.xml");  
```  
  
## <a name="saving-an-xml-document"></a><span data-ttu-id="2d67e-202">Speichern eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="2d67e-202">Saving an XML Document</span></span>  
 <span data-ttu-id="2d67e-203">Änderungen eines <xref:System.Xml.XmlDocument>-Objekts, die von den in diesem Thema beschriebenen Methoden vorgenommen wurden, werden mit den Methoden der <xref:System.Xml.XmlDocument>-Klasse gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d67e-203">Saving changes made to an <xref:System.Xml.XmlDocument> object as the result of the methods described in this topic is performed using the methods of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="2d67e-204">Weitere Informationen zum Speichern der an einem <xref:System.Xml.XmlDocument>-Objekt vorgenommenen Änderungen finden Sie unter [Speichern und Ausgeben eines Dokuments](saving-and-writing-a-document.md).</span><span class="sxs-lookup"><span data-stu-id="2d67e-204">For more information about saving changes made to an <xref:System.Xml.XmlDocument> object, see [Saving and Writing a Document](saving-and-writing-a-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d67e-205">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d67e-205">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="2d67e-206">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="2d67e-206">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="2d67e-207">Ändern von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="2d67e-207">Modify XML Data using XPathNavigator</span></span>](modify-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="2d67e-208">Entfernen von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="2d67e-208">Remove XML Data using XPathNavigator</span></span>](remove-xml-data-using-xpathnavigator.md)
