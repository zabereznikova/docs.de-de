---
title: Regeln zum Herleiten einfacher Typen
ms.date: 03/30/2017
ms.assetid: 394624d6-4da0-430a-8a88-46efe40f14de
ms.openlocfilehash: b8fa3037d9ad5af057f477733ffdea74681f5549
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686539"
---
# <a name="rules-for-inferring-simple-types"></a>Regeln zum Herleiten einfacher Typen

Beschreibt das Herleiten der Datentypen für Attribute und Elemente mit der <xref:System.Xml.Schema.XmlSchemaInference>-Klasse.  
  
 Die <xref:System.Xml.Schema.XmlSchemaInference>-Klasse leitet den Datentyp für Attribute und Elemente als einfache Typen her. In diesem Abschnitt werden die möglichen hergeleiteten Typen, das Zusammenführen mehrerer unterschiedlicher Werte zu einem einzelnen Typ und die Behandlung von schemadefinierten `xsi`-Attributen beschrieben.  
  
## <a name="inferred-types"></a>Hergeleitete Typen  

 Die <xref:System.Xml.Schema.XmlSchemaInference>-Klasse leitet Elemente und Attribute als einfache Typen her und fügt im resultierenden Schema einen Attributtyp ein. Bei allen hergeleiteten Typen handelt es sich um einfache Typen. Basistypen oder Facets sind keine Bestandteile des resultierenden Schemas.  
  
 Die Werte werden einzeln, in der Reihenfolge ihres Vorhandenseins im XML-Dokument überprüft. Der Typ für einen Wert wird zum Zeitpunkt der Überprüfung des Werts hergeleitet. Wenn ein Typ für ein Attribut oder ein Element hergeleitet wurde und für das Attribut oder das Element ein Wert festgestellt wird, der nicht mit dem aktuell hergeleiteten Typ übereinstimmt, stuft die <xref:System.Xml.Schema.XmlSchemaInference>-Klasse den Typ für jede Regelgruppe hoch. Diese Regeln werden weiter unten im Abschnitt "Heraufstufen von Typen" erläutert.  
  
 In der folgenden Tabelle werden die für das resultierende Schema möglichen hergeleiteten Typen aufgeführt.  
  
|Einfacher Typ|Beschreibung|  
|-----------------|-----------------|  
|boolean|True, false, 0, 1.|  
|byte|Ganze Zahlen im Bereich von -128 bis 127.|  
|unsignedByte|Ganze Zahlen im Bereich von 0 bis 255.|  
|short|Ganze Zahlen im Bereich von -32768 bis 32767.|  
|unsignedShort|Ganze Zahlen im Bereich von 0 bis 65535.|  
|int|Ganze Zahlen im Bereich von -2147483648 bis 2147483647.|  
|unsignedInt|Ganze Zahlen im Bereich von 0 bis 4294967295.|  
|long|Ganze Zahlen im Bereich von -9223372036854775808 bis 9223372036854775807.|  
|unsignedLong|Ganze Zahlen im Bereich von 0 bis 18446744073709551615.|  
|Ganze Zahl|Eine endliche Anzahl von Ziffern, möglichst mit dem Präfix "-".|  
|decimal|Numerische Werte mit einer Genauigkeit von 0 bis 28 Stellen.|  
|float|Dezimalzahlen, nach denen optional "E" oder "e" folgt, gefolgt von einem Ganzzahlenwert als Exponent. Dezimalwerte können im Bereich von -16777216 bis 16777216 liegen. Exponentenwerte können im Bereich von -149 bis 104 liegen.<br /><br /> Float ermöglicht spezielle Werte, mit denen unendliche und nicht numerische Werte dargestellt werden. Besondere Werte für Float sind 0, -0, INF, -INF, NaN.|  
|double|Die gleichen Werte wie bei float, allerdings können die Dezimalwerte im Bereich von -9007199254740992 bis 9007199254740992 und die Exponentenwerte zwischen –1075 und 970 liegen.<br /><br /> Double ermöglicht spezielle Werte, mit denen unendliche und nicht numerische Werte dargestellt werden. Besondere Werte für Float sind 0, -0, INF, -INF, NaN.|  
|duration|Das W3C-Format für duration.|  
|dateTime|Das W3C-Format für dateTime.|  
|Uhrzeit|Das W3C-Format für time.|  
|date|Die Werte für Jahreszahlen sind auf einen Bereich von 0001 bis 9999 beschränkt.|  
|gYearMonth|Das gregorianische Monats- und Zeitformat von W3C.|  
|string|Ein oder mehrere Unicode-Zeichen.|  
  
