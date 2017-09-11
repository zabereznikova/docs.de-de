---
title: Analysieren numerischer Zeichenfolgen in .NET
description: Analysieren numerischer Zeichenfolgen in .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e393430a-731a-49fa-83de-ff7ed52d5704
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 85cd57d33b03f7a2105ee3f770b2f8bcc0a57ee4
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-numeric-strings-in-net"></a><span data-ttu-id="c9b27-104">Analysieren numerischer Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="c9b27-104">Parsing numeric strings in .NET</span></span>

<span data-ttu-id="c9b27-105">Alle numerischen Typen weisen zwei statische Analysemethoden auf, `Parse` und `TryParse`, mit denen Sie die Zeichenfolgendarstellung einer Zahl in einen numerischen Typ konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="c9b27-105">All numeric types have two static parsing methods, `Parse` and `TryParse`, that you can use to convert the string representation of a number into a numeric type.</span></span> <span data-ttu-id="c9b27-106">Mit diesen Methoden können Sie Zeichenfolgen analysieren, die mithilfe der Formatzeichenfolgen erstellt wurden, die unter [Standardformatzeichenfolgen für Zahlen](standard-numeric.md) und [Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric.md) dokumentiert sind.</span><span class="sxs-lookup"><span data-stu-id="c9b27-106">These methods enable you to parse strings that were produced by using the format strings documented in [Standard Numeric Format Strings](standard-numeric.md) and [Custom Numeric Format Strings](custom-numeric.md).</span></span> <span data-ttu-id="c9b27-107">In der Standardeinstellung können die Methoden `Parse` und `TryParse` Zeichenfolgen, die nur Vorkommastellen enthalten, erfolgreich in ganzzahlige Werte konvertieren.</span><span class="sxs-lookup"><span data-stu-id="c9b27-107">By default, the `Parse` and `TryParse` methods can successfully convert strings that contain integral decimal digits only to integer values.</span></span> <span data-ttu-id="c9b27-108">Sie können Zeichenfolgen, die Vor- und Nachkommastellen, Gruppentrennzeichen und ein Dezimaltrennzeichen enthalten, erfolgreich in Gleitkommawerte konvertieren.</span><span class="sxs-lookup"><span data-stu-id="c9b27-108">They can successfully convert strings that contain integral and fractional decimal digits, group separators, and a decimal separator to floating-point values.</span></span> <span data-ttu-id="c9b27-109">Die `Parse`-Methode löst eine Ausnahme aus, wenn der Vorgang einen Fehler verursacht, wohingegen die `TryParse`-Methode `false` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c9b27-109">The `Parse` method throws an exception if the operation fails, whereas the `TryParse` method returns `false`.</span></span>

## <a name="parsing-and-format-providers"></a><span data-ttu-id="c9b27-110">Analyse und Formatanbieter</span><span class="sxs-lookup"><span data-stu-id="c9b27-110">Parsing and format providers</span></span>

