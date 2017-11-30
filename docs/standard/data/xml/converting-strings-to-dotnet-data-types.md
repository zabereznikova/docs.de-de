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
# <a name="converting-strings-to-net-framework-data-types"></a><span data-ttu-id="f0184-102">Konvertieren von Zeichenfolgen in .NET Framework-Datentypen</span><span class="sxs-lookup"><span data-stu-id="f0184-102">Converting Strings to .NET Framework Data Types</span></span>
<span data-ttu-id="f0184-103">Wenn Sie eine Zeichenfolge in einen .NET Framework-Datentyp konvertieren möchten, verwenden Sie die **XmlConvert** Methode, die den Anforderungen der Anwendung entspricht.</span><span class="sxs-lookup"><span data-stu-id="f0184-103">If you want to convert a string to a .NET Framework data type, use the **XmlConvert** method that fits the application requirements.</span></span> <span data-ttu-id="f0184-104">Eine Liste aller Konvertierung Methoden zur Verfügung, in der **XmlConvert** Klasse, finden Sie unter <xref:System.Xml.XmlConvert>.</span><span class="sxs-lookup"><span data-stu-id="f0184-104">For a list of all conversion methods available in the **XmlConvert** class, see <xref:System.Xml.XmlConvert>.</span></span>  
  
 <span data-ttu-id="f0184-105">Die Zeichenfolge zurückgegeben, die von der **ToString** Methode ist eine Zeichenfolgenversion der Daten, die übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="f0184-105">The string returned from the **ToString** method is a string version of the data that is passed in.</span></span> <span data-ttu-id="f0184-106">Darüber hinaus stehen mehrere .NET Framework-Typen, die konvertieren Sie mithilfe der **XmlConvert** -Klasse noch keine Methoden verwendet wird die **System.Convert** Klasse.</span><span class="sxs-lookup"><span data-stu-id="f0184-106">Additionally, there are several .NET Framework types that convert using the **XmlConvert** class yet they do not use the methods in the **System.Convert** class.</span></span> <span data-ttu-id="f0184-107">Die **XmlConvert** Klasse folgt die Datentypspezifikation für XML-Schema (XSD) und weist einen Datentyp der **XmlConvert** zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="f0184-107">The **XmlConvert** class follows the XML Schema (XSD) data type specification and has a data type that the **XmlConvert** can map to.</span></span>  
  
 <span data-ttu-id="f0184-108">Die folgende Tabelle enthält die .NET Framework-Datentypen und die Zeichenfolgentypen, die unter Verwendung der XSD-Datentypzuordnung (XML Schema) zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f0184-108">The following table lists .NET Framework data types and the string types that are returned using XML Schema (XSD) data type mapping.</span></span> <span data-ttu-id="f0184-109">Diese .NET Framework-Typen können nicht verarbeitet werden, mithilfe von **System.Convert**.</span><span class="sxs-lookup"><span data-stu-id="f0184-109">These .NET Framework types cannot be processed using **System.Convert**.</span></span>  
  
