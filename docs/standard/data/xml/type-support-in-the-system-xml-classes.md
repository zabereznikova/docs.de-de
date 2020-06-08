---
title: Typenunterstützung in den System.Xml-Klassen
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
ms.openlocfilehash: 8ceda15cb8463db3e81260529ebb1e3a67a0c1af
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283298"
---
# <a name="type-support-in-the-systemxml-classes"></a><span data-ttu-id="01a31-102">Typenunterstützung in den System.Xml-Klassen</span><span class="sxs-lookup"><span data-stu-id="01a31-102">Type Support in the System.Xml Classes</span></span>
<span data-ttu-id="01a31-103">In .NET Framework, Version 2.0, wurden die Kern-XML-Klassen erweitert und enthalten nun Funktionen zur Typunterstützung.</span><span class="sxs-lookup"><span data-stu-id="01a31-103">In the .NET Framework version 2.0, the core XML classes have been enhanced to include type support features.</span></span> <span data-ttu-id="01a31-104">Die Klassen <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> und <xref:System.Xml.XPath.XPathNavigator> enthalten Funktionen zur Typunterstützung. Dazu gehört auch die Funktion zum Konvertieren zwischen XML-Schematypen und CLR-Typen (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="01a31-104">The <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes include type support features including the ability to convert between XML Schema types and common language runtime (CLR) types.</span></span>  
  
 <span data-ttu-id="01a31-105">In .NET Framework, Version 2.0, wurden die Klassen <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> und <xref:System.Xml.XPath.XPathNavigator> erweitert und enthalten nun Funktionen zur Typunterstützung.</span><span class="sxs-lookup"><span data-stu-id="01a31-105">In the .NET Framework version 2.0, the <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.XPath.XPathNavigator> classes have been enhanced to include type support features.</span></span>  
  
- <span data-ttu-id="01a31-106">Die <xref:System.Xml.XmlReader>-Klasse und die <xref:System.Xml.XPath.XPathNavigator>-Klasse enthalten jeweils eine **SchemaInfo**-Eigenschaft, die die Schemainformationen eines Knotens zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="01a31-106">The <xref:System.Xml.XmlReader> and <xref:System.Xml.XPath.XPathNavigator> classes each include a **SchemaInfo** property that returns the schema information on a node.</span></span>  
  
- <span data-ttu-id="01a31-107">Die **ReadContentAs**-Eigenschaft und die **ReadElementContentAs**-Eigenschaft sowie die Methoden der <xref:System.Xml.XmlReader>-Klasse lesen einen Textwert und konvertieren diesen durch einen einzigen Methodenaufruf in einen CLR-Wert.</span><span class="sxs-lookup"><span data-stu-id="01a31-107">The **ReadContentAs** and **ReadElementContentAs** and methods on the <xref:System.Xml.XmlReader> class read a text value and convert it to a CLR value in a single method call.</span></span>  
  
- <span data-ttu-id="01a31-108">Die <xref:System.Xml.XmlWriter.WriteValue%2A>-Methode der <xref:System.Xml.XmlWriter>-Klasse konvertiert einen CLR-Typ beim Schreiben von XML-Daten in einen XML-Schematyp.</span><span class="sxs-lookup"><span data-stu-id="01a31-108">The <xref:System.Xml.XmlWriter.WriteValue%2A> method on the <xref:System.Xml.XmlWriter> class converts a CLR type to an XML Schema type when writing out XML.</span></span>  
  
- <span data-ttu-id="01a31-109">Die **ValueAs**-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse geben einen Knotenwert zurück und konvertieren diesen durch einen einzigen Methodenaufruf in einen CLR-Wert.</span><span class="sxs-lookup"><span data-stu-id="01a31-109">The **ValueAs** and <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> properties on the <xref:System.Xml.XPath.XPathNavigator> class return a node value and convert it to a CLR value in a single method call.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="01a31-110">In .NET Framework, Version 1.0, war zum Konvertieren zwischen XML-Schematypen und CLR-Typen die <xref:System.Xml.XmlConvert>-Klasse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="01a31-110">In the .NET Framework version 1.0 the <xref:System.Xml.XmlConvert> class was needed to convert between XML Schema and CLR types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="01a31-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="01a31-111">In This Section</span></span>  
 [<span data-ttu-id="01a31-112">Zuordnen von XML-Datentypen zu CLR-Typen</span><span class="sxs-lookup"><span data-stu-id="01a31-112">Mapping XML Data Types to CLR Types</span></span>](mapping-xml-data-types-to-clr-types.md)  
 <span data-ttu-id="01a31-113">Beschreibt die Standardzuordnungen von XML-Datentypen zu CLR-Typen.</span><span class="sxs-lookup"><span data-stu-id="01a31-113">Describes the default mappings of XML data types to CLR types.</span></span>  
  
 [<span data-ttu-id="01a31-114">Implementierungshinweise zur XML-Typunterstützung</span><span class="sxs-lookup"><span data-stu-id="01a31-114">XML Type Support Implementation Notes</span></span>](xml-type-support-implementation-notes.md)  
 <span data-ttu-id="01a31-115">Erläutert einige Implementierungsdetails der Typunterstützung.</span><span class="sxs-lookup"><span data-stu-id="01a31-115">Discusses some of the type support implementation details.</span></span>  
  
 [<span data-ttu-id="01a31-116">Konvertierung von XML-Datentypen</span><span class="sxs-lookup"><span data-stu-id="01a31-116">Conversion of XML Data Types</span></span>](conversion-of-xml-data-types.md)  
 <span data-ttu-id="01a31-117">Beschreibt die Verwendung der <xref:System.Xml.XmlConvert>-Klasse zum Konvertieren zwischen XML-Schematypen und CLR-Typen.</span><span class="sxs-lookup"><span data-stu-id="01a31-117">Describes how to use the <xref:System.Xml.XmlConvert> class to convert between XML Schema and CLR types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="01a31-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="01a31-118">Related Sections</span></span>  
 [<span data-ttu-id="01a31-119">Zugreifen auf streng typisierte XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="01a31-119">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](accessing-strongly-typed-xml-data-using-xpathnavigator.md)
