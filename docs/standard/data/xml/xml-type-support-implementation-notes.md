---
title: "Implementierungshinweise zur XML-Typunterstützung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26b071f3-1261-47ef-8690-0717f5cd93c1
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5e99573fc3a82db7798426172a13a78e10c65636
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xml-type-support-implementation-notes"></a><span data-ttu-id="68127-102">Implementierungshinweise zur XML-Typunterstützung</span><span class="sxs-lookup"><span data-stu-id="68127-102">XML Type Support Implementation Notes</span></span>
<span data-ttu-id="68127-103">In diesem Thema werden einige Implementierungsdetails beschrieben, die Sie beachten müssen.</span><span class="sxs-lookup"><span data-stu-id="68127-103">This topic describes some implementation details that you want to be aware of.</span></span>  
  
## <a name="list-mappings"></a><span data-ttu-id="68127-104">Listenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="68127-104">List Mappings</span></span>  
 <span data-ttu-id="68127-105">Die <xref:System.Collections.IList>, <xref:System.Collections.ICollection>, <xref:System.Collections.IEnumerable>, **[] geben**, und <xref:System.String> Typen werden verwendet, um die Typen von XML Schema Definition Language (XSD) Liste darstellen.</span><span class="sxs-lookup"><span data-stu-id="68127-105">The <xref:System.Collections.IList>, <xref:System.Collections.ICollection>, <xref:System.Collections.IEnumerable>, **Type[]**, and <xref:System.String> types are used to represent XML Schema definition language (XSD) list types.</span></span>  
  
## <a name="union-mappings"></a><span data-ttu-id="68127-106">Union-Zuordnungen</span><span class="sxs-lookup"><span data-stu-id="68127-106">Union Mappings</span></span>  
 <span data-ttu-id="68127-107">Union-Typen werden durch den <xref:System.Xml.Schema.XmlAtomicValue>-Typ oder den <xref:System.String>-Typ dargestellt.</span><span class="sxs-lookup"><span data-stu-id="68127-107">Union types are represented using the <xref:System.Xml.Schema.XmlAtomicValue> or <xref:System.String> type.</span></span> <span data-ttu-id="68127-108">Der Ausgangs- oder Zieltyp muss daher immer <xref:System.String> oder <xref:System.Xml.Schema.XmlAtomicValue> sein.</span><span class="sxs-lookup"><span data-stu-id="68127-108">The source type or the destination type must therefore always be either <xref:System.String> or <xref:System.Xml.Schema.XmlAtomicValue>.</span></span>  
  
 <span data-ttu-id="68127-109">Wenn das <xref:System.Xml.Schema.XmlSchemaDatatype>-Objekt einen Listentyp darstellt, konvertiert das Objekt den Wert der Eingabezeichenfolge in eine Liste aus einem oder mehreren Objekten.</span><span class="sxs-lookup"><span data-stu-id="68127-109">If the <xref:System.Xml.Schema.XmlSchemaDatatype> object represents a list type the object converts the input string value to a list of one or more objects.</span></span> <span data-ttu-id="68127-110">Wenn das <xref:System.Xml.Schema.XmlSchemaDatatype>-Objekt einen Union-Typ darstellt, wird versucht, den Eingabewert als einen Membertyp der Union zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="68127-110">If the <xref:System.Xml.Schema.XmlSchemaDatatype> represents a union type then an attempt is made to parse the input value as a member type of the union.</span></span> <span data-ttu-id="68127-111">Wenn ein Versuch fehlschlägt, wird der Konvertierungsversuch mit dem nächsten Member der Union wiederholt. Dies wird wiederholt bis die Konvertierung erfolgreich ist oder bis die Konvertierung für alle Membertypen erfolglos war. In diesem Fall wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="68127-111">If the parse attempt fails then the conversion is attempted with the next member of the union and so on until the conversion is successful, or there are no other member types to try, in which case an exception is thrown.</span></span>  
  
## <a name="differences-between-clr-and-xml-data-types"></a><span data-ttu-id="68127-112">Unterschiede zwischen CLR-Datentypen und XML-Datentypen</span><span class="sxs-lookup"><span data-stu-id="68127-112">Differences Between CLR and XML Data Types</span></span>  
 <span data-ttu-id="68127-113">Es folgt eine Beschreibung möglicher Konflikte zwischen CLR-Datentypen und XML-Datentypen und ihrer Behandlung.</span><span class="sxs-lookup"><span data-stu-id="68127-113">The following describes certain mismatches that can occur between CLR types and XML data types and how they are handled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68127-114">Das `xs`-Präfix wird dem Namespace-URI http://www.w3.org/2001/XMLSchema zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="68127-114">The `xs` prefix is mapped to the http://www.w3.org/2001/XMLSchema and namespace URI.</span></span>  
  
