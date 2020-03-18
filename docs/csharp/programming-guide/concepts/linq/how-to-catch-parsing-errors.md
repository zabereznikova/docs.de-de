---
title: 'Vorgehensweise: Auffangen von Parsingfehlern (C#)'
ms.date: 07/20/2015
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
ms.openlocfilehash: 1a05037892061dec85e7837472e8ec13e076724b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141482"
---
# <a name="how-to-catch-parsing-errors-c"></a>Vorgehensweise: Auffangen von Parsingfehlern (C#)
In diesem Thema wird gezeigt, wie nicht wohlgeformter oder ungültiger XML-Code erkannt werden kann.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] wird mithilfe von <xref:System.Xml.XmlReader> implementiert. Wenn nicht wohlgeformter oder ungültiger XML-Code an [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] übergeben wird, löst die zugrunde liegende <xref:System.Xml.XmlReader>-Klasse eine Ausnahme aus. Die verschiedenen Methoden, die XML analysieren, z.B. <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, fangen die Ausnahme nicht ab. Die Ausnahme kann dann von Ihrer Anwendung abgefangen werden.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code versucht, ungültiges XML zu analysieren:  
  
```csharp  
try {  
    XElement contacts = XElement.Parse(  
        @"<Contacts>  
            <Contact>  
                <Name>Jim Wilson</Name>  
            </Contact>  
          </Contcts>");  
  
    Console.WriteLine(contacts);  
}  
catch (System.Xml.XmlException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
 Wenn Sie diesen Code ausführen, wird die folgende Ausnahme ausgelöst:  
  
```console  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 Weitere Informationen zu den Ausnahmen, von denen Sie ausgehen können, dass sie von den Methoden <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> und <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> ausgelöst werden, finden Sie in der <xref:System.Xml.XmlReader>-Dokumentation.  
  