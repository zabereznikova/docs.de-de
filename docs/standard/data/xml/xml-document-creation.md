---
title: Erstellen eines XML-Dokuments
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
ms.openlocfilehash: a12555a02b45a964ff7efcbe00e0d2cb8637474a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709984"
---
# <a name="xml-document-creation"></a>Erstellen eines XML-Dokuments
Es gibt zwei Möglichkeiten, ein XML-Dokument zu erstellen. Eine besteht darin, ein **XmlDocument** ohne Parameter zu erstellen. Die andere Möglichkeit besteht darin, ein **XmlDocument** zu erstellen und ihm eine XmlNameTable als Parameter zu übergeben. Das folgende Beispiel zeigt, wie Sie ein neues, leeres **XmlDocument** ohne Parameter erstellen.  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 Nachdem Sie ein Dokument erstellt haben, können Sie es mithilfe der **Load**-Methode mit Daten aus einer Zeichenfolge, einem Datenstream, einer URL, einem Textreader oder einer abgeleiteten Klasse von **XmlReader** füllen. Eine weitere Lademethode, die **LoadXML**-Methode, liest XML aus einer Zeichenfolge ein. Weitere Informationen zu den verschiedenen **Load**-Methoden finden Sie unter [Einlesen eines XML-Dokuments in das Dokumentobjektmodell](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).  
  
 Es gibt eine Klasse mit dem Namen **XmlNameTable**. Sie besteht aus einer Tabelle mit atomisierten Zeichenfolgenobjekten. Diese Tabelle ist ein effizientes Instrument, mit dem der XML-Parser das gleiche Zeichenfolgenobjekt für alle wiederkehrenden Element- und Attributnamen in einem XML-Dokument verwenden kann. Eine **XmlNameTable** wird automatisch generiert, wenn ein Dokument wie oben beschrieben erstellt wird, und wird mit Attribut- und Elementnamen gefüllt, wenn das Dokument geladen wird. Wenn bereits ein Dokument mit einer Namenstabelle vorhanden ist und diese Namen in einem anderen Dokument nützlich wären, können Sie mit der **Load**-Methode ein neues Dokument erstellen, das eine **XmlNameTable** als Parameter verwendet. Wenn das Dokument mit dieser Methode erstellt wird, wird die bestehende **XmlNameTable** mit allen bereits aus dem anderen Dokument geladenen Attributen und Elementen verwendet. Dies dient zum effizienten Vergleichen von Element- und Attributnamen. Weitere Informationen zu **XmlNameTable** finden Sie unter [Objektvergleich mit „XmlNameTable“](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md). Weitere Informationen finden Sie unter <xref:System.Xml.XmlNameTable>.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
