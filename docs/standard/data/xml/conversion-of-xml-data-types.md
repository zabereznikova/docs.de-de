---
title: Konvertierung von XML-Datentypen
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
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d2f5f5d27b3d21ff12f5eea7613e80e73c5b6597
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="conversion-of-xml-data-types"></a>Konvertierung von XML-Datentypen
Der Großteil der Methoden gefunden, eine **XmlConvert** Klasse werden verwendet, um Daten zwischen Zeichenfolgen und stark typisierten Formaten konvertiert. Die Methoden sind unabhängig vom Gebietsschema. Dies bedeutet, dass im Rahmen von Konvertierungen keine Gebietsschemaeinstellungen berücksichtigt werden.  
  
## <a name="reading-string-as-types"></a>Lesen von Zeichenfolgen als Typen  
 Im folgenden Beispiel liest eine Zeichenfolge und konvertiert sie in einem **"DateTime"** Typ.  
  
 Die folgenden XML-Eingaben sind vorhanden:  
  
 **Eingabe**  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 Dieser Code konvertiert die Zeichenfolge, die die **"DateTime"** Format:  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a>Schreiben von Zeichenfolgen als Typen  
 Das folgende Beispiel liest eine **Int32** und in eine Zeichenfolge konvertiert.  
  
 Die folgenden XML-Eingaben sind vorhanden:  
  
 **Eingabe**  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 Dieser Code konvertiert das **Int32** in einem **Zeichenfolge**:  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Konvertieren von Zeichenfolgen in .NET Framework-Datentypen](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [Konvertieren von .NET Framework-Typen in Zeichenfolgen](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
