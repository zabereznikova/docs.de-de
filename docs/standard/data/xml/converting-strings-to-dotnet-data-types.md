---
title: Konvertieren von Zeichenfolgen in .NET-Datentypen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
ms.openlocfilehash: 2eee3ff905473d8fd520929c0fe5abfb5d5c42da
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830960"
---
# <a name="convert-strings-to-net-data-types"></a><span data-ttu-id="7b037-102">Konvertieren von Zeichenfolgen in .NET-Datentypen</span><span class="sxs-lookup"><span data-stu-id="7b037-102">Convert strings to .NET data types</span></span>

<span data-ttu-id="7b037-103">Wenn Sie eine Zeichenfolge in einen .NET-Datentyp konvertieren möchten, verwenden Sie die **XmlConvert**-Methode, die den Anwendungsanforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="7b037-103">If you want to convert a string to a .NET data type, use the **XmlConvert** method that fits the application requirements.</span></span> <span data-ttu-id="7b037-104">Eine Liste sämtlicher in der **XmlConvert**-Klasse verfügbarer Konvertierungsmethoden finden Sie unter <xref:System.Xml.XmlConvert>.</span><span class="sxs-lookup"><span data-stu-id="7b037-104">For a list of all conversion methods available in the **XmlConvert** class, see <xref:System.Xml.XmlConvert>.</span></span>  
  
 <span data-ttu-id="7b037-105">Die von der **ToString**-Methode zurückgegebene Zeichenfolge ist eine Zeichenfolgenversion der Daten, die übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="7b037-105">The string returned from the **ToString** method is a string version of the data that is passed in.</span></span> <span data-ttu-id="7b037-106">Darüber hinaus gibt es mehrere .NET-Typen, die mit der **XmlConvert**-Klasse konvertiert werden können, wobei sie jedoch nicht die Methoden in der **System.Convert**-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b037-106">Additionally, there are several .NET types that convert using the **XmlConvert** class yet they do not use the methods in the **System.Convert** class.</span></span> <span data-ttu-id="7b037-107">Die **XmlConvert**-Klasse entspricht der Spezifikation für XSD-Datentypen (XML-Schema) und besitzt einen Datentyp, dem **XmlConvert** zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7b037-107">The **XmlConvert** class follows the XML Schema (XSD) data type specification and has a data type that the **XmlConvert** can map to.</span></span>  
  
 <span data-ttu-id="7b037-108">Die folgende Tabelle enthält die .NET-Datentypen und die Zeichenfolgentypen, die unter Verwendung der XSD-Datentypzuordnung (XML Schema) zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7b037-108">The following table lists .NET data types and the string types that are returned using XML Schema (XSD) data type mapping.</span></span> <span data-ttu-id="7b037-109">Diese .NET-Typen können nicht mit **System.Convert** verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7b037-109">These .NET types cannot be processed using **System.Convert**.</span></span>  
  
