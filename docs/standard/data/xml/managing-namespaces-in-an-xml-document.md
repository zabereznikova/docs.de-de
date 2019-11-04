---
title: Verwalten von Namespaces in einem XML-Dokument
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 682643fc-b848-4e42-8c0d-50deeaeb5f2a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3befdd0ec96856a62e5c3c603935303498758710
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423929"
---
# <a name="managing-namespaces-in-an-xml-document"></a><span data-ttu-id="969e9-102">Verwalten von Namespaces in einem XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="969e9-102">Managing Namespaces in an XML Document</span></span>
<span data-ttu-id="969e9-103">XML-Namespaces ordnen benutzerdefinierten und vordefinierten URIs in einem XML-Dokument Element- und Attributnamen zu.</span><span class="sxs-lookup"><span data-stu-id="969e9-103">XML namespaces associate element and attribute names in an XML document with custom and predefined URIs.</span></span> <span data-ttu-id="969e9-104">Um diese Zuordnungen zu erstellen, definieren Sie Präfixe für Namespace-URIs und verwenden diese zur Kennzeichnung von Element- und Attributnamen in XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="969e9-104">To create these associations, you define prefixes for namespace URIs, and use those prefixes to qualify element and attribute names in XML data.</span></span> <span data-ttu-id="969e9-105">Namespaces verhindern Konflikte zwischen Element- und Attributnamen. Sie ermöglichen eine unterschiedliche Verarbeitung und Validierung von gleichnamigen Elementen und Attributen.</span><span class="sxs-lookup"><span data-stu-id="969e9-105">Namespaces prevent element and attribute name collisions, and enable elements and attributes of the same name to be handled and validated differently.</span></span>  
  
<a name="declare"></a>   
## <a name="declaring-namespaces"></a><span data-ttu-id="969e9-106">Deklarieren von Namespaces</span><span class="sxs-lookup"><span data-stu-id="969e9-106">Declaring namespaces</span></span>  
 <span data-ttu-id="969e9-107">Um einen Namespace für ein Element zu deklarieren, verwenden Sie das `xmlns:`-Attribut:</span><span class="sxs-lookup"><span data-stu-id="969e9-107">To declare a namespace on an element, you use the `xmlns:` attribute:</span></span>  
  
 `xmlns:<name>=<"uri">`  
  
 <span data-ttu-id="969e9-108">`<name>` entspricht dabei dem Namespacepräfix und `<"uri">` dem URI, durch den der Namespace identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="969e9-108">where `<name>` is the namespace prefix and `<"uri">` is the URI that identifies the namespace.</span></span> <span data-ttu-id="969e9-109">Nachdem das Präfix deklariert wurde, können Sie mit ihm Elemente und Attribute in einem XML-Dokument kennzeichnen und diese dem Namespace-URI zuordnen.</span><span class="sxs-lookup"><span data-stu-id="969e9-109">After you declare the prefix, you can use it to qualify elements and attributes in an XML document and associate them with the namespace URI.</span></span> <span data-ttu-id="969e9-110">Da das Namespacepräfix im gesamten Dokument verwendet wird, sollte es möglichst kurz sein.</span><span class="sxs-lookup"><span data-stu-id="969e9-110">Because the namespace prefix is used throughout a document, it should be short in length.</span></span>  
  
 <span data-ttu-id="969e9-111">Im Beispiel werden zwei `BOOK`-Elemente definiert.</span><span class="sxs-lookup"><span data-stu-id="969e9-111">This example defines two `BOOK` elements.</span></span> <span data-ttu-id="969e9-112">Das erste Element wird durch das Präfix `mybook`, das zweite durch das Präfix `bb` gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="969e9-112">The first element is qualified by the prefix, `mybook`, and the second element is qualified by the prefix, `bb`.</span></span> <span data-ttu-id="969e9-113">Jedes Präfix wird einem anderen Namespace-URI zugeordnet:</span><span class="sxs-lookup"><span data-stu-id="969e9-113">Each prefix is associated with a different namespace URI:</span></span>  
  