|<span data-ttu-id="f0184-110">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="f0184-110">.NET Framework type</span></span>|<span data-ttu-id="f0184-111">Zurückgegebene Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f0184-111">String returned</span></span>|  
|-------------------------|---------------------|  
|<span data-ttu-id="f0184-112">Boolean</span><span class="sxs-lookup"><span data-stu-id="f0184-112">Boolean</span></span>|<span data-ttu-id="f0184-113">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="f0184-113">"true", "false"</span></span>|  
|<span data-ttu-id="f0184-114">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="f0184-114">Single.PositiveInfinity</span></span>|<span data-ttu-id="f0184-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="f0184-115">"INF"</span></span>|  
|<span data-ttu-id="f0184-116">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="f0184-116">Single.NegativeInfinity</span></span>|<span data-ttu-id="f0184-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="f0184-117">"-INF"</span></span>|  
|<span data-ttu-id="f0184-118">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="f0184-118">Double.PositiveInfinity</span></span>|<span data-ttu-id="f0184-119">"INF"</span><span class="sxs-lookup"><span data-stu-id="f0184-119">"INF"</span></span>|  
|<span data-ttu-id="f0184-120">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="f0184-120">Double.NegativeInfinity</span></span>|<span data-ttu-id="f0184-121">"-INF"</span><span class="sxs-lookup"><span data-stu-id="f0184-121">"-INF"</span></span>|  
|<span data-ttu-id="f0184-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="f0184-122">DateTime</span></span>|<span data-ttu-id="f0184-123">Das Format ist "jjjj-mm-ddTHH:mm:sszzzzzz" und die entsprechenden Unterteilungen.</span><span class="sxs-lookup"><span data-stu-id="f0184-123">Format is "yyyy-MM-ddTHH:mm:sszzzzzz" and its subsets.</span></span>|  
|<span data-ttu-id="f0184-124">Timespan</span><span class="sxs-lookup"><span data-stu-id="f0184-124">Timespan</span></span>|<span data-ttu-id="f0184-125">Das Format lautet "PnYnMnTnHnMnS". Die bedeutet für `P2Y10M15DT10H30M20S` eine Dauer von 2 Jahren, 10 Monaten, 15 Tagen, 10 Stunden, 30 Minuten und 20 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="f0184-125">Format is PnYnMnTnHnMnS that is, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10 hours, 30 minutes, and 20 seconds.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="f0184-126">Wenn in der Tabelle in eine Zeichenfolge mit den .NET Framework-Typen konvertieren aufgeführt werden. die **ToString** -Methode, die zurückgegebene Zeichenfolge ist nicht der Basistyp, sondern den String-Datentyp XML-Schema (XSD).</span><span class="sxs-lookup"><span data-stu-id="f0184-126">If converting any of the .NET Framework types listed in the table to a string using the **ToString** method, the returned string is not the base type, but the XML Schema (XSD) string type.</span></span>  
  
 <span data-ttu-id="f0184-127">Die **"DateTime"** und **Timespan** Werttyp unterscheidet sich insofern ein **"DateTime"** einen Zeitpunkt darstellt, während eine **TimeSpan** Stellt ein Zeitintervall dar.</span><span class="sxs-lookup"><span data-stu-id="f0184-127">The **DateTime** and **Timespan** value type differs in that a **DateTime** represents an instant in time, whereas a **TimeSpan** represents a time interval.</span></span> <span data-ttu-id="f0184-128">Die **"DateTime"** und **Timespan** Formate werden in der XML-Schema (XSD) Data-Typen-Spezifikation angegeben.</span><span class="sxs-lookup"><span data-stu-id="f0184-128">The **DateTime** and **Timespan** formats are specified in the XML Schema (XSD) data types specification.</span></span> <span data-ttu-id="f0184-129">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f0184-129">For example:</span></span>  
  
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
  
 <span data-ttu-id="f0184-130">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="f0184-130">**Output**</span></span>  
  
 <span data-ttu-id="f0184-131">`<Date>2001-08-04T00:00:00</Date>`.</span><span class="sxs-lookup"><span data-stu-id="f0184-131">`<Date>2001-08-04T00:00:00</Date>`.</span></span>  
  
 <span data-ttu-id="f0184-132">Der folgende Code konvertiert eine ganze Zahl in eine Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="f0184-132">The following code converts an integer to a string:</span></span>  
  
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
  
 <span data-ttu-id="f0184-133">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="f0184-133">**Output**</span></span>  
  
 `<Number>200</Number>`  
  
 <span data-ttu-id="f0184-134">Jedoch wenn Sie eine Zeichenfolge zu konvertieren, **booleschen**, **einzelne**, oder **doppelte**, der .NET Framework-Typ, der zurückgegeben wird entspricht nicht der Rückgabetyp, die bei Verwendung der **System.Convert** Klasse.</span><span class="sxs-lookup"><span data-stu-id="f0184-134">However, if you are converting a string to **Boolean**, **Single**, or **Double**, the .NET Framework type that is returned is not the same as the type returned when using the **System.Convert** class.</span></span>  
  
## <a name="string-to-boolean"></a><span data-ttu-id="f0184-135">Zeichenfolge in Boolean</span><span class="sxs-lookup"><span data-stu-id="f0184-135">String to Boolean</span></span>  
 <span data-ttu-id="f0184-136">Die folgende Tabelle zeigt, welcher Typ für die angegebenen Eingabezeichenfolgen generiert wird, wenn eine Zeichenfolge zu konvertieren **booleschen** mithilfe der **ToBoolean** Methode.</span><span class="sxs-lookup"><span data-stu-id="f0184-136">The following table shows what type is generated for the given input strings, when converting a string to **Boolean** using the **ToBoolean** method.</span></span>  
  
