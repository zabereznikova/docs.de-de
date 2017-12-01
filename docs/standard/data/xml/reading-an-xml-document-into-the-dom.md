---
title: Einlesen eines XML-Dokuments in das DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a4fb291f-5630-49ba-a49a-5b66c3b71e49
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b8844705b492574443ff4f37de33ccaf1f5fedd7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="reading-an-xml-document-into-the-dom"></a>Einlesen eines XML-Dokuments in das DOM
XML-Daten werden aus verschiedenen Formaten in den Speicher eingelesen. Dies kann z. B. aus einer Zeichenfolge, einem Datenstream, einer URL, einem Textreader oder einer von <xref:System.Xml.XmlReader> abgeleiteten Klasse erfolgen.  
  
 Die <xref:System.Xml.XmlDocument.Load%2A>-Methode lädt das Dokument in den Speicher. Sie verfügt über überladene Methoden, die Daten aus den unterschiedlichen Formaten einlesen. Eine weitere Methode, die <xref:System.Xml.XmlDocument.LoadXml%2A>-Methode, liest XML aus einer Zeichenfolge ein.  
  
 Die unterschiedlichen <xref:System.Xml.XmlDocument.Load%2A>-Methoden beeinflussen, welche Knoten beim Laden des XML-DOM ( Document Object Model) erstellt werden. In der folgenden Tabelle werden die Unterschiede zwischen einigen <xref:System.Xml.XmlDocument.Load%2A>-Methoden sowie die zugehörigen Themen aufgelistet.  
  
|Betreff|Thema|  
|-------------|-----------|  
|Erstellen von Leerraumknoten|Das zum Laden des DOM verwendete Objekt beeinflusst die Leerraum- und die signifikanten Leerraumknoten, die im DOM erzeugt werden. Weitere Informationen finden Sie unter [signifikanten Leerraum Behandlung von Leerräumen und beim Laden des DOM](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md).|  
|Laden von XML, beginnend an einem bestimmten Knoten, oder Laden des gesamten XML-Dokuments|Mithilfe der <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType> Methodendaten können aus einem bestimmten Knoten in das DOM geladen werden Weitere Informationen finden Sie unter [Daten aus einem Reader laden](../../../../docs/standard/data/xml/load-data-from-a-reader.md).|  
|Validieren des geladenen XML|Die XML-Daten, die in das DOM geladen werden, können beim Laden validiert werden. Dies erfolgt mit dem Validierungs-<xref:System.Xml.XmlReader>. Weitere Informationen zu XML-Validierung, wie es geladen wird, finden Sie unter [Validieren eines XML-Dokuments im DOKUMENTOBJEKTMODELL](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md).|  
  
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
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
