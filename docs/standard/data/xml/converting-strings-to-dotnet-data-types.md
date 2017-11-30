---
title: "Konvertieren von Zeichenfolgen in .NET Framework-Datentypen"
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
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce594234e601cd8feb4723bbc383db9e3ed40522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="converting-strings-to-net-framework-data-types"></a>Konvertieren von Zeichenfolgen in .NET Framework-Datentypen
Wenn Sie eine Zeichenfolge in einen .NET Framework-Datentyp konvertieren möchten, verwenden Sie die **XmlConvert** Methode, die den Anforderungen der Anwendung entspricht. Eine Liste aller Konvertierung Methoden zur Verfügung, in der **XmlConvert** Klasse, finden Sie unter <xref:System.Xml.XmlConvert>.  
  
 Die Zeichenfolge zurückgegeben, die von der **ToString** Methode ist eine Zeichenfolgenversion der Daten, die übergeben werden. Darüber hinaus stehen mehrere .NET Framework-Typen, die konvertieren Sie mithilfe der **XmlConvert** -Klasse noch keine Methoden verwendet wird die **System.Convert** Klasse. Die **XmlConvert** Klasse folgt die Datentypspezifikation für XML-Schema (XSD) und weist einen Datentyp der **XmlConvert** zuordnen können.  
  
 Die folgende Tabelle enthält die .NET Framework-Datentypen und die Zeichenfolgentypen, die unter Verwendung der XSD-Datentypzuordnung (XML Schema) zurückgegeben werden. Diese .NET Framework-Typen können nicht verarbeitet werden, mithilfe von **System.Convert**.  
  
|.NET Framework-Typ|Zurückgegebene Zeichenfolge|  
|-------------------------|---------------------|  
|Boolean|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|Das Format ist "jjjj-mm-ddTHH:mm:sszzzzzz" und die entsprechenden Unterteilungen.|  
|Timespan|Das Format lautet "PnYnMnTnHnMnS". Die bedeutet für `P2Y10M15DT10H30M20S` eine Dauer von 2 Jahren, 10 Monaten, 15 Tagen, 10 Stunden, 30 Minuten und 20 Sekunden.|  
  
> [!NOTE]
>  Wenn in der Tabelle in eine Zeichenfolge mit den .NET Framework-Typen konvertieren aufgeführt werden. die **ToString** -Methode, die zurückgegebene Zeichenfolge ist nicht der Basistyp, sondern den String-Datentyp XML-Schema (XSD).  
  
 Die **"DateTime"** und **Timespan** Werttyp unterscheidet sich insofern ein **"DateTime"** einen Zeitpunkt darstellt, während eine **TimeSpan** Stellt ein Zeitintervall dar. Die **"DateTime"** und **Timespan** Formate werden in der XML-Schema (XSD) Data-Typen-Spezifikation angegeben. Zum Beispiel:  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim [date] As New DateTime(2001, 8, 4)  
writer.WriteElementString("Date", XmlConvert.ToString([date]))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
DateTime date = new DateTime (2001, 08, 04);  
writer.WriteElementString("Date", XmlConvert.ToString(date));  
```  
  
 **Ausgabe**  
  
 `<Date>2001-08-04T00:00:00</Date>`.  
  
 Der folgende Code konvertiert eine ganze Zahl in eine Zeichenfolge:  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim value As Int32 = 200  
writer.WriteElementString("Number", XmlConvert.ToString(value))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
Int32 value = 200;  
writer.WriteElementString("Number", XmlConvert.ToString(value));  
```  
  
 **Ausgabe**  
  
 `<Number>200</Number>`  
  
 Jedoch wenn Sie eine Zeichenfolge zu konvertieren, **booleschen**, **einzelne**, oder **doppelte**, der .NET Framework-Typ, der zurückgegeben wird entspricht nicht der Rückgabetyp, die bei Verwendung der **System.Convert** Klasse.  
  
## <a name="string-to-boolean"></a>Zeichenfolge in Boolean  
 Die folgende Tabelle zeigt, welcher Typ für die angegebenen Eingabezeichenfolgen generiert wird, wenn eine Zeichenfolge zu konvertieren **booleschen** mithilfe der **ToBoolean** Methode.  
  
|Gültiger Eingabeparameter für die Zeichenfolge|.NET Framework-Ausgabetyp|  
|----------------------------------|--------------------------------|  
|"true"|Boolean.True|  
|"1"|Boolean.True|  
|"false"|Boolean.False|  
|"0"|Boolean.False|  
  
 Betrachten Sie beispielsweise den folgenden XML-Code:  
  
 **Eingabe**  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>   
```  
  
 Beide können durch den folgenden Code verstanden werden und **Bvalue** ist **System.Boolean.True**:  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a>String in Single  
 Die folgende Tabelle zeigt, welcher Typ für die angegebenen Eingabezeichenfolgen generiert wird, wenn eine Zeichenfolge zu konvertieren einer **einzelne** mithilfe der **ToSingle** Methode.  
  
|Gültiger Eingabeparameter für die Zeichenfolge|.NET Framework-Ausgabetyp|  
|----------------------------------|--------------------------------|  
|"INF"|Single.PositiveInfinity|  
|"-INF"|Single.NegativeInfinity|  
  
## <a name="string-to-double"></a>String in Double  
 Die folgende Tabelle zeigt, welcher Typ für die angegebenen Eingabezeichenfolgen generiert wird, wenn eine Zeichenfolge zu konvertieren einer **einzelne** mithilfe der **ToDouble** Methode.  
  
|Gültiger Eingabeparameter für die Zeichenfolge|.NET Framework-Ausgabetyp|  
|----------------------------------|--------------------------------|  
|"INF"|Double.PositiveInfinity|  
|"-INF"|Double.NegativeInfinity|  
  
 Der folgende Code schreibt `<Infinity>INF</Infinity>`:  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Konvertierung von XML-Datentypen](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [Konvertieren von .NET Framework-Typen in Zeichenfolgen](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
