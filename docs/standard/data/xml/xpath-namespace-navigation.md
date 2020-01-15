---
title: XPath-Namespacenavigation
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 06cc7abb-7416-415c-9dd6-67751b8cabd5
ms.openlocfilehash: 37b9d3e04e075c7ef95420c70881ba9b34e031ce
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709789"
---
# <a name="xpath-namespace-navigation"></a><span data-ttu-id="d7b7a-102">XPath-Namespacenavigation</span><span class="sxs-lookup"><span data-stu-id="d7b7a-102">XPath Namespace Navigation</span></span>
<span data-ttu-id="d7b7a-103">Zum Verwenden von XPath-Abfragen mit XML-Dokumenten müssen Sie XML-Namespaces und die darin enthaltenen Elemente korrekt adressieren.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-103">To use XPath queries with XML documents, you have to correctly address XML namespaces and the elements contained by namespaces.</span></span> <span data-ttu-id="d7b7a-104">Mithilfe von Namespaces werden Zweideutigkeiten vermieden, die auftreten können, wenn Namen in mehr als einem Kontext verwendet werden. Der Name `ID` kann beispielsweise auf mehrere ID-Bezeichner verweisen, die unterschiedlichen Elementen eines XML-Dokuments zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-104">Namespaces prevent ambiguities that can occur when names are used in more than one context; for example, the name `ID` may refer to more than one identifier associated with different elements of an XML document.</span></span> <span data-ttu-id="d7b7a-105">In der Namespace-Syntax werden URIs, Namen und Präfixe zur Unterscheidung der Elemente in einem XML-Dokument definiert.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-105">Namespace syntax specifies URIs, names, and prefixes that distinguish the elements of an XML document.</span></span>  
  
 <span data-ttu-id="d7b7a-106">Anhand des Beispiels in diesem Thema wird gezeigt, wie Präfixe beim Navigieren in einem XML-Dokument mit dem <xref:System.Xml.XPath.XPathNavigator> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-106">The example in this topic demonstrates the use of prefixes in navigating an XML document with <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="d7b7a-107">Weitere Informationen zu Namespaces und Syntax finden Sie unter [XML-Dateien: Grundlegendes zu XML-Namespaces](https://docs.microsoft.com/previous-versions/dotnet/articles/bb986013(v=msdn.10)).</span><span class="sxs-lookup"><span data-stu-id="d7b7a-107">For more information about namespaces and syntax, see [XML Files: Understanding XML Namespaces](https://docs.microsoft.com/previous-versions/dotnet/articles/bb986013(v=msdn.10)).</span></span>  
  
## <a name="namespace-declarations"></a><span data-ttu-id="d7b7a-108">Namespacedeklarationen</span><span class="sxs-lookup"><span data-stu-id="d7b7a-108">Namespace Declarations</span></span>  
 <span data-ttu-id="d7b7a-109">Mithilfe von Namespacedeklarationen werden die Elemente in einem XML-Dokument beim Verwenden einer Instanz des <xref:System.Xml.XPath.XPathNavigator> unterscheidbar und adressierbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-109">Namespace declarations make the elements of an XML document distinguishable and addressable when using an instance of <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="d7b7a-110">Namespacepräfixe stellen eine kurze Syntax für Adressierungsnamespaces bereit.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-110">Namespace prefixes provide a brief syntax for addressing namespaces.</span></span>  
  
 <span data-ttu-id="d7b7a-111">Präfixe werden durch folgende Form definiert: `<e:Envelope>`e\`" eine Abkürzung für den formalen URI des Namespaces.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-111">Prefixes are defined by the form: `<e:Envelope>`e\`" is an abbreviation for the formal URI of the namespace.</span></span> <span data-ttu-id="d7b7a-112">Sie können das `Body`-Element mit folgender Syntax als Member des `Envelope`-Namespaces kennzeichnen: `e:Body`.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-112">You can identify the `Body` element as a member of the `Envelope` namespace by using the syntax: `e:Body`.</span></span>  
  
 <span data-ttu-id="d7b7a-113">Im Navigationsbeispiel im nächsten Abschnitt wird auf das folgende XML-Dokument als `response.xml` verwiesen.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-113">The following XML document will be referenced as `response.xml` in the navigation example in the next section.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<e:Envelope xmlns:e="http://schemas.xmlsoap.org/soap/envelope/">  
  <e:Body>  
    <s:Search xmlns:s="http://schemas.microsoft.com/v1/Search">  
      <r:request xmlns:r="http://schemas.microsoft.com/v1/Search/metadata"   
                 xmlns:i="http://www.w3.org/2001/XMLSchema-instance">  
      </r:request>  
    </s:Search>  
  </e:Body>  
</e:Envelope>  
```  
  