|<span data-ttu-id="7b037-110">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="7b037-110">.NET type</span></span>|<span data-ttu-id="7b037-111">Zurückgegebene Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7b037-111">String returned</span></span>|  
|-------------------------|---------------------|  
|<span data-ttu-id="7b037-112">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7b037-112">Boolean</span></span>|<span data-ttu-id="7b037-113">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="7b037-113">"true", "false"</span></span>|  
|<span data-ttu-id="7b037-114">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="7b037-114">Single.PositiveInfinity</span></span>|<span data-ttu-id="7b037-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="7b037-115">"INF"</span></span>|  
|<span data-ttu-id="7b037-116">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="7b037-116">Single.NegativeInfinity</span></span>|<span data-ttu-id="7b037-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="7b037-117">"-INF"</span></span>|  
|<span data-ttu-id="7b037-118">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="7b037-118">Double.PositiveInfinity</span></span>|<span data-ttu-id="7b037-119">"INF"</span><span class="sxs-lookup"><span data-stu-id="7b037-119">"INF"</span></span>|  
|<span data-ttu-id="7b037-120">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="7b037-120">Double.NegativeInfinity</span></span>|<span data-ttu-id="7b037-121">"-INF"</span><span class="sxs-lookup"><span data-stu-id="7b037-121">"-INF"</span></span>|  
|<span data-ttu-id="7b037-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="7b037-122">DateTime</span></span>|<span data-ttu-id="7b037-123">Das Format ist "jjjj-mm-ddTHH:mm:sszzzzzz" und die entsprechenden Unterteilungen.</span><span class="sxs-lookup"><span data-stu-id="7b037-123">Format is "yyyy-MM-ddTHH:mm:sszzzzzz" and its subsets.</span></span>|  
|<span data-ttu-id="7b037-124">Timespan</span><span class="sxs-lookup"><span data-stu-id="7b037-124">Timespan</span></span>|<span data-ttu-id="7b037-125">Das Format lautet "PnYnMnTnHnMnS". Die bedeutet für `P2Y10M15DT10H30M20S` eine Dauer von 2 Jahren, 10 Monaten, 15 Tagen, 10 Stunden, 30 Minuten und 20 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="7b037-125">Format is PnYnMnTnHnMnS that is, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10 hours, 30 minutes, and 20 seconds.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="7b037-126">Wenn einer der in der Tabelle aufgeführten .NET-Typen mit der **ToString**-Methode in eine Zeichenfolge umgewandelt wird, ist die zurückgegebene Zeichenfolge nicht der Basistyp sondern der dem XML-Schema (XSD) entsprechende Zeichenfolgentyp.</span><span class="sxs-lookup"><span data-stu-id="7b037-126">If converting any of the .NET types listed in the table to a string using the **ToString** method, the returned string is not the base type, but the XML Schema (XSD) string type.</span></span>  
  
 <span data-ttu-id="7b037-127">Der **DateTime**-Werttyp und der **Timespan**-Werttyp unterscheiden sich voneinander in dem Punkt, dass **DateTime** einen Zeitpunkt darstellt, während **TimeSpan** einen Zeitraum angibt.</span><span class="sxs-lookup"><span data-stu-id="7b037-127">The **DateTime** and **Timespan** value type differs in that a **DateTime** represents an instant in time, whereas a **TimeSpan** represents a time interval.</span></span> <span data-ttu-id="7b037-128">Das **DateTime**- und das **Timespan**-Format werden in der Spezifikation für XSD-Datentypen (XML-Schema) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7b037-128">The **DateTime** and **Timespan** formats are specified in the XML Schema (XSD) data types specification.</span></span> <span data-ttu-id="7b037-129">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7b037-129">For example:</span></span>  
  
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
  
 <span data-ttu-id="7b037-130">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="7b037-130">**Output**</span></span>  
  
 <span data-ttu-id="7b037-131">`<Date>2001-08-04T00:00:00</Date>`</span><span class="sxs-lookup"><span data-stu-id="7b037-131">`<Date>2001-08-04T00:00:00</Date>`.</span></span>  
  
 <span data-ttu-id="7b037-132">Der folgende Code konvertiert eine ganze Zahl in eine Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="7b037-132">The following code converts an integer to a string:</span></span>  
  
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
  
 <span data-ttu-id="7b037-133">**Ausgabe**</span><span class="sxs-lookup"><span data-stu-id="7b037-133">**Output**</span></span>  
  
 `<Number>200</Number>`  
  
 <span data-ttu-id="7b037-134">Wenn Sie jedoch eine Zeichenfolge in einen der Typen **Boolean**, **Single** oder **Double** konvertieren, stimmt der zurückgegebene .NET-Typ nicht mit dem bei Verwendung der **System.Convert**-Klasse zurückgegebenen Typ überein.</span><span class="sxs-lookup"><span data-stu-id="7b037-134">However, if you are converting a string to **Boolean**, **Single**, or **Double**, the .NET type that's returned is not the same as the type returned when using the **System.Convert** class.</span></span>  
  
## <a name="string-to-boolean"></a><span data-ttu-id="7b037-135">Zeichenfolge in Boolean</span><span class="sxs-lookup"><span data-stu-id="7b037-135">String to Boolean</span></span>  
 <span data-ttu-id="7b037-136">Die folgende Tabelle zeigt, welcher Typ für die angegebenen Eingabezeichenfolgen generiert wird, wenn eine Zeichenfolge mithilfe der **ToBoolean**-Methode in **Boolean** konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="7b037-136">The following table shows what type is generated for the given input strings, when converting a string to **Boolean** using the **ToBoolean** method.</span></span>  
  
