---
title: Erstellen eines XML-Dokuments
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
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a0806e34cfbf7c8e0b5ba995ca4876b8d10405e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-creation"></a>Erstellen eines XML-Dokuments
Es gibt zwei Möglichkeiten, ein XML-Dokument zu erstellen. Eine Möglichkeit besteht im Erstellen einer **XmlDocument** ohne Parameter. Eine andere Möglichkeit besteht im Erstellen einer **XmlDocument** und ihm eine XmlNameTable als Parameter übergeben. Im folgende Beispiel wird gezeigt, wie ein neues, leeres erstellen **XmlDocument** ohne Parameter.  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 Sobald ein Dokument erstellt wird, können Sie es mit Daten aus einer Zeichenfolge laden Datenstream, einer URL, Text-Reader oder ein **XmlReader** abgeleiteten Klasse von der **laden** Methode. Es gibt auch eine andere Load-Methode, die **LoadXML** -Methode, die XML aus einer Zeichenfolge liest. Weitere Informationen zu den verschiedenen **laden** Methoden, finden Sie unter [Lesen eines XML-Dokuments in das DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).  
  
 Es wird eine Klasse mit dem Namen der **XmlNameTable**. Sie besteht aus einer Tabelle mit atomisierten Zeichenfolgenobjekten. Diese Tabelle ist ein effizientes Instrument, mit dem der XML-Parser das gleiche Zeichenfolgenobjekt für alle wiederkehrenden Element- und Attributnamen in einem XML-Dokument verwenden kann. Ein **XmlNameTable** wird automatisch erstellt, wenn ein Dokument erstellt wird, wie oben dargestellt und wird mit Attribut- und Elementnamen geladen, wenn das Dokument geladen wird. Wenn Sie bereits über ein Dokument mit einer Namenstabelle verfügen und diese Namen in einem anderen Dokument nützlich wären, können Sie erstellen, ein neues Dokument mit der **laden** Methode, eine **XmlNameTable** als Parameter. Wenn das Dokument mit dieser Methode erstellt wird, verwendet die vorhandene **XmlNameTable** mit allen Attributen und Elementen, die bereits geladenen aus dem anderen Dokument. Dies dient zum effizienten Vergleichen von Element- und Attributnamen. Weitere Informationen zu den **XmlNameTable**, finden Sie unter [Objekt Vergleich mit "XmlNameTable"](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md). Weitere Informationen finden Sie <xref:System.Xml.XmlNameTable>.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