## <a name="navigation-by-namespace-prefix"></a><span data-ttu-id="d7b7a-114">Navigation nach Namespace-Präfix</span><span class="sxs-lookup"><span data-stu-id="d7b7a-114">Navigation by Namespace Prefix</span></span>  
 <span data-ttu-id="d7b7a-115">Im Code in diesem Abschnitt werden das <xref:System.Xml.XPath.XPathNavigator>-Objekt und das <xref:System.Xml.XmlNamespaceManager>-Objekt verwendet, um das `Search`-Element im XML-Dokument vom vorherigen Abschnitt auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-115">The code in this section uses <xref:System.Xml.XPath.XPathNavigator> and <xref:System.Xml.XmlNamespaceManager> objects to select the `Search` element from the XML document in the previous section.</span></span> <span data-ttu-id="d7b7a-116">Die Abfrage `xpath` enthält Namespace-Präfixe für jedes Element im Pfad.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-116">The query `xpath` includes namespace prefixes on each element in the path.</span></span> <span data-ttu-id="d7b7a-117">Durch die Angabe der genauen Identität der Namespaces, die die einzelnen Elemente enthalten, wird die korrekte Navigation zum `Search`-Element durch die <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>-Methode sichergestellt.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-117">Specifying the precise identity of the namespaces that contain each element assures correct navigation to the `Search` element by the <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> method.</span></span>  
  
```csharp  
using (XmlReader reader = XmlReader.Create("response.xml"))  
{  
    XPathDocument doc = new XPathDocument(reader);  
    XPathNavigator nav = doc.CreateNavigator();
  
    XmlNamespaceManager nsmgr = new XmlNamespaceManager(nav.NameTable);  
    nsmgr.AddNamespace("e", @"http://schemas.xmlsoap.org/soap/envelope/");  
    nsmgr.AddNamespace("s", @"http://schemas.microsoft.com/v1/Search");  
    nsmgr.AddNamespace("r", @"http://schemas.microsoft.com/v1/Search/metadata");  
    nsmgr.AddNamespace("i", @"http://www.w3.org/2001/XMLSchema-instance");  
  
    string xpath = "/e:Envelope/e:Body/s:Search";  
  
    XPathNavigator element = nav.SelectSingleNode(xpath, nsmgr);  
  
    Console.WriteLine("Element Prefix:" + element.Prefix +   
    " Local name:" + element.LocalName);  
    Console.WriteLine("Namespace URI: " + element.NamespaceURI);  
}  
```  
  
 <span data-ttu-id="d7b7a-118">Die Präzision vollqualifizierter Namespaces und Namen dient nicht nur der Bequemlichkeit.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-118">The precision of fully qualifying namespaces and names is more than a convenience.</span></span> <span data-ttu-id="d7b7a-119">Wenn Sie ein wenig mit der Dokumentdefinition und dem Code in den voranstehenden Beispielen experimentieren, können Sie feststellen, dass bei der Navigation ohne vollqualifizierte Elementnamen Ausnahmen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-119">A little experimentation with the document definition and code in the previous examples will verify that navigation without fully qualified element names throws exceptions.</span></span> <span data-ttu-id="d7b7a-120">Beispiel: Die Elementdefinition `<Search>` und die Abfragezeichenfolge `xpath = "/s:Envelope/s:Body/Search";` würde ohne den Namespacepräfix für das `Search`-Element `null` statt des `Search`-Elements zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="d7b7a-120">For example, the element definition: `<Search>`, and query: string `xpath = "/s:Envelope/s:Body/Search";` without the namespace prefix on the `Search` element returns `null` instead of the `Search` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b7a-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7b7a-121">See also</span></span>

- [<span data-ttu-id="d7b7a-122">Zugreifen auf XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d7b7a-122">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="d7b7a-123">Auswählen, Auswerten und Zuordnen von XML-Daten mithilfe von XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d7b7a-123">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)
