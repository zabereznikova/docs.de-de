---
title: "Implementierungshinweise zur XML-Typunterst&#252;tzung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 26b071f3-1261-47ef-8690-0717f5cd93c1
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# Implementierungshinweise zur XML-Typunterst&#252;tzung
In diesem Thema werden einige Implementierungsdetails beschrieben, die Sie beachten müssen.  
  
## Listenzuordnungen  
 Die Typen <xref:System.Collections.IList>, <xref:System.Collections.ICollection>, <xref:System.Collections.IEnumerable>, **Type\[\]** und <xref:System.String> werden zur Darstellung von XSD\-Listentypen \(XML Schema Definition Language\) verwendet.  
  
## Union\-Zuordnungen  
 Union\-Typen werden durch den <xref:System.Xml.Schema.XmlAtomicValue>\-Typ oder den <xref:System.String>\-Typ dargestellt.  Der Ausgangs\- oder Zieltyp muss daher immer <xref:System.String> oder <xref:System.Xml.Schema.XmlAtomicValue> sein.  
  
 Wenn das <xref:System.Xml.Schema.XmlSchemaDatatype>\-Objekt einen Listentyp darstellt, konvertiert das Objekt den Wert der Eingabezeichenfolge in eine Liste aus einem oder mehreren Objekten.  Wenn das <xref:System.Xml.Schema.XmlSchemaDatatype>\-Objekt einen Union\-Typ darstellt, wird versucht, den Eingabewert als einen Membertyp der Union zu interpretieren.  Wenn ein Versuch fehlschlägt, wird der Konvertierungsversuch mit dem nächsten Member der Union wiederholt. Dies wird wiederholt bis die Konvertierung erfolgreich ist oder bis die Konvertierung für alle Membertypen erfolglos war. In diesem Fall wird eine Ausnahme ausgelöst.  
  
## Unterschiede zwischen CLR\-Datentypen und XML\-Datentypen  
 Es folgt eine Beschreibung möglicher Konflikte zwischen CLR\-Datentypen und XML\-Datentypen und ihrer Behandlung.  
  
> [!NOTE]
>  Das `xs`\-Präfix wird dem Namespace\-URI http:\/\/www.w3.org\/2001\/XMLSchema zugeordnet.  
  
### "System.TimeSpan" und "xs:duration"  
 Der `xs:duration`\-Typ ist insofern partiell geordnet, als dass es Intervalle gibt, die verschieden, aber äquivalent sind.  Dies bedeutet, dass für Werte von Typ `xs:duration` gilt, dass ein Monat \(P1M\) kleiner als 32 Tage \(P32D\), größer als 27 Tage \(P27D\) und äquivalent zu 28, 29 oder 30 Tagen ist.  
  
 Die <xref:System.TimeSpan>\-Klasse unterstützt diese partielle Ordnung nicht.  Für ein Jahr und einen Monat wird eine bestimmte Anzahl von Tagen \(365 bzw. 30\) festgelegt.  
  
 Weitere Informationen über den `xs:duration`\-Typ finden Sie im W3C XML Schema Part 2: Datatypes Recommendation unter http:\/\/www.w3.org\/TR\/xmlschema\-2\/.  
  
### "xs:time", Typen für das gregorianische Datum und "System.DateTime"  
 Wenn einem `xs:time`\-Wert ein <xref:System.DateTime>\-Objekt zugeordnet wird, wird das <xref:System.DateTime.MinValue>\-Feld zur Initialisierung der Datumseigenschaften des <xref:System.DateTime>\-Objekts \(z. B. <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A> oder <xref:System.DateTime.Day%2A>\) mit dem kleinsten möglichen <xref:System.DateTime>\-Wert verwendet.  
  
 In gleicher Weise wird den Instanzen von `xs:gMonth`, `xs:gDay`, `xs:gYear`, `xs:gYearMonth` und `xs:gMonthDay` ein <xref:System.DateTime>\-Objekt zugeordnet.  Nicht verwendete Eigenschaften des <xref:System.DateTime>\-Objekts werden mit den Werten von <xref:System.DateTime.MinValue> initialisiert.  
  
> [!NOTE]
>  Wenn der Inhalt den Typ `xs:gMonthDay` hat, ist der <xref:System.DateTime.Year%2A?displayProperty=fullName>\-Wert nicht verlässlich.  Der <xref:System.DateTime.Year%2A?displayProperty=fullName>\-Wert wird in diesem Fall immer auf 1904 festgelegt.  
  
### "xs:anyURI" und "System.Uri"  
 Wenn einer Instanz von `xs:anyURI`, die einen relativen URI darstellt, ein <xref:System.Uri> zugeordnet wird, hat das <xref:System.Uri>\-Objekt keinen Basis\-URI.  
  
## Siehe auch  
 [Typenunterstützung in den System.Xml\-Klassen](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)