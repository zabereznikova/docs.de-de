---
title: Verwendung von System.Xml
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce9869d538b69af9beaa74be3300175f279b8f53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572813"
---
# <a name="systemxml-usage"></a><span data-ttu-id="a5ccf-102">Verwendung von System.Xml</span><span class="sxs-lookup"><span data-stu-id="a5ccf-102">System.Xml Usage</span></span>
<span data-ttu-id="a5ccf-103">In diesem Abschnitt finden Sie zur Verwendung von mehreren Typen, die in den <xref:System.Xml?displayProperty=nameWithType> Namespaces, die zum Darstellen von XML-Daten verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a5ccf-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>  
  
 <span data-ttu-id="a5ccf-104">**X DO NOT** verwenden <xref:System.Xml.XmlNode> oder <xref:System.Xml.XmlDocument> zur Darstellung von XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="a5ccf-104">**X DO NOT** use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="a5ccf-105">Mithilfe von Instanzen der begünstigen <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, oder Untertypen von <xref:System.Xml.Linq.XNode> stattdessen.</span><span class="sxs-lookup"><span data-stu-id="a5ccf-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="a5ccf-106">`XmlNode` und `XmlDocument` dienen zum Verfügbarmachen von in öffentlichen APIs nicht.</span><span class="sxs-lookup"><span data-stu-id="a5ccf-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>  
  
 <span data-ttu-id="a5ccf-107">**✓ DO** verwenden `XmlReader`, `IXPathNavigable`, oder Untertypen von `XNode` als Eingabe oder Ausgabe von Membern, die XML annehmen oder zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a5ccf-107">**✓ DO** use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>  
  
 <span data-ttu-id="a5ccf-108">Verwenden Sie diese Abstraktionen anstelle von `XmlDocument`, `XmlNode`, oder <xref:System.Xml.XPath.XPathDocument>, da dies die Methoden aus bestimmter Implementierungen von XML-Dokuments im Arbeitsspeicher entkoppelt und ermöglicht es ihnen, die mit virtuellen XML-Datenquellen arbeiten, die verfügbar machen `XNode` , `XmlReader`, oder <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="a5ccf-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="a5ccf-109">**X DO NOT** Unterklasse `XmlDocument` , wenn Sie einen Typ, eine XML-Sicht des zugrunde liegenden Modell oder die Datenquelle erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="a5ccf-109">**X DO NOT** subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>  
  
 <span data-ttu-id="a5ccf-110">*Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="a5ccf-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="a5ccf-111">*Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*</span><span class="sxs-lookup"><span data-stu-id="a5ccf-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ccf-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5ccf-112">See Also</span></span>  
 [<span data-ttu-id="a5ccf-113">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a5ccf-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="a5ccf-114">Verwendungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a5ccf-114">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
