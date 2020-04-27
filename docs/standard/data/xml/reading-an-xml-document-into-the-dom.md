---
title: Einlesen eines XML-Dokuments in das DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a4fb291f-5630-49ba-a49a-5b66c3b71e49
ms.openlocfilehash: 2e61a9ed1a1ccaa2f9f1543efa1d33c3fcf00061
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130833"
---
# <a name="reading-an-xml-document-into-the-dom"></a>Einlesen eines XML-Dokuments in das DOM
XML-Daten werden aus verschiedenen Formaten in den Speicher eingelesen. Dies kann z. B. aus einer Zeichenfolge, einem Datenstream, einer URL, einem Textreader oder einer von <xref:System.Xml.XmlReader> abgeleiteten Klasse erfolgen.  
  
 Die <xref:System.Xml.XmlDocument.Load%2A>-Methode lädt das Dokument in den Speicher. Sie verfügt über überladene Methoden, die Daten aus den unterschiedlichen Formaten einlesen. Eine weitere Methode, die <xref:System.Xml.XmlDocument.LoadXml%2A>-Methode, liest XML aus einer Zeichenfolge ein.  
  
 Die unterschiedlichen <xref:System.Xml.XmlDocument.Load%2A>-Methoden beeinflussen, welche Knoten beim Laden des XML-DOM ( Document Object Model) erstellt werden. In der folgenden Tabelle werden die Unterschiede zwischen einigen <xref:System.Xml.XmlDocument.Load%2A>-Methoden sowie die zugehörigen Themen aufgelistet.  
  
|Betreff|Thema|  
|-------------|-----------|  
|Erstellen von Leerraumknoten|Das zum Laden des DOM verwendete Objekt beeinflusst die Leerraum- und die signifikanten Leerraumknoten, die im DOM erzeugt werden. Weitere Informationen finden Sie unter [Behandlung von Leerräumen und signifikanten Leerräumen beim Laden des DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).|  
|Laden von XML, beginnend an einem bestimmten Knoten, oder Laden des gesamten XML-Dokuments|Mithilfe der <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType>-Methode können Daten aus einem bestimmten Knoten in das DOM geladen werden. Weitere Informationen finden Sie unter [Laden von Daten aus einem Reader](../../../../docs/standard/data/xml/load-data-from-a-reader.md).|  
|Validieren des geladenen XML|Die XML-Daten, die in das DOM geladen werden, können beim Laden validiert werden. Dies erfolgt mit dem Validierungs-<xref:System.Xml.XmlReader>. Weitere Informationen zum Validieren von XML beim Ladevorgang finden Sie unter [Validieren eines XML-Dokuments im DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md).|  
  
 Im folgenden Beispiel wird veranschaulicht, wie XML mithilfe der <xref:System.Xml.XmlDocument.LoadXml%2A>-Methode geladen wird, und wie die Daten anschließend in der Textdatei `data.xml` gespeichert werden.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.LoadXml(("<book genre='novel' ISBN='1-861001-57-5'>" & _  
                    "<title>Pride And Prejudice</title>" & _  
                    "</book>"))  
        ' Save the document to a file.  
        doc.Save("data.xml")  
    End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    public static void Main()  
    {  
        // Create the XmlDocument.  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5'>" +  
                    "<title>Pride And Prejudice</title>" +  
                    "</book>");  
  
        // Save the document to a file.  
        doc.Save("data.xml");  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