<span data-ttu-id="c9b27-111">In der Regel unterscheiden sich die Zeichenfolgendarstellungen numerischer Werte je nach Kultur.</span><span class="sxs-lookup"><span data-stu-id="c9b27-111">Typically, the string representations of numeric values differ by culture.</span></span> <span data-ttu-id="c9b27-112">Elemente numerischer Zeichenfolgen wie Währungssymbole, Gruppentrennzeichen (oder Tausendertrennzeichen) und Dezimaltrennzeichen variieren alle je nach Kultur.</span><span class="sxs-lookup"><span data-stu-id="c9b27-112">Elements of numeric strings such as currency symbols, group (or thousands) separators, and decimal separators all vary by culture.</span></span> <span data-ttu-id="c9b27-113">Analysemethoden verwenden entweder implizit oder explizit einen Formatanbieter, der diese kulturspezifischen Variationen erkennt.</span><span class="sxs-lookup"><span data-stu-id="c9b27-113">Parsing methods either implicitly or explicitly use a format provider that recognizes these culture-specific variations.</span></span> <span data-ttu-id="c9b27-114">Wird in einem Aufruf der `Parse`- oder der `TryParse`-Methode kein Formatanbieter angegeben, so wird der der aktuellen Threadkultur zugeordnete Formatanbieter verwendet (das von der [NumberFormatInfo.CurrentInfo](xref:System.Globalization.NumberFormatInfo.CurrentInfo)-Eigenschaft zurückgegebene [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt).</span><span class="sxs-lookup"><span data-stu-id="c9b27-114">If no format provider is specified in a call to the `Parse` or `TryParse` method, the format provider associated with the current thread culture (the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object returned by the [NumberFormatInfo.CurrentInfo](xref:System.Globalization.NumberFormatInfo.CurrentInfo) property) is used.</span></span> 

<span data-ttu-id="c9b27-115">Ein Formatanbieter wird durch eine [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo)-Implementierung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c9b27-115">A format provider is represented by an [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) implementation.</span></span> <span data-ttu-id="c9b27-116">Diese Schnittstelle verfügt über einen einzelnen Member, die [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Methode, deren einziger Parameter ein [Type](xref:System.Type)-Objekt ist, das den zu formatierenden Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="c9b27-116">This interface has a single member, the [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method, whose single parameter is a [Type](xref:System.Type) object that represents the type to be formatted.</span></span> <span data-ttu-id="c9b27-117">Diese Methode gibt das Objekt mit den Formatierungsinformationen zurück.</span><span class="sxs-lookup"><span data-stu-id="c9b27-117">This method returns the object that provides formatting information.</span></span> <span data-ttu-id="c9b27-118">.NET unterstützt die folgenden beiden [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo)-Implementierungen zur Analyse numerischer Zeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="c9b27-118">.NET supports the following two [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) implementations for parsing numeric strings:</span></span>

* <span data-ttu-id="c9b27-119">Ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, dessen [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type))-Methode ein [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt zurückgibt, das kulturspezifische Formatierungsinformationen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c9b27-119">A [CultureInfo](xref:System.Globalization.CultureInfo) object whose [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns a [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that provides culture-specific formatting information.</span></span>

* <span data-ttu-id="c9b27-120">Ein [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt, dessen [NumberFormatInfo.GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type))-Methode sich selbst zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c9b27-120">A [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object whose [NumberFormatInfo.GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) method returns itself.</span></span>

<span data-ttu-id="c9b27-121">Im folgenden Beispiel wird versucht, jede Zeichenfolge in einem Array in einen [Double](xref:System.Double)-Wert zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="c9b27-121">The following example tries to convert each string in an array to a [Double](xref:System.Double) value.</span></span> <span data-ttu-id="c9b27-122">Zuerst wird versucht, die Zeichenfolge anhand eines Formatanbieters zu analysieren, der die Konventionen der Kultur „Englisch (USA)“ wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="c9b27-122">It first tries to parse the string by using a format provider that reflects the conventions of the English (United States) culture.</span></span> <span data-ttu-id="c9b27-123">Wenn dieser Vorgang eine [FormatException](xref:System.FormatException) auslöst, wird versucht, die Zeichenfolge anhand eines Formatanbieters zu analysieren, der die Konventionen der Kultur „Französisch (Frankreich)“ darstellt.</span><span class="sxs-lookup"><span data-stu-id="c9b27-123">If this operation throws a [FormatException](xref:System.FormatException), it tries to parse the string by using a format provider that reflects the conventions of the French (France) culture.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string[] values = { "1,304.16", "$1,456.78", "1,094", "152", 
                          "123,45 €", "1 304,16", "Ae9f" };
      double number;
      CultureInfo culture = null;

      foreach (string value in values) {
         try {
            culture = CultureInfo.CreateSpecificCulture("en-US");
            number = Double.Parse(value, culture);
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
         }   
         catch (FormatException) {
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value);
            culture = CultureInfo.CreateSpecificCulture("fr-FR");
            try {
               number = Double.Parse(value, culture);
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
            }
            catch (FormatException) {
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value);
            }
         }
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//    en-US: 1,304.16 --> 1304.16
//    
//    en-US: Unable to parse '$1,456.78'.
//    fr-FR: Unable to parse '$1,456.78'.
//    
//    en-US: 1,094 --> 1094
//    
//    en-US: 152 --> 152
//    
//    en-US: Unable to parse '123,45 €'.
//    fr-FR: Unable to parse '123,45 €'.
//    
//    en-US: Unable to parse '1 304,16'.
//    fr-FR: 1 304,16 --> 1304.16
//    
//    en-US: Unable to parse 'Ae9f'.
//    fr-FR: Unable to parse 'Ae9f'.
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim values() As String = { "1,304.16", "$1,456.78", "1,094", "152", 
                                 "123,45 €", "1 304,16", "Ae9f" }
      Dim number As Double
      Dim culture As CultureInfo = Nothing

      For Each value As String In values
         Try
            culture = CultureInfo.CreateSpecificCulture("en-US")
            number = Double.Parse(value, culture)
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
         Catch e As FormatException
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value)
            culture = CultureInfo.CreateSpecificCulture("fr-FR")
            Try
               number = Double.Parse(value, culture)
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
            Catch ex As FormatException
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value)
            End Try
         End Try
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays the following output:
'    en-US: 1,304.16 --> 1304.16
'    
'    en-US: Unable to parse '$1,456.78'.
'    fr-FR: Unable to parse '$1,456.78'.
'    
'    en-US: 1,094 --> 1094
'    
'    en-US: 152 --> 152
'    
'    en-US: Unable to parse '123,45 €'.
'    fr-FR: Unable to parse '123,45 €'.
'    
'    en-US: Unable to parse '1 304,16'.
'    fr-FR: 1 304,16 --> 1304.16
'    
'    en-US: Unable to parse 'Ae9f'.
'    fr-FR: Unable to parse 'Ae9f'.
```

## <a name="parsing-and-numberstyles-values"></a><span data-ttu-id="c9b27-124">Analyse und NumberStyles-Werte</span><span class="sxs-lookup"><span data-stu-id="c9b27-124">Parsing and NumberStyles values</span></span>

<span data-ttu-id="c9b27-125">Die Stilelemente (z.B. Leerzeichen, Gruppentrennzeichen und Dezimaltrennzeichen), die der Analysevorgang verarbeiten kann, werden durch einen [NumberStyles](xref:System.Globalization.NumberStyles)-Enumerationswert definiert.</span><span class="sxs-lookup"><span data-stu-id="c9b27-125">The style elements (such as white space, group separators, and decimal separator) that the parse operation can handle are defined by a [NumberStyles](xref:System.Globalization.NumberStyles) enumeration value.</span></span> <span data-ttu-id="c9b27-126">Standardmäßig werden Zeichenfolgen, die ganzzahlige Werte darstellen, über den [NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer)-Wert analysiert, der nur Ziffern, vorangestellte und nachfolgende Leerzeichen sowie ein Vorzeichen zulässt.</span><span class="sxs-lookup"><span data-stu-id="c9b27-126">By default, strings that represent integer values are parsed by using the [NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer) value, which permits only numeric digits, leading and trailing white space, and a leading sign.</span></span> <span data-ttu-id="c9b27-127">Zeichenfolgen, die Gleitkommawerte darstellen, werden mithilfe einer Kombination der Werte [NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) und [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) analysiert. Dieser zusammengesetzte Stil lässt Dezimalstellen sowie vorangestellte und nachfolgende Leerzeichen, ein Vorzeichen, ein Dezimaltrennzeichen, ein Gruppentrennzeichen und einen Exponenten zu.</span><span class="sxs-lookup"><span data-stu-id="c9b27-127">Strings that represent floating-point values are parsed using a combination of the [NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) and [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) values; this composite style permits decimal digits along with leading and trailing white space, a leading sign, a decimal separator, a group separator, and an exponent.</span></span> <span data-ttu-id="c9b27-128">Durch den Aufruf einer Überladung der `Parse`- oder der `TryParse`-Methode mit einem Parameter vom Typ [NumberStyles](xref:System.Globalization.NumberStyles) und durch Festlegen von [NumberStyles](xref:System.Globalization.NumberStyles)-Flags können Sie die Stilelemente steuern, die in der Zeichenfolge vorhanden sein dürfen, damit der Analysevorgang erfolgreich durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c9b27-128">By calling an overload of the `Parse` or `TryParse` method that includes a parameter of type [NumberStyles](xref:System.Globalization.NumberStyles) and setting one or more [NumberStyles](xref:System.Globalization.NumberStyles) flags, you can control the style elements that can be present in the string for the parse operation to succeed.</span></span> 

<span data-ttu-id="c9b27-129">Beispielsweise kann eine Zeichenfolge, die ein Gruppentrennzeichen enthält, nicht mithilfe der [Int32.Parse(String)](xref:System.Int32.Parse(System.String))-Methode in einen [Int32](xref:System.Int32)-Wert konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="c9b27-129">For example, a string that contains a group separator cannot be converted to an [Int32](xref:System.Int32) value by using the [Int32.Parse(String)](xref:System.Int32.Parse(System.String)) method.</span></span> <span data-ttu-id="c9b27-130">Die Konvertierung ist jedoch erfolgreich, wenn Sie das [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands)-Flag verwenden, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c9b27-130">However, the conversion succeeds if you use the [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) flag, as the following example illustrates.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string value = "1,304";
      int number;
      IFormatProvider provider = CultureInfo.CreateSpecificCulture("en-US");
      if (Int32.TryParse(value, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);

      if (Int32.TryParse(value, NumberStyles.Integer | NumberStyles.AllowThousands, 
                        provider, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);
   }
}
// The example displays the following output:
//       Unable to convert '1,304'
//       1,304 --> 1304
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As String = "1,304"
      Dim number As Integer
      Dim provider As IFormatProvider = CultureInfo.CreateSpecificCulture("en-US")
      If Int32.TryParse(value, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If

      If Int32.TryParse(value, NumberStyles.Integer Or NumberStyles.AllowThousands, 
                        provider, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If
   End Sub
End Module
' The example displays the following output:
'       Unable to convert '1,304'
'       1,304 --> 1304
```

