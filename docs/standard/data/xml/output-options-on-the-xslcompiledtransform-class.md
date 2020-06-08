---
title: Ausgabeoptionen für die XslCompiledTransform-Klasse
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 91ce8cba-386c-411e-bb38-0891a0393c0a
ms.openlocfilehash: e9ffdc1377dbf124f042802279e7e7a275222eff
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288705"
---
# <a name="output-options-on-the-xslcompiledtransform-class"></a>Ausgabeoptionen für die XslCompiledTransform-Klasse
In diesem Thema finden Sie Informationen zu den verfügbaren XSLT-Ausgabeoptionen. Sie können Ausgabeoptionen im Stylesheet oder in der <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode angeben.  
  
## <a name="xsloutput-element"></a>xsl:output-Element  
 Mit dem `xsl:output`-Element werden die Ausgabeoptionen angegeben. Mit dem von der <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode angegebenen Ausgabetyp wird das Verhalten der `xsl:output`-Optionen bestimmt.  
  
 In der folgenden Tabelle wird das Verhalten der einzelnen im `xsl:output`-Element verfügbaren Attribute beschrieben, wenn der Ausgabetyp ein Datenstream oder ein <xref:System.IO.TextWriter> ist.  
  
|Attributname|Verhalten|  
|--------------------|--------------|  
|Methode|Unterstützt.|  
|Version|Ignoriert. Diese Version ist immer 1.0 für XML und 4.0 für HTML.|  
|encoding|Wird bei Ausgabe in einen <xref:System.IO.TextWriter> ignoriert. Stattdessen wird die <xref:System.IO.TextWriter.Encoding%2A?displayProperty=nameWithType>-Eigenschaft verwendet.|  
|omit-xml-declaration|Unterstützt.|  
|Eigenständig|Unterstützt.|  
|doctype-public|Unterstützt.|  
|doctype-system|Unterstützt.|  
|cdata-section-elements|Unterstützt.|  
|indent|Unterstützt.|  
|media-type|Unterstützt.|  
  
#### <a name="sending-output-to-an-xmlwriter"></a>Senden der Ausgabe an einen XmlWriter  
 Wenn das Stylesheet das `xsl:output`-Element verwendet und der Ausgabetyp ein <xref:System.Xml.XmlWriter>-Objekt ist, müssen Sie zum Erstellen des <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=nameWithType>-Objekts die <xref:System.Xml.XmlWriter>-Eigenschaft verwenden. Die <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=nameWithType>-Eigenschaft gibt ein <xref:System.Xml.XmlWriterSettings>-Objekt mit Informationen zurück, die aus dem `xsl:output`-Element eines kompilierten Stylesheets abgeleitet wurden. Dieses <xref:System.Xml.XmlWriterSettings>-Objekt kann an die <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType>-Methode übergeben werden, um ein <xref:System.Xml.XmlWriter>-Objekt mit den ordnungsgemäßen Einstellungen zu erstellen.  
  
## <a name="output-types"></a>Ausgabetypen  
 In der folgenden Liste sind die über den <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Befehl verfügbaren Ausgabetypen beschrieben.  
  
#### <a name="xmlwriter"></a>XmlWriter  
 Die <xref:System.Xml.XmlWriter>-Klasse schreibt XML-Datenströme oder XML-Dateien aus. Sie können die Funktionen angegeben, die vom <xref:System.Xml.XmlWriter>-Objekt unterstützt werden sollen, einschließlich der Ausgabeoptionen, indem Sie die <xref:System.Xml.XmlWriterSettings>-Klasse verwenden. Die <xref:System.Xml.XmlWriter>-Klasse ist ein integraler Bestandteil des <xref:System.Xml>-Framework. Verwenden Sie diesen Ausgabetyp, um Ausgabeergebnisse in einen anderen XML-Prozess weiterzuleiten.  
  
#### <a name="string"></a>Zeichenfolge  
 Verwenden Sie diesen Ausgabetyp, um den URI der Ausgabedatei anzugeben.  
  
#### <a name="stream"></a>Stream  
 Ein Stream (Datenstream) ist eine Abstraktion einer Folge von Bytes, beispielsweise eine Datei, ein Eingabe-/Ausgabegerät, eine Pipe für die Kommunikation zwischen Prozessen oder ein TCP/IP-Socket. Die <xref:System.IO.Stream>-Klasse und die davon abgeleiteten Klassen stellen eine allgemeine Ansicht dieser unterschiedlichen Eingabe- und Ausgabetypen bereit, sodass Programmierer sich nicht mit den Einzelheiten des Betriebssystems und der zugrunde liegenden Geräte befassen müssen.  
  
 Verwenden Sie diesen Ausgabetyp, um Daten an einen <xref:System.IO.FileStream>, einen <xref:System.IO.MemoryStream> oder einen Ausgabedatenstream (`Response.OutputStream`) zu senden.  
  
#### <a name="textwriter"></a>TextWriter  
 Der <xref:System.IO.TextWriter> schreibt sequenzielle Zeichen. Er ist in der <xref:System.IO.StringWriter>-Klasse und der <xref:System.IO.StreamWriter>-Klasse implementiert, die Zeichen in Zeichenfolgen bzw. in Datenströme schreiben. Verwenden Sie diesen Ausgabetyp, wenn die Ausgabe in eine Zeichenfolge erfolgen soll.  
  
## <a name="notes"></a>Hinweise  
  
- Beim Schreiben leerer Tags wird ein Leerzeichen zwischen das letzte Zeichen des Elementnamens und den umgekehrten Schrägstrich geschrieben, beispielsweise `<myElement />`. Dadurch können die generierten HTML-Seiten in älteren Webbrowsern ordnungsgemäß angezeigt werden.  
  
## <a name="see-also"></a>Siehe auch

- [XSLT Transformations (XSLT-Transformationen)](xslt-transformations.md)
