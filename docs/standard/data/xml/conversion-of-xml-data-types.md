---
title: Konvertierung von XML-Datentypen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
ms.openlocfilehash: d7ee7447ab7a8be1bad0d087dba5fc2afaa878e8
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830973"
---
# <a name="conversion-of-xml-data-types"></a>Konvertierung von XML-Datentypen
Mit den meisten Methoden in einer **XmlConvert**-Klasse werden Daten zwischen Zeichenfolgen und stark typisierten Formaten konvertiert. Die Methoden sind unabhängig vom Gebietsschema. Dies bedeutet, dass im Rahmen von Konvertierungen keine Gebietsschemaeinstellungen berücksichtigt werden.  
  
## <a name="reading-string-as-types"></a>Lesen von Zeichenfolgen als Typen  
 Im folgenden Beispiel wird eine Zeichenfolge gelesen und in einen **DateTime**-Typ konvertiert.  
  
 Die folgenden XML-Eingaben sind vorhanden:  
  
 **Eingabe**  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 Mit diesem Code wird die Zeichenfolge in das **DateTime**-Format konvertiert:  
  
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
 Im folgenden Beispiel wird ein **Int32**-Typ gelesen und in eine Zeichenfolge konvertiert.  
  
 Die folgenden XML-Eingaben sind vorhanden:  
  
 **Eingabe**  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 Mit diesem Code wird der **Int32**-Typ in einen **String** konvertiert:  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a>Siehe auch

- [Konvertieren von Zeichenfolgen in .NET Framework-Datentypen](converting-strings-to-dotnet-data-types.md)
- [Konvertieren von .NET Framework-Typen in Zeichenfolgen](converting-dotnet-types-to-strings.md)