|<span data-ttu-id="f0184-137">Gültiger Eingabeparameter für die Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f0184-137">Valid string input parameter</span></span>|<span data-ttu-id="f0184-138">.NET Framework-Ausgabetyp</span><span class="sxs-lookup"><span data-stu-id="f0184-138">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="f0184-139">"true"</span><span class="sxs-lookup"><span data-stu-id="f0184-139">"true"</span></span>|<span data-ttu-id="f0184-140">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="f0184-140">Boolean.True</span></span>|  
|<span data-ttu-id="f0184-141">"1"</span><span class="sxs-lookup"><span data-stu-id="f0184-141">"1"</span></span>|<span data-ttu-id="f0184-142">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="f0184-142">Boolean.True</span></span>|  
|<span data-ttu-id="f0184-143">"false"</span><span class="sxs-lookup"><span data-stu-id="f0184-143">"false"</span></span>|<span data-ttu-id="f0184-144">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="f0184-144">Boolean.False</span></span>|  
|<span data-ttu-id="f0184-145">"0"</span><span class="sxs-lookup"><span data-stu-id="f0184-145">"0"</span></span>|<span data-ttu-id="f0184-146">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="f0184-146">Boolean.False</span></span>|  
  
 <span data-ttu-id="f0184-147">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="f0184-147">For example, given the following XML:</span></span>  
  
 <span data-ttu-id="f0184-148">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="f0184-148">**Input**</span></span>  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>   
```  
  
 <span data-ttu-id="f0184-149">Beide können durch den folgenden Code verstanden werden und **Bvalue** ist **System.Boolean.True**:</span><span class="sxs-lookup"><span data-stu-id="f0184-149">Both can be understood by the following code, and **bvalue** is **System.Boolean.True**:</span></span>  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a><span data-ttu-id="f0184-150">String in Single</span><span class="sxs-lookup"><span data-stu-id="f0184-150">String to Single</span></span>  
 <span data-ttu-id="f0184-151">Die folgende Tabelle zeigt, welcher Typ für die angegebenen Eingabezeichenfolgen generiert wird, wenn eine Zeichenfolge zu konvertieren einer **einzelne** mithilfe der **ToSingle** Methode.</span><span class="sxs-lookup"><span data-stu-id="f0184-151">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToSingle** method.</span></span>  
  
|<span data-ttu-id="f0184-152">Gültiger Eingabeparameter für die Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f0184-152">Valid string input parameter</span></span>|<span data-ttu-id="f0184-153">.NET Framework-Ausgabetyp</span><span class="sxs-lookup"><span data-stu-id="f0184-153">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="f0184-154">"INF"</span><span class="sxs-lookup"><span data-stu-id="f0184-154">"INF"</span></span>|<span data-ttu-id="f0184-155">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="f0184-155">Single.PositiveInfinity</span></span>|  
|<span data-ttu-id="f0184-156">"-INF"</span><span class="sxs-lookup"><span data-stu-id="f0184-156">"-INF"</span></span>|<span data-ttu-id="f0184-157">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="f0184-157">Single.NegativeInfinity</span></span>|  
  
## <a name="string-to-double"></a><span data-ttu-id="f0184-158">String in Double</span><span class="sxs-lookup"><span data-stu-id="f0184-158">String to Double</span></span>  
 <span data-ttu-id="f0184-159">Die folgende Tabelle zeigt, welcher Typ für die angegebenen Eingabezeichenfolgen generiert wird, wenn eine Zeichenfolge zu konvertieren einer **einzelne** mithilfe der **ToDouble** Methode.</span><span class="sxs-lookup"><span data-stu-id="f0184-159">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToDouble** method.</span></span>  
  
|<span data-ttu-id="f0184-160">Gültiger Eingabeparameter für die Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f0184-160">Valid string input parameter</span></span>|<span data-ttu-id="f0184-161">.NET Framework-Ausgabetyp</span><span class="sxs-lookup"><span data-stu-id="f0184-161">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="f0184-162">"INF"</span><span class="sxs-lookup"><span data-stu-id="f0184-162">"INF"</span></span>|<span data-ttu-id="f0184-163">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="f0184-163">Double.PositiveInfinity</span></span>|  
|<span data-ttu-id="f0184-164">"-INF"</span><span class="sxs-lookup"><span data-stu-id="f0184-164">"-INF"</span></span>|<span data-ttu-id="f0184-165">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="f0184-165">Double.NegativeInfinity</span></span>|  
  
 <span data-ttu-id="f0184-166">Der folgende Code schreibt `<Infinity>INF</Infinity>`:</span><span class="sxs-lookup"><span data-stu-id="f0184-166">The following code writes `<Infinity>INF</Infinity>`:</span></span>  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0184-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0184-167">See Also</span></span>  
 [<span data-ttu-id="f0184-168">Konvertierung von XML-Datentypen</span><span class="sxs-lookup"><span data-stu-id="f0184-168">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="f0184-169">Konvertieren von .NET Framework-Typen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f0184-169">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