|<span data-ttu-id="7b037-137">Gültiger Eingabeparameter für die Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7b037-137">Valid string input parameter</span></span>|<span data-ttu-id="7b037-138">.NET-Ausgabetyp</span><span class="sxs-lookup"><span data-stu-id="7b037-138">.NET output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="7b037-139">"true"</span><span class="sxs-lookup"><span data-stu-id="7b037-139">"true"</span></span>|<span data-ttu-id="7b037-140">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="7b037-140">Boolean.True</span></span>|  
|<span data-ttu-id="7b037-141">"1"</span><span class="sxs-lookup"><span data-stu-id="7b037-141">"1"</span></span>|<span data-ttu-id="7b037-142">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="7b037-142">Boolean.True</span></span>|  
|<span data-ttu-id="7b037-143">"false"</span><span class="sxs-lookup"><span data-stu-id="7b037-143">"false"</span></span>|<span data-ttu-id="7b037-144">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="7b037-144">Boolean.False</span></span>|  
|<span data-ttu-id="7b037-145">"0"</span><span class="sxs-lookup"><span data-stu-id="7b037-145">"0"</span></span>|<span data-ttu-id="7b037-146">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="7b037-146">Boolean.False</span></span>|  
  
 <span data-ttu-id="7b037-147">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="7b037-147">For example, given the following XML:</span></span>  
  
 <span data-ttu-id="7b037-148">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="7b037-148">**Input**</span></span>  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>
```  
  
 <span data-ttu-id="7b037-149">Beide können vom folgenden Code verarbeitet werden, und **bvalue** ist **System.Boolean.True**:</span><span class="sxs-lookup"><span data-stu-id="7b037-149">Both can be understood by the following code, and **bvalue** is **System.Boolean.True**:</span></span>  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a><span data-ttu-id="7b037-150">String in Single</span><span class="sxs-lookup"><span data-stu-id="7b037-150">String to Single</span></span>  
 <span data-ttu-id="7b037-151">Die folgende Tabelle zeigt, welcher Typ für die angegebenen Eingabezeichenfolgen generiert wird, wenn eine Zeichenfolge mithilfe der **ToSingle**-Methode in **Single** konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="7b037-151">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToSingle** method.</span></span>  
  
|<span data-ttu-id="7b037-152">Gültiger Eingabeparameter für die Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7b037-152">Valid string input parameter</span></span>|<span data-ttu-id="7b037-153">.NET-Ausgabetyp</span><span class="sxs-lookup"><span data-stu-id="7b037-153">.NET output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="7b037-154">"INF"</span><span class="sxs-lookup"><span data-stu-id="7b037-154">"INF"</span></span>|<span data-ttu-id="7b037-155">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="7b037-155">Single.PositiveInfinity</span></span>|  
|<span data-ttu-id="7b037-156">"-INF"</span><span class="sxs-lookup"><span data-stu-id="7b037-156">"-INF"</span></span>|<span data-ttu-id="7b037-157">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="7b037-157">Single.NegativeInfinity</span></span>|  
  
## <a name="string-to-double"></a><span data-ttu-id="7b037-158">String in Double</span><span class="sxs-lookup"><span data-stu-id="7b037-158">String to Double</span></span>  
 <span data-ttu-id="7b037-159">Die folgende Tabelle zeigt, welcher Typ für die angegebenen Eingabezeichenfolgen generiert wird, wenn eine Zeichenfolge mithilfe der **ToDouble**-Methode in **Single** konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="7b037-159">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToDouble** method.</span></span>  
  
|<span data-ttu-id="7b037-160">Gültiger Eingabeparameter für die Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7b037-160">Valid string input parameter</span></span>|<span data-ttu-id="7b037-161">.NET-Ausgabetyp</span><span class="sxs-lookup"><span data-stu-id="7b037-161">.NET output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="7b037-162">"INF"</span><span class="sxs-lookup"><span data-stu-id="7b037-162">"INF"</span></span>|<span data-ttu-id="7b037-163">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="7b037-163">Double.PositiveInfinity</span></span>|  
|<span data-ttu-id="7b037-164">"-INF"</span><span class="sxs-lookup"><span data-stu-id="7b037-164">"-INF"</span></span>|<span data-ttu-id="7b037-165">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="7b037-165">Double.NegativeInfinity</span></span>|  
  
 <span data-ttu-id="7b037-166">Der folgende Code schreibt `<Infinity>INF</Infinity>`:</span><span class="sxs-lookup"><span data-stu-id="7b037-166">The following code writes `<Infinity>INF</Infinity>`:</span></span>  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b037-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b037-167">See also</span></span>

- [<span data-ttu-id="7b037-168">Konvertierung von XML-Datentypen</span><span class="sxs-lookup"><span data-stu-id="7b037-168">Conversion of XML Data Types</span></span>](conversion-of-xml-data-types.md)
- [<span data-ttu-id="7b037-169">Konvertieren von .NET-Typen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="7b037-169">Converting .NET Types to Strings</span></span>](converting-dotnet-types-to-strings.md)
