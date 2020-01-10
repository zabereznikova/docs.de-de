---
title: Verwendung von System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: c57f5451526094d58066d7d391f41795f17732de
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709035"
---
# <a name="systemxml-usage"></a><span data-ttu-id="17753-102">Verwendung von System.Xml</span><span class="sxs-lookup"><span data-stu-id="17753-102">System.Xml Usage</span></span>
<span data-ttu-id="17753-103">In diesem Abschnitt wird die Verwendung mehrerer Typen in <xref:System.Xml?displayProperty=nameWithType> Namespaces erläutert, die zur Darstellung von XML-Daten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="17753-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>  
  
 <span data-ttu-id="17753-104">**X DO NOT** verwenden <xref:System.Xml.XmlNode> oder <xref:System.Xml.XmlDocument> zur Darstellung von XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="17753-104">**X DO NOT** use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="17753-105">Bevorzugen Sie stattdessen die Verwendung von Instanzen von <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>oder Untertypen von <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="17753-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="17753-106">`XmlNode` und `XmlDocument` sind nicht für die Bereitstellung in öffentlichen APIs konzipiert.</span><span class="sxs-lookup"><span data-stu-id="17753-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>  
  
 <span data-ttu-id="17753-107">**✓ DO** verwenden `XmlReader`, `IXPathNavigable`, oder Untertypen von `XNode` als Eingabe oder Ausgabe von Membern, die XML annehmen oder zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="17753-107">**✓ DO** use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>  
  
 <span data-ttu-id="17753-108">Verwenden Sie diese Abstraktionen anstelle von `XmlDocument`, `XmlNode`oder <xref:System.Xml.XPath.XPathDocument>, da dadurch die Methoden von bestimmten Implementierungen eines XML-Dokuments im Arbeitsspeicher entkoppelt werden und Sie mit virtuellen XML-Datenquellen arbeiten können, die `XNode`, `XmlReader`oder <xref:System.Xml.XPath.XPathNavigator>verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="17753-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="17753-109">**X DO NOT** Unterklasse `XmlDocument` , wenn Sie einen Typ, eine XML-Sicht des zugrunde liegenden Modell oder die Datenquelle erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="17753-109">**X DO NOT** subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>  
  
 <span data-ttu-id="17753-110">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="17753-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="17753-111">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="17753-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17753-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17753-112">See also</span></span>

- [<span data-ttu-id="17753-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="17753-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="17753-114">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="17753-114">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
