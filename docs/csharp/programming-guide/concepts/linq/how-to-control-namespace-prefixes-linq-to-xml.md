---
title: 'Gewusst wie: Steuern von Namespacepräfixen (C#) (LINQ to XML)'
description: Hier erfahren Sie, wie Sie Namespacepräfixe beim Serialisieren eines XML-Baums in LINQ to XML in C# steuern. Für einige Szenarios ist die Steuerung von Namespacepräfixen erforderlich.
ms.date: 07/20/2015
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
ms.openlocfilehash: b0c5cbfa7488f3a7105595830ef6765e6bfb1f12
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105305"
---
# <a name="how-to-control-namespace-prefixes-c-linq-to-xml"></a><span data-ttu-id="fb907-104">Gewusst wie: Steuern von Namespacepräfixen (C#) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="fb907-104">How to control namespace prefixes (C#) (LINQ to XML)</span></span>
<span data-ttu-id="fb907-105">In diesem Thema wird beschrieben, wie Sie beim Serialisieren einer XML-Struktur Namespacepräfixe steuern können.</span><span class="sxs-lookup"><span data-stu-id="fb907-105">This topic describes how you can control namespace prefixes when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="fb907-106">In vielen Situationen ist es nicht notwendig, die Namespacepräfixe zu steuern.</span><span class="sxs-lookup"><span data-stu-id="fb907-106">In many situations, it is not necessary to control namespace prefixes.</span></span>  
  
 <span data-ttu-id="fb907-107">Bestimmte XML-Programmiertools erfordern jedoch eine spezifische Steuerung der Namespacepräfixe.</span><span class="sxs-lookup"><span data-stu-id="fb907-107">However, certain XML programming tools require specific control of namespace prefixes.</span></span> <span data-ttu-id="fb907-108">Angenommen, Sie möchten z. B. ein XSLT-Stylesheet oder ein XAML-Dokument bearbeiten, das eingebettete XPath-Ausdrücke enthält, die auf bestimmte Namespacepräfixe verweisen. In diesem Fall ist es wichtig, dass das Dokument mit diesen konkreten Präfixen serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="fb907-108">For example, you might be manipulating an XSLT style sheet or a XAML document that contains embedded XPath expressions that refer to specific namespace prefixes; in this case, it is important that the document be serialized with those specific prefixes.</span></span>  
  
 <span data-ttu-id="fb907-109">Dies ist der häufigste Grund für die Steuerung von Namespacepräfixen.</span><span class="sxs-lookup"><span data-stu-id="fb907-109">This is the most common reason for controlling namespace prefixes.</span></span>  
  
 <span data-ttu-id="fb907-110">Ein weiterer Grund für die Notwendigkeit, Namespacepräfixe zu steuern, liegt darin, dass die Benutzer das XML-Dokument manuell bearbeiten können sollen und dass Sie Namespacepräfixe erstellen möchten, die für den Benutzer einfach einzugeben sind.</span><span class="sxs-lookup"><span data-stu-id="fb907-110">Another common reason for controlling namespace prefixes is that you want users to edit the XML document manually, and you want to create namespace prefixes that are convenient for the user to type.</span></span> <span data-ttu-id="fb907-111">Nehmen wir z. B. an, Sie möchten ein XSD-Dokument generieren.</span><span class="sxs-lookup"><span data-stu-id="fb907-111">For example, you might be generating an XSD document.</span></span> <span data-ttu-id="fb907-112">Den Konventionen für Schemas zufolge verwenden Sie  als Präfix für den Schemanamespace entweder `xs` oder `xsd`.</span><span class="sxs-lookup"><span data-stu-id="fb907-112">Conventions for schemas suggest that you use either `xs` or `xsd` as the prefix for the schema namespace.</span></span>  
  
 <span data-ttu-id="fb907-113">Zum Steuern von Namespacepräfixen fügen Sie Attribute ein, die Namespaces deklarieren.</span><span class="sxs-lookup"><span data-stu-id="fb907-113">To control namespace prefixes, you insert attributes that declare namespaces.</span></span> <span data-ttu-id="fb907-114">Wenn Sie die Namespaces mit bestimmten Präfixen deklarieren, versucht [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], die Namespacepräfixe beim Serialisieren zu beachten.</span><span class="sxs-lookup"><span data-stu-id="fb907-114">If you declare the namespaces with specific prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will attempt to honor the namespace prefixes when serializing.</span></span>  
  
 <span data-ttu-id="fb907-115">Beim Erstellen eines Attributs, das einen Namespace mit einem Präfix deklariert, erstellen Sie ein Attribut, bei dem der Namespace des Namens des Attributs <xref:System.Xml.Linq.XNamespace.Xmlns%2A> lautet und der Name des Attributs das Namespacepräfix ist.</span><span class="sxs-lookup"><span data-stu-id="fb907-115">To create an attribute that declares a namespace with a prefix, you create an attribute where the namespace of the name of the attribute is <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, and the name of the attribute is the namespace prefix.</span></span> <span data-ttu-id="fb907-116">Der Wert des Attributs ist der URI des Namespace.</span><span class="sxs-lookup"><span data-stu-id="fb907-116">The value of the attribute is the URI of the namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb907-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb907-117">Example</span></span>  
 <span data-ttu-id="fb907-118">Dieses Beispiel deklariert zwei Namespaces.</span><span class="sxs-lookup"><span data-stu-id="fb907-118">This example declares two namespaces.</span></span> <span data-ttu-id="fb907-119">Es gibt für den `http://www.adventure-works.com`-Namespace das Präfix `aw` und für den `www.fourthcoffee.com`-Namespace das Präfix `fc` an.</span><span class="sxs-lookup"><span data-stu-id="fb907-119">It specifies that the `http://www.adventure-works.com` namespace has the prefix of `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="fb907-120">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="fb907-120">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb907-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb907-121">See also</span></span>

- [<span data-ttu-id="fb907-122">Namespaces: Übersicht (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fb907-122">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
