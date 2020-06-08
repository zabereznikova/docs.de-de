---
title: Implementierungshinweise zur XML-Typunterstützung
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 26b071f3-1261-47ef-8690-0717f5cd93c1
ms.openlocfilehash: 91a685f122ff846217ea7a8677b29df430b65363
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290278"
---
# <a name="xml-type-support-implementation-notes"></a>Implementierungshinweise zur XML-Typunterstützung
In diesem Thema werden einige Implementierungsdetails beschrieben, die Sie beachten müssen.  
  
## <a name="list-mappings"></a>Listenzuordnungen  
 Die Typen <xref:System.Collections.IList>, <xref:System.Collections.ICollection>, <xref:System.Collections.IEnumerable>, **Type[]** und <xref:System.String> werden zur Darstellung von XSD-Listentypen (XML Schema Definition Language) verwendet.  
  
## <a name="union-mappings"></a>Union-Zuordnungen  
 Union-Typen werden durch den <xref:System.Xml.Schema.XmlAtomicValue>-Typ oder den <xref:System.String>-Typ dargestellt. Der Ausgangs- oder Zieltyp muss daher immer <xref:System.String> oder <xref:System.Xml.Schema.XmlAtomicValue> sein.  
  
 Wenn das <xref:System.Xml.Schema.XmlSchemaDatatype>-Objekt einen Listentyp darstellt, konvertiert das Objekt den Wert der Eingabezeichenfolge in eine Liste aus einem oder mehreren Objekten. Wenn das <xref:System.Xml.Schema.XmlSchemaDatatype>-Objekt einen Union-Typ darstellt, wird versucht, den Eingabewert als einen Membertyp der Union zu interpretieren. Wenn ein Versuch fehlschlägt, wird der Konvertierungsversuch mit dem nächsten Member der Union wiederholt. Dies wird wiederholt bis die Konvertierung erfolgreich ist oder bis die Konvertierung für alle Membertypen erfolglos war. In diesem Fall wird eine Ausnahme ausgelöst.  
  
## <a name="differences-between-clr-and-xml-data-types"></a>Unterschiede zwischen CLR-Datentypen und XML-Datentypen  
 Es folgt eine Beschreibung möglicher Konflikte zwischen CLR-Datentypen und XML-Datentypen und ihrer Behandlung.  
  
> [!NOTE]
> Das `xs`-Präfix wird <https://www.w3.org/2001/XMLSchema> und dem Namespace-URI zugeordnet.
  
### <a name="systemtimespan-and-xsduration"></a>"System.TimeSpan" und "xs:duration"  
 Der `xs:duration`-Typ ist insofern partiell geordnet, als dass es Intervalle gibt, die verschieden, aber äquivalent sind. Dies bedeutet, dass für Werte von Typ `xs:duration` gilt, dass ein Monat (P1M) kleiner als 32 Tage (P32D), größer als 27 Tage (P27D) und äquivalent zu 28, 29 oder 30 Tagen ist.  
  
 Die <xref:System.TimeSpan>-Klasse unterstützt diese partielle Ordnung nicht. Für ein Jahr und einen Monat wird eine bestimmte Anzahl von Tagen (365 bzw. 30) festgelegt.  
  
 Weitere Informationen über den `xs:duration`-Typ finden Sie in der W3C-Spezifikation [XML-Schema Teil 2: Empfehlungen zu Datentypen](https://www.w3.org/TR/xmlschema-2/).
  
### <a name="xstime-gregorian-date-types-and-systemdatetime"></a>"xs:time", Typen für das gregorianische Datum und "System.DateTime"  
 Wenn einem `xs:time`-Wert ein <xref:System.DateTime>-Objekt zugeordnet wird, wird das <xref:System.DateTime.MinValue>-Feld zur Initialisierung der Datumseigenschaften des <xref:System.DateTime>-Objekts (z. B. <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A> oder <xref:System.DateTime.Day%2A>) mit dem kleinsten möglichen <xref:System.DateTime>-Wert verwendet.  
  
 In gleicher Weise wird den Instanzen von `xs:gMonth`, `xs:gDay`, `xs:gYear`, `xs:gYearMonth` und `xs:gMonthDay` ein <xref:System.DateTime>-Objekt zugeordnet. Nicht verwendete Eigenschaften des <xref:System.DateTime>-Objekts werden mit den Werten von <xref:System.DateTime.MinValue> initialisiert.  
  
> [!NOTE]
> Wenn der Inhalt den Typ <xref:System.DateTime.Year%2A?displayProperty=nameWithType> hat, ist der `xs:gMonthDay`-Wert nicht verlässlich. Der <xref:System.DateTime.Year%2A?displayProperty=nameWithType>-Wert wird in diesem Fall immer auf 1904 festgelegt.  
  
### <a name="xsanyuri-and-systemuri"></a>"xs:anyURI" und "System.Uri"  
 Wenn einer Instanz von `xs:anyURI`, die einen relativen URI darstellt, ein <xref:System.Uri> zugeordnet wird, hat das <xref:System.Uri>-Objekt keinen Basis-URI.  
  
## <a name="see-also"></a>Siehe auch

- [Type Support in the System.Xml Classes (Typenunterstützung in den System.Xml-Klassen)](type-support-in-the-system-xml-classes.md)
