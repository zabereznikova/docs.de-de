---
title: Verwendung von System.Xml
ms.date: 10/22/2008
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 46282afa6548c731b04c40d8de91a1fed997c57c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677569"
---
# <a name="systemxml-usage"></a><span data-ttu-id="ff371-102">Verwendung von System.Xml</span><span class="sxs-lookup"><span data-stu-id="ff371-102">System.Xml Usage</span></span>

<span data-ttu-id="ff371-103">In diesem Abschnitt wird die Verwendung mehrerer Typen in <xref:System.Xml?displayProperty=nameWithType> Namespaces erläutert, die zum Darstellen von XML-Daten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ff371-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>

 <span data-ttu-id="ff371-104">❌ Verwenden Sie <xref:System.Xml.XmlNode> oder nicht <xref:System.Xml.XmlDocument> , um XML-Daten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ff371-104">❌ DO NOT use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="ff371-105">Bevorzugen Sie stattdessen die Verwendung von Instanzen der-,-,- <xref:System.Xml.XPath.IXPathNavigable> <xref:System.Xml.XmlReader> oder- <xref:System.Xml.XmlWriter> Untertypen von <xref:System.Xml.Linq.XNode> .</span><span class="sxs-lookup"><span data-stu-id="ff371-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="ff371-106">`XmlNode` und `XmlDocument` sind nicht für die Bereitstellung in öffentlichen APIs konzipiert.</span><span class="sxs-lookup"><span data-stu-id="ff371-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>

 <span data-ttu-id="ff371-107">✔️ verwenden `XmlReader` die-,-oder- `IXPathNavigable` Untertypen von `XNode` als Eingabe oder Ausgabe von Membern, die XML akzeptieren oder zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ff371-107">✔️ DO use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>

 <span data-ttu-id="ff371-108">Verwenden Sie diese Abstraktionen anstelle von `XmlDocument` , `XmlNode` oder <xref:System.Xml.XPath.XPathDocument> , da dadurch die Methoden von bestimmten Implementierungen eines XML-Dokuments im Arbeitsspeicher entkoppelt und mit virtuellen XML-Datenquellen verwendet werden können, die `XNode` , `XmlReader` oder <xref:System.Xml.XPath.XPathNavigator> verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="ff371-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>

 <span data-ttu-id="ff371-109">❌ Verwenden Sie keine Unterklasse `XmlDocument` , wenn Sie einen Typ erstellen möchten, der eine XML-Sicht eines zugrunde liegenden Objektmodells oder einer zugrunde liegenden Datenquelle darstellt.</span><span class="sxs-lookup"><span data-stu-id="ff371-109">❌ DO NOT subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>

 <span data-ttu-id="ff371-110">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="ff371-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="ff371-111">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="ff371-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="ff371-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff371-112">See also</span></span>

- [<span data-ttu-id="ff371-113">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ff371-113">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="ff371-114">Verwendungs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ff371-114">Usage Guidelines</span></span>](usage-guidelines.md)