```xml  
<mybook:BOOK xmlns:mybook="http://www.contoso.com/books.dtd">  
<bb:BOOK xmlns:bb="urn:blueyonderairlines">  
```  
  
 <span data-ttu-id="969e9-114">Sie können angeben, dass ein Element Teil eines bestimmten Namespaces ist, indem Sie das Namespacepräfix hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="969e9-114">To signify that an element is a part of a particular namespace, add the namespace prefix to it.</span></span> <span data-ttu-id="969e9-115">Wenn das `Author`-Element beispielsweise ein Teil des `mybook`-Namespaces ist, wird es als `<mybook:Author>` deklariert.</span><span class="sxs-lookup"><span data-stu-id="969e9-115">For example, if a `Author` element belongs to the `mybook` namespace, it is declared as `<mybook:Author>`.</span></span>  
  
<a name="scope"></a>   
## <a name="declaration-scope"></a><span data-ttu-id="969e9-116">Gültigkeitsbereich der Deklaration</span><span class="sxs-lookup"><span data-stu-id="969e9-116">Declaration scope</span></span>  
 <span data-ttu-id="969e9-117">Ein Namespace gilt ab dem Punkt der Deklaration bis zum Ende desjenigen Elements, in dem er deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="969e9-117">A namespace is effective from its point of declaration until the end of the element it was declared in.</span></span> <span data-ttu-id="969e9-118">In diesem Beispiel wird der im `BOOK`-Element definierte Namespace nicht auf Elemente außerhalb des `BOOK`-Elements, z. B. das `Publisher`-Element, angewendet:</span><span class="sxs-lookup"><span data-stu-id="969e9-118">In this example, the namespace defined in the `BOOK` element doesn't apply to elements outside the `BOOK` element, such as the `Publisher` element:</span></span>  
  
```xml  
<Author>Joe Smith</Author>  
<BOOK xmlns:book="http://www.contoso.com">  
    <title>My Wonderful Day</title>  
      <price>$3.95</price>  
</BOOK>  
<Publisher>  
    <Name>MSPress</Name>  
</Publisher>  
```  
  
 <span data-ttu-id="969e9-119">Ein Namespace muss deklariert werden, bevor er verwendet werden kann, aber er muss sich nicht unbedingt am Anfang des XML-Dokuments befinden.</span><span class="sxs-lookup"><span data-stu-id="969e9-119">A namespace must be declared before it can be used, but it doesn't have to appear at the top of the XML document.</span></span>  
  
 <span data-ttu-id="969e9-120">Wenn Sie mehrere Namespaces in einem XML-Dokument verwenden, können Sie einen Namespace als Standardnamespace definieren, um ein übersichtlicheres Dokument zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="969e9-120">When you use multiple namespaces in an XML document, you can define one namespace as the default namespace to create a cleaner looking document.</span></span> <span data-ttu-id="969e9-121">Der Standardnamespace wird im Stammelement deklariert und auf alle nicht gekennzeichneten Elemente im Dokument angewendet.</span><span class="sxs-lookup"><span data-stu-id="969e9-121">The default namespace is declared in the root element and applies to all unqualified elements in the document.</span></span> <span data-ttu-id="969e9-122">Standardnamespaces gelten nur für Elemente und nicht für Attribute.</span><span class="sxs-lookup"><span data-stu-id="969e9-122">Default namespaces apply to elements only, not to attributes.</span></span>  
  
 <span data-ttu-id="969e9-123">Um den Standardnamespace zu verwenden, lassen Sie das Präfix und den Doppelpunkt in der Elementdeklaration aus:</span><span class="sxs-lookup"><span data-stu-id="969e9-123">To use the default namespace, omit the prefix and the colon from the declaration on the element:</span></span>  
  
```xml  
<BOOK xmlns="http://www.contoso.com/books.dtd">  
```  
  