## <a name="type-promotion"></a>Typerweiterung  

 Die <xref:System.Xml.Schema.XmlSchemaInference>-Klasse überprüft Attribut- und Elementwerte der Reihenfolge nach. Wenn Werte festgestellt werden, wird der am weitesten eingeschränkte Typ ohne Vorzeichen hergeleitet. Wenn für ein Attribut oder ein Element ein Typ hergeleitet wurde und einer neuer Wert festgestellt wird, der nicht mit dem aktuell hergeleiteten Typ übereinstimmt, wird der hergeleitete Typ auf einen neuen Typ heraufgestuft. Dieser Typ entspricht sowohl dem aktuell hergeleiteten Typ als auch dem neuen Wert. Die <xref:System.Xml.Schema.XmlSchemaInference>-Klasse berücksichtigt beim Heraufstufen hergeleiteter Typen vorherige Werte.  
  
 Betrachten Sie beispielsweise die folgenden XML-Ausschnitte aus zwei XML-Dokumenten:  
  
 `<MyElement1 attr1="12" />`  
  
 `<MyElement1 attr1="52344" />`  
  
 Wenn der erste `attr1`-Wert festgestellt wird, wird der Typ von `attr1` auf der Grundlage des Werts `unsignedByte` als `12` hergeleitet. Wenn der zweite `attr1`-Wert festgestellt wird, wird der Typ auf der Grundlage des aktuell hergeleiteten Typs `unsignedShort` und des aktuellen Werts `unsignedByte` auf `52344` heraufgestuft.  
  
 Betrachten Sie nun die folgenden XML-Daten aus zwei XML-Dokumenten:  
  
 `<MyElement2 attr2="0" />`  
  
 `<MyElement2 attr2="true" />`  
  
 Wenn der erste `attr2`-Wert festgestellt wird, wird der Typ von `attr2` auf der Grundlage des Werts `unsignedByte` als `0` hergeleitet. Wenn der zweite `attr2`-Wert festgestellt wird, wird der Typ auf der Grundlage des aktuell hergeleiteten Typs `string` und des aktuellen Werts `unsignedByte` auf `true` heraufgestuft, da die <xref:System.Xml.Schema.XmlSchemaInference>-Klasse beim Heraufstufen des hergeleiteten Typs vorherige Werte berücksichtigt. Wenn jedoch beide Instanzen von `attr2` im selben XML-Dokument und nicht, wie im Beispiel oben dargestellt, in zwei unterschiedlichen Dokumenten festgestellt worden wären, wäre `attr2` als `boolean` hergeleitet worden.  
  
### <a name="ignored-attributes-from-the-httpswwww3org2001xmlschema-instance-namespace"></a>Vom <https://www.w3.org/2001/XMLSchema-instance>-Namespace ignorierte Attribute

Bei den folgenden Attributen handelt es sich um schemadefinierte Attribute, die während der Schemaherleitung ignoriert werden.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`xsi:type`|Wenn ein Element mit der Angabe `xsi:type` festgestellt wird, wird `xsi:type` ignoriert.|  
|`xsi:nil`|Wenn ein Element mit einem `xsi:nil`-Attribut festgestellt wird, weist dessen Elementdeklaration im hergeleiteten Schema den Wert `nillable="true"` auf. Ein Element, dessen `xsi:nil`-Attribut auf `true` festgelegt wurde, darf keine untergeordneten Elemente besitzen.|  
|`xsi:schemaLocation`|Wenn `xsi:schemaLocation` festgestellt wird, wird dies ignoriert.|  
|`xsi:noNamespaceSchemaLocation`|Wenn `xsi:noNamespaceSchemaLocation` festgestellt wird, wird dies ignoriert.|  
  
## <a name="see-also"></a>Siehe auch

- [XML Schema Object Model (SOM) (XML-Schemaobjektmodell (SOM))](xml-schema-object-model-som.md)
- [Herleiten von Schemas aus XML-Dokumenten](inferring-schemas-from-xml-documents.md)
- [Regeln für Rückschlussschemaknotentypen und Struktur](rules-for-inferring-schema-node-types-and-structure.md)