> <span data-ttu-id="c9b27-131">**Warnung**</span><span class="sxs-lookup"><span data-stu-id="c9b27-131">**Warning**</span></span>
>
> <span data-ttu-id="c9b27-132">Beim Analysevorgang werden immer die Formatierungskonventionen einer bestimmten Kultur verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9b27-132">The parse operation always uses the formatting conventions of a particular culture.</span></span> <span data-ttu-id="c9b27-133">Wenn Sie keine Kultur durch Übergabe eines [CultureInfo](xref:System.Globalization.CultureInfo)- oder [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts angeben, wird die dem aktuellen Thread zugeordnete Kultur verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9b27-133">If you do not specify a culture by passing a [CultureInfo](xref:System.Globalization.CultureInfo) or [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object, the culture associated with the current thread is used.</span></span>
 
<span data-ttu-id="c9b27-134">Die folgende Tabelle enthält die Member der [NumberStyles](xref:System.Globalization.NumberStyles)-Enumeration und beschreibt, wie diese sich auf den Analysevorgang auswirken.</span><span class="sxs-lookup"><span data-stu-id="c9b27-134">The following table lists the members of the [NumberStyles](xref:System.Globalization.NumberStyles) enumeration and describes the effect that they have on the parsing operation.</span></span>

<span data-ttu-id="c9b27-135">NumberStyles-Wert</span><span class="sxs-lookup"><span data-stu-id="c9b27-135">NumberStyles value</span></span> | <span data-ttu-id="c9b27-136">Auswirkung auf die zu analysierende Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c9b27-136">Effect on the string to be parsed</span></span>
------------------ | --------------------------------- 
[<span data-ttu-id="c9b27-137">NumberStyles.None</span><span class="sxs-lookup"><span data-stu-id="c9b27-137">NumberStyles.None</span></span>](xref:System.Globalization.NumberStyles.None) | <span data-ttu-id="c9b27-138">Nur Ziffern sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c9b27-138">Only numeric digits are permitted.</span></span>
[<span data-ttu-id="c9b27-139">NumberStyles.AllowDecimalPoint</span><span class="sxs-lookup"><span data-stu-id="c9b27-139">NumberStyles.AllowDecimalPoint</span></span>](xref:System.Globalization.NumberStyles.AllowDecimalPoint) | <span data-ttu-id="c9b27-140">Das Dezimaltrennzeichen und Nachkommastellen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c9b27-140">The decimal separator and fractional digits are permitted.</span></span> <span data-ttu-id="c9b27-141">Für ganzzahlige Werte ist nur&0; (null) als Nachkommastelle zulässig.</span><span class="sxs-lookup"><span data-stu-id="c9b27-141">For integer values, only zero is permitted as a fractional digit.</span></span> <span data-ttu-id="c9b27-142">Gültige Dezimaltrennzeichen werden über die [NumberFormatInfo.NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator)- oder die [NumberFormatInfo.CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator)-Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c9b27-142">Valid decimal separators are determined by the [NumberFormatInfo.NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) or [NumberFormatInfo.CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) property.</span></span>
[<span data-ttu-id="c9b27-143">NumberStyles.AllowExponent</span><span class="sxs-lookup"><span data-stu-id="c9b27-143">NumberStyles.AllowExponent</span></span>](xref:System.Globalization.NumberStyles.AllowExponent) | <span data-ttu-id="c9b27-144">Das Zeichen „e“ oder „E“ kann zum Angeben der Exponentialschreibweise verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9b27-144">The "e" or "E" character can be used to indicate exponential notation.</span></span>
[<span data-ttu-id="c9b27-145">NumberStyles.AllowLeadingWhite</span><span class="sxs-lookup"><span data-stu-id="c9b27-145">NumberStyles.AllowLeadingWhite</span></span>](xref:System.Globalization.NumberStyles.AllowLeadingWhite) | <span data-ttu-id="c9b27-146">Vorangestellte Leerzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c9b27-146">Leading white space is permitted.</span></span>
[<span data-ttu-id="c9b27-147">NumberStyles.AllowTrailingWhite</span><span class="sxs-lookup"><span data-stu-id="c9b27-147">NumberStyles.AllowTrailingWhite</span></span>](xref:System.Globalization.NumberStyles.AllowTrailingWhite) | <span data-ttu-id="c9b27-148">Nachfolgende Leerzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="c9b27-148">Trailing white space is permitted.</span></span>
[<span data-ttu-id="c9b27-149">NumberStyles.AllowLeadingSign</span><span class="sxs-lookup"><span data-stu-id="c9b27-149">NumberStyles.AllowLeadingSign</span></span>](xref:System.Globalization.NumberStyles.AllowLeadingSign) | <span data-ttu-id="c9b27-150">Ein positives oder negatives Vorzeichen kann numerischen Zeichen vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c9b27-150">A positive or negative sign can precede numeric digits.</span></span>
[<span data-ttu-id="c9b27-151">NumberStyles.AllowTrailingSign</span><span class="sxs-lookup"><span data-stu-id="c9b27-151">NumberStyles.AllowTrailingSign</span></span>](xref:System.Globalization.NumberStyles.AllowTrailingSign) | <span data-ttu-id="c9b27-152">Ein positives oder negatives Vorzeichen kann numerischen Zeichen nachfolgen.</span><span class="sxs-lookup"><span data-stu-id="c9b27-152">A positive or negative sign can follow numeric digits.</span></span>
[<span data-ttu-id="c9b27-153">NumberStyles.AllowParentheses</span><span class="sxs-lookup"><span data-stu-id="c9b27-153">NumberStyles.AllowParentheses</span></span>](xref:System.Globalization.NumberStyles.AllowParentheses) | <span data-ttu-id="c9b27-154">Klammern können zum Festlegen negativer Werte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9b27-154">Parentheses can be used to indicate negative values.</span></span>
[<span data-ttu-id="c9b27-155">NumberStyles.AllowThousands</span><span class="sxs-lookup"><span data-stu-id="c9b27-155">NumberStyles.AllowThousands</span></span>](xref:System.Globalization.NumberStyles.AllowThousands) | <span data-ttu-id="c9b27-156">Das Gruppentrennzeichen ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="c9b27-156">The group separator is permitted.</span></span> <span data-ttu-id="c9b27-157">Das Gruppentrennzeichen wird durch die [NumberFormatInfo.NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator)- oder die [NumberFormatInfo.CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator)-Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c9b27-157">The group separator character is determined by the [NumberFormatInfo.NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) or [NumberFormatInfo.CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) property.</span></span>
[<span data-ttu-id="c9b27-158">NumberStyles.AllowCurrencySymbol</span><span class="sxs-lookup"><span data-stu-id="c9b27-158">NumberStyles.AllowCurrencySymbol</span></span>](xref:System.Globalization.NumberStyles.AllowCurrencySymbol) | <span data-ttu-id="c9b27-159">Das Währungssymbol ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="c9b27-159">The currency symbol is permitted.</span></span> <span data-ttu-id="c9b27-160">Das Währungssymbol wird über die [NumberFormatInfo.CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol)-Eigenschaft definiert.</span><span class="sxs-lookup"><span data-stu-id="c9b27-160">The currency symbol is defined by the [NumberFormatInfo.CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) property.</span></span>
[<span data-ttu-id="c9b27-161">NumberStyles.AllowHexSpecifier</span><span class="sxs-lookup"><span data-stu-id="c9b27-161">NumberStyles.AllowHexSpecifier</span></span>](xref:System.Globalization.NumberStyles.AllowHexSpecifier) | <span data-ttu-id="c9b27-162">Die zu analysierende Zeichenfolge wird als Hexadezimalzahl interpretiert.</span><span class="sxs-lookup"><span data-stu-id="c9b27-162">The string to be parsed is interpreted as a hexadecimal number.</span></span> <span data-ttu-id="c9b27-163">Sie kann die Hexadezimalzeichen 0 bis 9, A bis F und a bis f enthalten.</span><span class="sxs-lookup"><span data-stu-id="c9b27-163">It can include the hexadecimal digits 0-9, A-F, and a-f.</span></span> <span data-ttu-id="c9b27-164">Dieses Flag kann nur für die Analyse ganzzahliger Werte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9b27-164">This flag can be used only to parse integer values.</span></span>
 
<span data-ttu-id="c9b27-165">Darüber hinaus stellt die [NumberStyles](xref:System.Globalization.NumberStyles)-Enumeration die folgenden zusammengesetzten Stile bereit, die mehrere [NumberStyles](xref:System.Globalization.NumberStyles)-Flags umfassen.</span><span class="sxs-lookup"><span data-stu-id="c9b27-165">In addition, the [NumberStyles](xref:System.Globalization.NumberStyles) enumeration provides the following composite styles, which include multiple [NumberStyles](xref:System.Globalization.NumberStyles) flags.</span></span> 

<span data-ttu-id="c9b27-166">Zusammengesetzter NumberStyles-Wert</span><span class="sxs-lookup"><span data-stu-id="c9b27-166">Composite NumberStyles value</span></span> | <span data-ttu-id="c9b27-167">Umfasst folgende Member</span><span class="sxs-lookup"><span data-stu-id="c9b27-167">Includes members</span></span>
---------------------------- | ---------------- 
[<span data-ttu-id="c9b27-168">NumberStyles.Integer</span><span class="sxs-lookup"><span data-stu-id="c9b27-168">NumberStyles.Integer</span></span>](xref:System.Globalization.NumberStyles.Integer) | <span data-ttu-id="c9b27-169">Enthält die Stile [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) und [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign).</span><span class="sxs-lookup"><span data-stu-id="c9b27-169">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), and [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign) styles.</span></span> <span data-ttu-id="c9b27-170">Dies ist der Standardstil für die Analyse ganzzahliger Werte.</span><span class="sxs-lookup"><span data-stu-id="c9b27-170">This is the default style used to parse integer values.</span></span>
[<span data-ttu-id="c9b27-171">NumberStyles.Number</span><span class="sxs-lookup"><span data-stu-id="c9b27-171">NumberStyles.Number</span></span>](xref:System.Globalization.NumberStyles.Number) | <span data-ttu-id="c9b27-172">Enthält die Stile [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) und [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands).</span><span class="sxs-lookup"><span data-stu-id="c9b27-172">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint), and [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) styles.</span></span>
[<span data-ttu-id="c9b27-173">NumberStyles.Float</span><span class="sxs-lookup"><span data-stu-id="c9b27-173">NumberStyles.Float</span></span>](xref:System.Globalization.NumberStyles.Float) | <span data-ttu-id="c9b27-174">Enthält die Stile [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) und [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent).</span><span class="sxs-lookup"><span data-stu-id="c9b27-174">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint), and [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) styles.</span></span>
[<span data-ttu-id="c9b27-175">NumberStyles.Currency</span><span class="sxs-lookup"><span data-stu-id="c9b27-175">NumberStyles.Currency</span></span>](xref:System.Globalization.NumberStyles.Currency) | <span data-ttu-id="c9b27-176">Enthält alle Stile mit Ausnahme von [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) und [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span><span class="sxs-lookup"><span data-stu-id="c9b27-176">Includes all styles except [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) and [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span></span>
[<span data-ttu-id="c9b27-177">NumberStyles.Any</span><span class="sxs-lookup"><span data-stu-id="c9b27-177">NumberStyles.Any</span></span>](xref:System.Globalization.NumberStyles.Any) | <span data-ttu-id="c9b27-178">Enthält alle Stile mit Ausnahme von [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span><span class="sxs-lookup"><span data-stu-id="c9b27-178">Includes all styles except [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span></span>
[<span data-ttu-id="c9b27-179">NumberStyles.HexNumber</span><span class="sxs-lookup"><span data-stu-id="c9b27-179">NumberStyles.HexNumber</span></span>](xref:System.Globalization.NumberStyles.HexNumber) | <span data-ttu-id="c9b27-180">Enthält die Stile [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) und [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span><span class="sxs-lookup"><span data-stu-id="c9b27-180">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), and [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier) styles.</span></span>
 
## <a name="parsing-and-unicode-digits"></a><span data-ttu-id="c9b27-181">Analyse und Unicode-Ziffern</span><span class="sxs-lookup"><span data-stu-id="c9b27-181">Parsing and Unicode digits</span></span>

<span data-ttu-id="c9b27-182">Der Unicode-Standard definiert Codepunkte für Ziffern in verschiedenen Schreibsystemen.</span><span class="sxs-lookup"><span data-stu-id="c9b27-182">The Unicode standard defines code points for digits in various writing systems.</span></span> <span data-ttu-id="c9b27-183">Beispielsweise stehen Codepunkte von U+0030 bis U+0039 für die grundlegenden lateinischen Ziffern 0 bis 9, Codepunkte von U+09E6 bis U+09EF für die Bangla-Ziffern 0 bis 9 und Codepunkte von U+FF10 bis U+FF19 für Ziffern voller Breite von 0 bis 9.</span><span class="sxs-lookup"><span data-stu-id="c9b27-183">For example, code points from U+0030 to U+0039 represent the basic Latin digits 0 through 9, code points from U+09E6 to U+09EF represent the Bangla digits 0 through 9, and code points from U+FF10 to U+FF19 represent the Fullwidth digits 0 through 9.</span></span> <span data-ttu-id="c9b27-184">Allerdings werden von den Analysemethoden nur die grundlegenden lateinischen Ziffern von 0 bis 9 mit den Codepunkten von U+0030 bis U+0039 erkannt.</span><span class="sxs-lookup"><span data-stu-id="c9b27-184">However, the only numeric digits recognized by parsing methods are the basic Latin digits 0-9 with code points from U+0030 to U+0039.</span></span> <span data-ttu-id="c9b27-185">Wenn einer numerische Analysemethode eine Zeichenfolge übergeben wird, die andere Ziffern enthält, löst die Methode eine [FormatException](xref:System.FormatException) aus.</span><span class="sxs-lookup"><span data-stu-id="c9b27-185">If a numeric parsing method is passed a string that contains any other digits, the method throws a [FormatException](xref:System.FormatException).</span></span>

<span data-ttu-id="c9b27-186">Im folgenden Beispiel wird die [Int32.Parse](xref:System.Int32.Parse(System.String))-Methode zum Analysieren von Zeichenfolgen verwendet, die aus Ziffern unterschiedlicher Schreibsysteme bestehen.</span><span class="sxs-lookup"><span data-stu-id="c9b27-186">The following example uses the [Int32.Parse](xref:System.Int32.Parse(System.String)) method to parse strings that consist of digits in different writing systems.</span></span> <span data-ttu-id="c9b27-187">Wie die Ausgabe des Beispiels zeigt, verläuft die Analyse der grundlegenden lateinischen Ziffern erfolgreich, aber der Versuch zum Analysieren der vollbreiten, der arabisch-indischen und der Bangla-Ziffern verursacht einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="c9b27-187">As the output from the example shows, the attempt to parse the basic Latin digits succeeds, but the attempt to parse the Fullwidth, Arabic-Indic, and Bangla digits fails.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string value;
      // Define a string of basic Latin digits 1-5.
      value = "\u0031\u0032\u0033\u0034\u0035";
      ParseDigits(value);

      // Define a string of Fullwidth digits 1-5.
      value = "\uFF11\uFF12\uFF13\uFF14\uFF15";
      ParseDigits(value);

      // Define a string of Arabic-Indic digits 1-5.
      value = "\u0661\u0662\u0663\u0664\u0665";
      ParseDigits(value);

      // Define a string of Bangla digits 1-5.
      value = "\u09e7\u09e8\u09e9\u09ea\u09eb";
      ParseDigits(value);
   }

   static void ParseDigits(string value)
   {
      try {
         int number = Int32.Parse(value);
         Console.WriteLine("'{0}' --> {1}", value, number);
      }   
      catch (FormatException) {
         Console.WriteLine("Unable to parse '{0}'.", value);      
      }     
   }
}
// The example displays the following output:
//       '12345' --> 12345
//       Unable to parse '１２３４５'.
//       Unable to parse '١٢٣٤٥'.
//       Unable to parse '১২৩৪৫'.
```

```vb
Module Example
   Public Sub Main()
      Dim value As String
      ' Define a string of basic Latin digits 1-5.
      value = ChrW(&h31) + ChrW(&h32) + ChrW(&h33) + ChrW(&h34) + ChrW(&h35)
      ParseDigits(value)

      ' Define a string of Fullwidth digits 1-5.
      value = ChrW(&hff11) + ChrW(&hff12) + ChrW(&hff13) + ChrW(&hff14) + ChrW(&hff15)
      ParseDigits(value)

      ' Define a string of Arabic-Indic digits 1-5.
      value = ChrW(&h661) + ChrW(&h662) + ChrW(&h663) + ChrW(&h664) + ChrW(&h665)
      ParseDigits(value)

      ' Define a string of Bangla digits 1-5.
      value = ChrW(&h09e7) + ChrW(&h09e8) + ChrW(&h09e9) + ChrW(&h09ea) + ChrW(&h09eb)
      ParseDigits(value)
   End Sub

   Sub ParseDigits(value As String)
      Try
         Dim number As Integer = Int32.Parse(value)
         Console.WriteLine("'{0}' --> {1}", value, number)
      Catch e As FormatException
         Console.WriteLine("Unable to parse '{0}'.", value)      
      End Try     
   End Sub
End Module
' The example displays the following output:
'       '12345' --> 12345
'       Unable to parse '１２３４５'.
'       Unable to parse '١٢٣٤٥'.
'       Unable to parse '১২৩৪৫'.
```

## <a name="see-also"></a><span data-ttu-id="c9b27-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9b27-188">See also</span></span>

[<span data-ttu-id="c9b27-189">System.Globalization.NumberStyles</span><span class="sxs-lookup"><span data-stu-id="c9b27-189">System.Globalization.NumberStyles</span></span>](xref:System.Globalization.NumberStyles)

[<span data-ttu-id="c9b27-190">Analysieren von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="c9b27-190">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="c9b27-191">Formatieren von Typen in .NET</span><span class="sxs-lookup"><span data-stu-id="c9b27-191">Formatting types in .NET</span></span>](formatting-types.md)