## <a name="managing-namespaces"></a><span data-ttu-id="969e9-124">Verwalten von Namespaces</span><span class="sxs-lookup"><span data-stu-id="969e9-124">Managing namespaces</span></span>  
 <span data-ttu-id="969e9-125">In der <xref:System.Xml.XmlNamespaceManager>-Klasse wird eine Sammlung von Namespace-URIs und ihrer Präfixe gespeichert. Sie können Namespaces in der Sammlung suchen, hinzufügen und entfernen.</span><span class="sxs-lookup"><span data-stu-id="969e9-125">The <xref:System.Xml.XmlNamespaceManager> class stores a collection of namespace URIs and their prefixes, and lets you look up, add, and remove namespaces from this collection.</span></span> <span data-ttu-id="969e9-126">In bestimmten Kontexten ist die Klasse erforderlich, um die XML-Verarbeitungsleistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="969e9-126">In certain contexts, this class is required for better XML processing performance.</span></span> <span data-ttu-id="969e9-127">So wird <xref:System.Xml.Xsl.XsltContext> von der <xref:System.Xml.XmlNamespaceManager>-Klasse verwendet, um XPath-Unterstützung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="969e9-127">For example, the <xref:System.Xml.Xsl.XsltContext> class uses <xref:System.Xml.XmlNamespaceManager> for XPath support.</span></span>  
  
 <span data-ttu-id="969e9-128">Der Namespace-Manager führt keine Validierung der Namespaces durch, sondern setzt voraus, dass Präfixe und Namespaces bereits überprüft wurden und der [W3C](https://www.w3.org/TR/REC-xml-names/)-Spezifikation für Namespaces entsprechen.</span><span class="sxs-lookup"><span data-stu-id="969e9-128">The namespace manager doesn't perform any validation on the namespaces, but assumes that prefixes and namespaces have already been verified and conform to the [W3C Namespaces](https://www.w3.org/TR/REC-xml-names/) specification.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="969e9-129">LINQ to XML in [C#](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) und [Visual Basic](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) verwenden nicht <xref:System.Xml.XmlNamespaceManager> zum Verwalten von Namespaces.</span><span class="sxs-lookup"><span data-stu-id="969e9-129">LINQ TO XML in [C#](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) and [Visual Basic](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) don't use <xref:System.Xml.XmlNamespaceManager> to manage namespaces.</span></span> <span data-ttu-id="969e9-130">Informationen zur Verwaltung von Namespaces bei der Verwendung von LINQ to XML finden Sie in der LINQ-Dokumentation unter [Arbeiten mit XML-Namespaces (C#)](../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md) und [Arbeiten mit XML-Namespaces (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="969e9-130">See [Working with XML Namespaces (C#)](../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md) and [Working with XML Namespaces (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md) in the LINQ documentation for information about managing namespaces when using LINQ to XML.</span></span>  
  
 <span data-ttu-id="969e9-131">Im Folgenden finden Sie einige der Verwaltungs- und Suchaufgaben, die Sie mit der <xref:System.Xml.XmlNamespaceManager>-Klasse ausführen können.</span><span class="sxs-lookup"><span data-stu-id="969e9-131">Here are some of the management and lookup tasks you can perform with the <xref:System.Xml.XmlNamespaceManager> class.</span></span> <span data-ttu-id="969e9-132">Weitere Informationen und Beispiele finden Sie, indem Sie den Links zur Referenzseite der einzelnen Methoden oder Eigenschaften folgen.</span><span class="sxs-lookup"><span data-stu-id="969e9-132">For more information and examples, follow the links to the reference page for each method or property.</span></span>  
  
|<span data-ttu-id="969e9-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="969e9-133">To</span></span>|<span data-ttu-id="969e9-134">Mit</span><span class="sxs-lookup"><span data-stu-id="969e9-134">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="969e9-135">Hinzufügen eines Namespaces</span><span class="sxs-lookup"><span data-stu-id="969e9-135">Add a namespace</span></span>|<span data-ttu-id="969e9-136"><xref:System.Xml.XmlNamespaceManager.AddNamespace%2A>-Methode</span><span class="sxs-lookup"><span data-stu-id="969e9-136"><xref:System.Xml.XmlNamespaceManager.AddNamespace%2A> method</span></span>|  
|<span data-ttu-id="969e9-137">Entfernen eines Namespaces</span><span class="sxs-lookup"><span data-stu-id="969e9-137">Remove a namespace</span></span>|<span data-ttu-id="969e9-138"><xref:System.Xml.XmlNamespaceManager.RemoveNamespace%2A>-Methode</span><span class="sxs-lookup"><span data-stu-id="969e9-138"><xref:System.Xml.XmlNamespaceManager.RemoveNamespace%2A> method</span></span>|  
|<span data-ttu-id="969e9-139">Suchen des URIs für den Standardnamespace</span><span class="sxs-lookup"><span data-stu-id="969e9-139">Find the URI for the default namespace</span></span>|<span data-ttu-id="969e9-140"><xref:System.Xml.XmlNamespaceManager.DefaultNamespace%2A> -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="969e9-140"><xref:System.Xml.XmlNamespaceManager.DefaultNamespace%2A> property</span></span>|  
|<span data-ttu-id="969e9-141">Suchen des URIs für ein Namespacepräfix</span><span class="sxs-lookup"><span data-stu-id="969e9-141">Find the URI for a namespace prefix</span></span>|<span data-ttu-id="969e9-142"><xref:System.Xml.XmlNamespaceManager.LookupNamespace%2A>-Methode</span><span class="sxs-lookup"><span data-stu-id="969e9-142"><xref:System.Xml.XmlNamespaceManager.LookupNamespace%2A> method</span></span>|  
|<span data-ttu-id="969e9-143">Suchen des Präfixes für einen Namespace-URI</span><span class="sxs-lookup"><span data-stu-id="969e9-143">Find the prefix for a namespace URI</span></span>|<span data-ttu-id="969e9-144"><xref:System.Xml.XmlNamespaceManager.LookupPrefix%2A>-Methode</span><span class="sxs-lookup"><span data-stu-id="969e9-144"><xref:System.Xml.XmlNamespaceManager.LookupPrefix%2A> method</span></span>|  
|<span data-ttu-id="969e9-145">Abrufen einer Namespaceliste im aktuellen Knoten</span><span class="sxs-lookup"><span data-stu-id="969e9-145">Get a list of namespaces in the current node</span></span>|<span data-ttu-id="969e9-146"><xref:System.Xml.XmlNamespaceManager.GetNamespacesInScope%2A>-Methode</span><span class="sxs-lookup"><span data-stu-id="969e9-146"><xref:System.Xml.XmlNamespaceManager.GetNamespacesInScope%2A> method</span></span>|  
|<span data-ttu-id="969e9-147">Festlegen des Gültigkeitsbereichs für einen Namespace</span><span class="sxs-lookup"><span data-stu-id="969e9-147">Scope a namespace</span></span>|<span data-ttu-id="969e9-148">Die Methoden <xref:System.Xml.XmlNamespaceManager.PushScope%2A> und <xref:System.Xml.XmlNamespaceManager.PopScope%2A></span><span class="sxs-lookup"><span data-stu-id="969e9-148"><xref:System.Xml.XmlNamespaceManager.PushScope%2A> and <xref:System.Xml.XmlNamespaceManager.PopScope%2A> methods</span></span>|  
|<span data-ttu-id="969e9-149">Überprüfen, ob im aktuellen Gültigkeitsbereich ein Präfix definiert ist</span><span class="sxs-lookup"><span data-stu-id="969e9-149">Check whether a prefix is defined in the current scope</span></span>|<span data-ttu-id="969e9-150"><xref:System.Xml.XmlNamespaceManager.HasNamespace%2A>-Methode</span><span class="sxs-lookup"><span data-stu-id="969e9-150"><xref:System.Xml.XmlNamespaceManager.HasNamespace%2A> method</span></span>|  
|<span data-ttu-id="969e9-151">Abrufen der Namenstabelle, die für die Suche nach Präfixen und URIs verwendet wird</span><span class="sxs-lookup"><span data-stu-id="969e9-151">Get the name table used to look up prefixes and URIs</span></span>|<span data-ttu-id="969e9-152"><xref:System.Xml.XmlNamespaceManager.NameTable%2A> -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="969e9-152"><xref:System.Xml.XmlNamespaceManager.NameTable%2A> property</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="969e9-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="969e9-153">See also</span></span>

- <xref:System.Xml.XmlNamespaceManager>
- [<span data-ttu-id="969e9-154">XML-Dokumente und -Daten</span><span class="sxs-lookup"><span data-stu-id="969e9-154">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