### <a name="systemtimespan-and-xsduration"></a><span data-ttu-id="68127-115">"System.TimeSpan" und "xs:duration"</span><span class="sxs-lookup"><span data-stu-id="68127-115">System.TimeSpan and xs:duration</span></span>  
 <span data-ttu-id="68127-116">Der `xs:duration`-Typ ist insofern partiell geordnet, als dass es Intervalle gibt, die verschieden, aber äquivalent sind.</span><span class="sxs-lookup"><span data-stu-id="68127-116">The `xs:duration` type is partially ordered in that there are certain duration values that are different but equivalent.</span></span> <span data-ttu-id="68127-117">Dies bedeutet, dass für Werte von Typ `xs:duration` gilt, dass ein Monat (P1M) kleiner als 32 Tage (P32D), größer als 27 Tage (P27D) und äquivalent zu 28, 29 oder 30 Tagen ist.</span><span class="sxs-lookup"><span data-stu-id="68127-117">This means that for the `xs:duration` type value such as 1 month (P1M) is less than 32 days (P32D), larger than 27 days (P27D) and equivalent to 28, 29 or 30 days.</span></span>  
  
 <span data-ttu-id="68127-118">Die <xref:System.TimeSpan>-Klasse unterstützt diese partielle Ordnung nicht.</span><span class="sxs-lookup"><span data-stu-id="68127-118">The <xref:System.TimeSpan> class does not support this partial ordering.</span></span> <span data-ttu-id="68127-119">Für ein Jahr und einen Monat wird eine bestimmte Anzahl von Tagen (365 bzw. 30) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="68127-119">Instead, it picks a specific number of days for 1 year and 1 month; 365 days and 30 days respectively.</span></span>  
  
 <span data-ttu-id="68127-120">Weitere Informationen über den `xs:duration`-Typ finden Sie im W3C XML Schema Part 2: Datatypes Recommendation unter http://www.w3.org/TR/xmlschema-2/.</span><span class="sxs-lookup"><span data-stu-id="68127-120">For more information on the `xs:duration` type, see the W3C XML Schema Part 2: Datatypes Recommendation at http://www.w3.org/TR/xmlschema-2/.</span></span>  
  
### <a name="xstime-gregorian-date-types-and-systemdatetime"></a><span data-ttu-id="68127-121">"xs:time", Typen für das gregorianische Datum und "System.DateTime"</span><span class="sxs-lookup"><span data-stu-id="68127-121">xs:time, Gregorian Date Types, and System.DateTime</span></span>  
 <span data-ttu-id="68127-122">Wenn einem `xs:time`-Wert ein <xref:System.DateTime>-Objekt zugeordnet wird, wird das <xref:System.DateTime.MinValue>-Feld zur Initialisierung der Datumseigenschaften des <xref:System.DateTime>-Objekts (z. B. <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A> oder <xref:System.DateTime.Day%2A>) mit dem kleinsten möglichen <xref:System.DateTime>-Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="68127-122">When an `xs:time` value is mapped to a <xref:System.DateTime> object, the <xref:System.DateTime.MinValue> field is used to initialize the date properties of the <xref:System.DateTime> object (such as <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, and <xref:System.DateTime.Day%2A>) to the smallest possible <xref:System.DateTime> value.</span></span>  
  
 <span data-ttu-id="68127-123">In gleicher Weise wird den Instanzen von `xs:gMonth`, `xs:gDay`, `xs:gYear`, `xs:gYearMonth` und `xs:gMonthDay` ein <xref:System.DateTime>-Objekt zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="68127-123">Similarly, instances of `xs:gMonth`, `xs:gDay`, `xs:gYear`, `xs:gYearMonth` and `xs:gMonthDay` are also mapped to a <xref:System.DateTime> object.</span></span> <span data-ttu-id="68127-124">Nicht verwendete Eigenschaften des <xref:System.DateTime>-Objekts werden mit den Werten von <xref:System.DateTime.MinValue> initialisiert.</span><span class="sxs-lookup"><span data-stu-id="68127-124">Unused properties on the <xref:System.DateTime> object are initialized to those from <xref:System.DateTime.MinValue>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68127-125">Wenn der Inhalt den Typ <xref:System.DateTime.Year%2A?displayProperty=nameWithType> hat, ist der `xs:gMonthDay`-Wert nicht verlässlich.</span><span class="sxs-lookup"><span data-stu-id="68127-125">You cannot rely on the <xref:System.DateTime.Year%2A?displayProperty=nameWithType> value when the content is typed as `xs:gMonthDay`.</span></span> <span data-ttu-id="68127-126">Der <xref:System.DateTime.Year%2A?displayProperty=nameWithType>-Wert wird in diesem Fall immer auf 1904 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="68127-126">The <xref:System.DateTime.Year%2A?displayProperty=nameWithType> value is always set to 1904 in this case.</span></span>  
  
### <a name="xsanyuri-and-systemuri"></a><span data-ttu-id="68127-127">"xs:anyURI" und "System.Uri"</span><span class="sxs-lookup"><span data-stu-id="68127-127">xs:anyURI and System.Uri</span></span>  
 <span data-ttu-id="68127-128">Wenn einer Instanz von `xs:anyURI`, die einen relativen URI darstellt, ein <xref:System.Uri> zugeordnet wird, hat das <xref:System.Uri>-Objekt keinen Basis-URI.</span><span class="sxs-lookup"><span data-stu-id="68127-128">When an instance of `xs:anyURI` that represents a relative URI is mapped to a <xref:System.Uri>, the <xref:System.Uri> object does not have a base URI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68127-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68127-129">See Also</span></span>  
 [<span data-ttu-id="68127-130">Type Support in the System.Xml Classes (Typenunterstützung in den System.Xml-Klassen)</span><span class="sxs-lookup"><span data-stu-id="68127-130">Type Support in the System.Xml Classes</span></span>](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)
