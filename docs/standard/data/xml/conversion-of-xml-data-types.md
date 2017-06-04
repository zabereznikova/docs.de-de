---
title: "Konvertierung von XML-Datentypen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Konvertierung von XML-Datentypen
Mit den meisten Methoden in **XmlConvert**\-Klasse werden Daten zwischen Zeichenfolgen und stark typisierten Formaten konvertiert.  Die Methoden sind unabhängig vom Gebietsschema.  Dies bedeutet, dass im Rahmen von Konvertierungen keine Gebietsschemaeinstellungen berücksichtigt werden.  
  
## Lesen von Zeichenfolgen als Typen  
 Im folgenden Beispiel wird eine Zeichenfolge gelesen und in einen **DateTime**\-Typ konvertiert.  
  
 Die folgenden XML\-Eingaben sind vorhanden:  
  
 **Eingabe**  
  
```  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 Mit diesem Code wird die Zeichenfolge in das **DateTime**\-Format konvertiert:  
  
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
  
## Schreiben von Zeichenfolgen als Typen  
 Im folgenden Beispiel wird ein **Int32**\-Typ gelesen und in eine Zeichenfolge konvertiert.  
  
 Die folgenden XML\-Eingaben sind vorhanden:  
  
 **Eingabe**  
  
```  
<TestInt32>-2147483648</TestInt32>  
```  
  
 Mit diesem Code wird der **Int32**\-Typ in einen **String** konvertiert:  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## Siehe auch  
 [Konvertieren von Zeichenfolgen in .NET Framework\-Datentypen](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)   
 [Konvertieren von .NET Framework\-Typen in Zeichenfolgen](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)