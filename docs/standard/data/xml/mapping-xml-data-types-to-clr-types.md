---
title: Zuordnen von XML-Datentypen zu CLR-Typen
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: cabdfcad-f359-479b-b71c-8b2fad42ca49
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9cff30147da82896fb3a757ba2fed16d794ec3c9
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004048"
---
# <a name="mapping-xml-data-types-to-clr-types"></a><span data-ttu-id="067e7-102">Zuordnen von XML-Datentypen zu CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="067e7-102">Mapping XML Data Types to CLR Types</span></span>
<span data-ttu-id="067e7-103">In der folgenden Tabelle wird die Zuordnung zwischen XML-Datentypen und CLR-Typen (Common Language Runtime) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="067e7-103">The following table describes the default mapping between the XML data types and the common language runtime (CLR) types.</span></span>  
  
## <a name="the-following-table-describes-the-default-mappings-of-an-xml-data-type-to-a-clr-type"></a><span data-ttu-id="067e7-104">In der folgenden Tabelle werden die Standardzuordnungen eines XML-Datentyps zu einem CLR-Typ beschrieben.</span><span class="sxs-lookup"><span data-stu-id="067e7-104">The following table describes the default mappings of an XML data type to a CLR type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="067e7-105">Die Präfixe `xs` und `xdt` sind den Namespace-URIs http://www.w3.org/2001/XMLSchema bzw. http://www.w3.org/2003/05/xpath-datatypes zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="067e7-105">The `xs` and the `xdt` prefixes are mapped to the http://www.w3.org/2001/XMLSchema and the http://www.w3.org/2003/05/xpath-datatypes namespace URIs respectively.</span></span>  
  
|<span data-ttu-id="067e7-106">XML-Typ</span><span class="sxs-lookup"><span data-stu-id="067e7-106">XML Type</span></span>|<span data-ttu-id="067e7-107">CLR-Typ</span><span class="sxs-lookup"><span data-stu-id="067e7-107">CLR Type</span></span>|  
|--------------|--------------|  
|`xs:anyURI`|<xref:System.Uri>|  
|`xs:base64Binary`|`Byte[]`|  
|`xs:boolean`|<xref:System.Boolean>|  
|`xs:byte`|<xref:System.SByte>|  
|`xs:date`|<xref:System.DateTime>|  
|`xs:dateTime`|<xref:System.DateTime>|  
|`xs:decimal`|<xref:System.Decimal>|  
|`xs:double`|<xref:System.Double>|  
|`xs:duration`|<xref:System.TimeSpan>|  
|`xs:ENTITIES`|`String[]`|  
|`xs:ENTITY`|<xref:System.String>|  
|`xs:float`|<xref:System.Single>|  
|`xs:gDay`|<xref:System.DateTime>|  
|`xs:gMonthDay`|<xref:System.DateTime>|  
|`xs:gYear`|<xref:System.DateTime>|  
|`xs:gYearMonth`|<xref:System.DateTime>|  
|`xs:hexBinary`|`Byte[]`|  
|`xs:ID`|<xref:System.String>|  
|`xs:IDREF`|<xref:System.String>|  
|`xs:IDREFS`|`String[]`|  
|`xs:int`|<xref:System.Int32>|  
|`xs:integer`|<xref:System.Decimal>|  
|`xs:language`|<xref:System.String>|  
|`xs:long`|<xref:System.Int64>|  
|`xs:gMmonth`|<xref:System.DateTime>|  
|`xs:Name`|<xref:System.String>|  
|`xs:NCName`|<xref:System.String>|  
|`xs:negativeInteger`|<xref:System.Decimal>|  
|`xs:NMTOKEN`|<xref:System.String>|  
|`xs:NMTOKENS`|`String[]`|  
|`xs:nonNegativeInteger`|<xref:System.Decimal>|  
|`xs:nonPositiveInteger`|<xref:System.Decimal>|  
|`xs:normalizedString`|<xref:System.String>|  
|`xs:NOTATION`|<xref:System.Xml.XmlQualifiedName>|  
|`xs:positiveInteger`|<xref:System.Decimal>|  
|`xs:QName`|<xref:System.Xml.XmlQualifiedName>|  
|`xs:short`|<xref:System.Int16>|  
|`xs:string`|<xref:System.String>|  
|`xs:time`|<xref:System.DateTime>|  
|`xs:token`|<xref:System.String>|  
|`xs:unsignedByte`|<xref:System.Byte>|  
|`xs:unsignedInt`|<xref:System.UInt32>|  
|`xs:unsignedLong`|<xref:System.UInt64>|  
|`xs:unsignedShort`|<xref:System.UInt16>|  
|`xdt:dayTimeDuration`|<xref:System.TimeSpan>|  
|`xdt:yearMonthDuration`|<xref:System.TimeSpan>|  
|`xdt:untypedAtomic`|<xref:System.String>|  
|`xdt:anyAtomicType`|<xref:System.Object>|  
|`xs:anySimpleType`|<xref:System.String>|  
|<span data-ttu-id="067e7-108">Dokumentknoten</span><span class="sxs-lookup"><span data-stu-id="067e7-108">Document node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="067e7-109">Elementknoten</span><span class="sxs-lookup"><span data-stu-id="067e7-109">Element node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="067e7-110">Attributknoten</span><span class="sxs-lookup"><span data-stu-id="067e7-110">Attribute node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="067e7-111">Namespaceknoten</span><span class="sxs-lookup"><span data-stu-id="067e7-111">Namespace node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="067e7-112">Textknoten</span><span class="sxs-lookup"><span data-stu-id="067e7-112">Text node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="067e7-113">Kommentarknoten</span><span class="sxs-lookup"><span data-stu-id="067e7-113">Comment node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="067e7-114">Verarbeitungsanweisungsknoten</span><span class="sxs-lookup"><span data-stu-id="067e7-114">Processing instruction node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
  
## <a name="see-also"></a><span data-ttu-id="067e7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="067e7-115">See also</span></span>

- [<span data-ttu-id="067e7-116">Type Support in the System.Xml Classes (Typenunterstützung in den System.Xml-Klassen)</span><span class="sxs-lookup"><span data-stu-id="067e7-116">Type Support in the System.Xml Classes</span></span>](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)
