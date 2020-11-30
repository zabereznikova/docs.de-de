---
title: Konvertieren von Zeichenfolgen in .NET-Datentypen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
ms.openlocfilehash: 0cee7481f9c002f860bff7f12b8be0bb763dadb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701470"
---
# <a name="convert-strings-to-net-data-types"></a>Konvertieren von Zeichenfolgen in .NET-Datentypen

Wenn Sie eine Zeichenfolge in einen .NET-Datentyp konvertieren möchten, verwenden Sie die **XmlConvert**-Methode, die den Anwendungsanforderungen entspricht. Eine Liste sämtlicher in der **XmlConvert**-Klasse verfügbarer Konvertierungsmethoden finden Sie unter <xref:System.Xml.XmlConvert>.  
  
 Die von der **ToString**-Methode zurückgegebene Zeichenfolge ist eine Zeichenfolgenversion der Daten, die übergeben werden. Darüber hinaus gibt es mehrere .NET-Typen, die mit der **XmlConvert**-Klasse konvertiert werden können, wobei sie jedoch nicht die Methoden in der **System.Convert**-Klasse verwenden. Die **XmlConvert**-Klasse entspricht der Spezifikation für XSD-Datentypen (XML-Schema) und besitzt einen Datentyp, dem **XmlConvert** zugeordnet werden kann.  
  
 Die folgende Tabelle enthält die .NET-Datentypen und die Zeichenfolgentypen, die unter Verwendung der XSD-Datentypzuordnung (XML Schema) zurückgegeben werden. Diese .NET-Typen können nicht mit **System.Convert** verarbeitet werden.  
  
|.NET-Typ|Zurückgegebene Zeichenfolge|  
|-------------------------|---------------------|  
|Boolesch|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|Das Format ist "jjjj-mm-ddTHH:mm:sszzzzzz" und die entsprechenden Unterteilungen.|  
|Timespan|Das Format lautet "PnYnMnTnHnMnS". Die bedeutet für `P2Y10M15DT10H30M20S` eine Dauer von 2 Jahren, 10 Monaten, 15 Tagen, 10 Stunden, 30 Minuten und 20 Sekunden.|  
  
> [!NOTE]
> Wenn einer der in der Tabelle aufgeführten .NET-Typen mit der **ToString**-Methode in eine Zeichenfolge umgewandelt wird, ist die zurückgegebene Zeichenfolge nicht der Basistyp sondern der dem XML-Schema (XSD) entsprechende Zeichenfolgentyp.  
  
 Der **DateTime**-Werttyp und der **Timespan**-Werttyp unterscheiden sich voneinander in dem Punkt, dass **DateTime** einen Zeitpunkt darstellt, während **TimeSpan** einen Zeitraum angibt. Das **DateTime**- und das **Timespan**-Format werden in der Spezifikation für XSD-Datentypen (XML-Schema) festgelegt. Zum Beispiel:  
  
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
  
 `<Date>2001-08-04T00:00:00</Date>`  
  
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
  
 Wenn Sie jedoch eine Zeichenfolge in einen der Typen **Boolean**, **Single** oder **Double** konvertieren, stimmt der zurückgegebene .NET-Typ nicht mit dem bei Verwendung der **System.Convert**-Klasse zurückgegebenen Typ überein.  
  
## <a name="string-to-boolean"></a>Zeichenfolge in Boolean  

 Die folgende Tabelle zeigt, welcher Typ für die angegebenen Eingabezeichenfolgen generiert wird, wenn eine Zeichenfolge mithilfe der **ToBoolean**-Methode in **Boolean** konvertiert wird.  
  
|Gültiger Eingabeparameter für die Zeichenfolge|.NET-Ausgabetyp|  
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
  
 Beide können vom folgenden Code verarbeitet werden, und **bvalue** ist **System.Boolean.True**:  
  
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

 Die folgende Tabelle zeigt, welcher Typ für die angegebenen Eingabezeichenfolgen generiert wird, wenn eine Zeichenfolge mithilfe der **ToSingle**-Methode in **Single** konvertiert wird.  
  
|Gültiger Eingabeparameter für die Zeichenfolge|.NET-Ausgabetyp|  
|----------------------------------|--------------------------------|  
|"INF"|Single.PositiveInfinity|  
|"-INF"|Single.NegativeInfinity|  
  
## <a name="string-to-double"></a>String in Double  

 Die folgende Tabelle zeigt, welcher Typ für die angegebenen Eingabezeichenfolgen generiert wird, wenn eine Zeichenfolge mithilfe der **ToDouble**-Methode in **Single** konvertiert wird.  
  
|Gültiger Eingabeparameter für die Zeichenfolge|.NET-Ausgabetyp|  
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

- [Konvertierung von XML-Datentypen](conversion-of-xml-data-types.md)
- [Konvertieren von .NET-Typen in Zeichenfolgen](converting-dotnet-types-to-strings.md)
