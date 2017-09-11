---
title: Formatierung von Typen
description: Formatierung von Typen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: cf497639-9f91-45cb-836f-998d1cea2f43
ms.translationtype: Human Translation
ms.sourcegitcommit: b967d8e55347f44a012e4ad8e916440ae228c8ec
ms.openlocfilehash: e9b8ad13a48dd43236769b130d6f8a75b7b023ca
ms.contentlocale: de-de
ms.lasthandoff: 03/10/2017

---

# <a name="formatting-types"></a><span data-ttu-id="ff003-104">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="ff003-104">Formatting types</span></span>

<span data-ttu-id="ff003-105">Bei der Formatierung wird eine Instanz einer Klasse, Struktur oder eines Enumerationswerts in die entsprechende Zeichenfolgendarstellung konvertiert. Die resultierende Zeichenfolge kann dann häufig Benutzern angezeigt oder sie kann deserialisiert werden, um den ursprünglichen Datentyp wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-105">Formatting is the process of converting an instance of a class, structure, or enumeration value to its string representation, often so that the resulting string can be displayed to users or deserialized to restore the original data type.</span></span> <span data-ttu-id="ff003-106">Diese Konvertierung kann eine Reihe von Problemen beinhalten:</span><span class="sxs-lookup"><span data-stu-id="ff003-106">This conversion can pose a number of challenges:</span></span>

* <span data-ttu-id="ff003-107">Die Art, wie diese Werte intern gespeichert werden, spiegelt nicht notwendigerweise die Art wider, wie die Benutzer sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="ff003-107">The way that values are stored internally does not necessarily reflect the way that users want to view them.</span></span> <span data-ttu-id="ff003-108">Eine Telefonnummer könnte beispielsweise wie folgt gespeichert werden: **8009999999**. Dies ist jedoch wenig benutzerfreundlich.</span><span class="sxs-lookup"><span data-stu-id="ff003-108">For example, a telephone number might be stored in the form **8009999999**, which is not user-friendly.</span></span> <span data-ttu-id="ff003-109">Stattdessen sollte die Telefonnummer wie folgt angezeigt werden: **800-999-9999**.</span><span class="sxs-lookup"><span data-stu-id="ff003-109">It should instead be displayed as **800-999-9999**.</span></span> <span data-ttu-id="ff003-110">Ein Beispiel für die Formatierung einer Zahl auf diese Weise finden Sie im Abschnitt [Benutzerdefinierte Formatzeichenfolgen](#custom-format-strings).</span><span class="sxs-lookup"><span data-stu-id="ff003-110">See the [Custom format strings](#custom-format-strings) section for an example that formats a number in this way.</span></span> 

* <span data-ttu-id="ff003-111">Manchmal ist die Konvertierung eines Objekts in seine Zeichenfolgendarstellung nicht intuitiv.</span><span class="sxs-lookup"><span data-stu-id="ff003-111">Sometimes the conversion of an object to its string representation is not intuitive.</span></span> <span data-ttu-id="ff003-112">Beispielsweise ist nicht klar, wie die Zeichenfolgendarstellung eines **Temperature**-Objekts oder eines **Person**-Objekts aussehen sollte.</span><span class="sxs-lookup"><span data-stu-id="ff003-112">For example, it is not clear how the string representation of a **Temperature** object or a **Person** object should appear.</span></span> <span data-ttu-id="ff003-113">Ein Beispiel für die Formatierung eines **Temperature**-Objekts auf verschiedene Weise finden Sie im Abschnitt [Standardformatzeichenfolgen](#standard-format-strings).</span><span class="sxs-lookup"><span data-stu-id="ff003-113">For an example that formats a **Temperature** object in a variety of ways, see the [Standard format strings](#standard-format-strings) section.</span></span>

* <span data-ttu-id="ff003-114">Oft ist für Werte eine kulturabhängige Formatierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ff003-114">Values often require culture-sensitive formatting.</span></span> <span data-ttu-id="ff003-115">In einer Anwendung, die zum Darstellen von Währungswerten Zahlen verwendet, sollten numerische Zeichenfolgen beispielsweise das Währungssymbol der aktuellen Kultur, das Gruppentrennzeichen (in den meisten Kulturen das Tausendertrennzeichen) und das Dezimaltrennzeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="ff003-115">For example, in an application that uses numbers to reflect monetary values, numeric strings should include the current culture’s currency symbol, group separator (which, in most cultures, is the thousands separator), and decimal symbol.</span></span> <span data-ttu-id="ff003-116">Ein Beispiel finden Sie im Abschnitt [Kulturabhängige Formatierung mit Formatanbietern und der IFormatProvider-Schnittstelle](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface).</span><span class="sxs-lookup"><span data-stu-id="ff003-116">For an example, see the [Culture-sensitive formatting with format providers and the IFormatProvider interface](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface) section.</span></span> 

* <span data-ttu-id="ff003-117">Unter Umständen muss ein Wert in einer Anwendung auf unterschiedliche Arten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-117">An application may have to display the same value in different ways.</span></span> <span data-ttu-id="ff003-118">Beispielsweise stellt eine Anwendung einen Enumerationsmember möglicherweise dar, indem eine Zeichenfolgendarstellung des Namens oder des zugrunde liegende Werts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ff003-118">For example, an application may represent an enumeration member by displaying a string representation of its name or by displaying its underlying value.</span></span> <span data-ttu-id="ff003-119">Ein Beispiel für die Formatierung eines Members der [DayOfWeek](xref:System.DayOfWeek)-Enumeration auf unterschiedliche Weise finden Sie im Abschnitt [Standardformatzeichenfolgen](#standard-format-strings).</span><span class="sxs-lookup"><span data-stu-id="ff003-119">For an example that formats a member of the [DayOfWeek](xref:System.DayOfWeek) enumeration in different ways, see the [Standard format strings](#standard-format-strings) section.</span></span>

<span data-ttu-id="ff003-120">.NET bietet eine umfangreiche Formatierungsunterstützung, die es Entwicklern ermöglicht, diese Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ff003-120">.NET provides rich formatting support that enables developers to address these requirements.</span></span> 

> [!NOTE]
> <span data-ttu-id="ff003-121">Durch das Formatieren wird der Wert eines Typs in eine Zeichenfolgendarstellung konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ff003-121">Formatting converts the value of a type into a string representation.</span></span> <span data-ttu-id="ff003-122">Die Analyse ist die Umkehroperation zum Formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-122">Parsing is the inverse of formatting.</span></span> <span data-ttu-id="ff003-123">In einem Analysevorgang wird eine Instanz eines Datentyps aus seiner Zeichenfolgendarstellung erstellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-123">A parsing operation creates an instance of a data type from its string representation.</span></span> <span data-ttu-id="ff003-124">Informationen zum Konvertieren von Zeichenfolgen in andere Datentypen finden Sie unter [Analysieren von Zeichenfolgen](parsing-strings.md).</span><span class="sxs-lookup"><span data-stu-id="ff003-124">For information about converting strings to other data types, see [Parsing strings](parsing-strings.md).</span></span>

<span data-ttu-id="ff003-125">Diese Übersicht enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="ff003-125">This overview contains the following sections:</span></span>

* [<span data-ttu-id="ff003-126">Formatierung in .NET</span><span class="sxs-lookup"><span data-stu-id="ff003-126">Formatting in .NET</span></span>](#formatting-in-net)

* [<span data-ttu-id="ff003-127">Standardformatierung mit der ToString-Methode</span><span class="sxs-lookup"><span data-stu-id="ff003-127">Default formatting using the ToString method</span></span>](#default-formatting-using-the-tostring-method)

* [<span data-ttu-id="ff003-128">Überschreiben der ToString-Methode</span><span class="sxs-lookup"><span data-stu-id="ff003-128">Overriding the ToString method</span></span>](#overriding-the-tostring-method)

* [<span data-ttu-id="ff003-129">ToString-Methode und Formatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-129">The ToString method and format strings</span></span>](#the-tostring-method-and-format-strings)

    * [<span data-ttu-id="ff003-130">Standardformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-130">Standard format strings</span></span>](#standard-format-strings)
    
    * [<span data-ttu-id="ff003-131">Benutzerdefinierte Formatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-131">Custom format strings</span></span>](#custom-format-strings)
    
    * [<span data-ttu-id="ff003-132">Formatzeichenfolgen und .NET-Typen</span><span class="sxs-lookup"><span data-stu-id="ff003-132">Format strings and .NET types</span></span>](#format-strings-and-net-types)
    
* [<span data-ttu-id="ff003-133">Kulturabhängige Formatierung mit Formatanbietern und der IFormatProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff003-133">Culture-sensitive formatting with format providers and the IFormatProvider interface</span></span>](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface)

    * [<span data-ttu-id="ff003-134">Kulturabhängige Formatierung von numerischen Werten</span><span class="sxs-lookup"><span data-stu-id="ff003-134">Culture-sensitive formatting of numeric values</span></span>](#culture-sensitive-formatting-of-numeric-values)
    
    * [<span data-ttu-id="ff003-135">Kulturabhängige Formatierung von Datums- und Uhrzeitwerten</span><span class="sxs-lookup"><span data-stu-id="ff003-135">Culture-sensitive formatting of date and time values</span></span>](#culture-sensitive-formatting-of-date-and-time-values)
    
* [<span data-ttu-id="ff003-136">IFormattable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff003-136">The IFormattable interface</span></span>](#the-iformattable-interface)

* [<span data-ttu-id="ff003-137">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="ff003-137">Composite formatting</span></span>](#composite-formatting)

* [<span data-ttu-id="ff003-138">Benutzerdefinierte Formatierung mit ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="ff003-138">Custom formatting with ICustomFormatter</span></span>](#custom-formatting-with-icustomformatter)

* [<span data-ttu-id="ff003-139">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ff003-139">Related topics</span></span>](#related-topics)

* [<span data-ttu-id="ff003-140">Referenz</span><span class="sxs-lookup"><span data-stu-id="ff003-140">Reference</span></span>](#reference)

## <a name="formatting-in-net"></a><span data-ttu-id="ff003-141">Formatierung in .NET</span><span class="sxs-lookup"><span data-stu-id="ff003-141">Formatting in .NET</span></span>

<span data-ttu-id="ff003-142">Der grundlegende Mechanismus für die Formatierung ist die Standardimplementierung der [Object.ToString](xref:System.Object.ToString)-Methode, die im Abschnitt [Standardformatierung mit der ToString-Methode](#default-formatting-using-the-tostring-method) weiter unten in diesem Thema erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="ff003-142">The basic mechanism for formatting is the default implementation of the [Object.ToString](xref:System.Object.ToString) method, which is discussed in the [Default formatting using the ToString method](#default-formatting-using-the-tostring-method) section later in this topic.</span></span> <span data-ttu-id="ff003-143">.NET bietet jedoch mehrere Möglichkeiten, die Standardformatierungsunterstützung zu ändern und zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="ff003-143">However, .NET provides several ways to modify and extend its default formatting support.</span></span> <span data-ttu-id="ff003-144">Hierzu gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ff003-144">These include the following:</span></span>

* <span data-ttu-id="ff003-145">Überschreiben der [Object.ToString](xref:System.Object.ToString)-Methode, um eine benutzerdefinierte Zeichenfolgendarstellung des Werts eines Objekts zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-145">Overriding the [Object.ToString](xref:System.Object.ToString) method to define a custom string representation of an object’s value.</span></span> <span data-ttu-id="ff003-146">Weitere Informationen erhalten Sie im Abschnitt [Überschreiben der ToString-Methode](#overriding-the-tostring-method) weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="ff003-146">For more information, see the [Overriding the ToString method](#overriding-the-tostring-method) section later in this topic.</span></span>

* <span data-ttu-id="ff003-147">Definieren von Formatbezeichnern, die es ermöglichen, dass die Zeichenfolgendarstellung des Werts eines Objekts mehrere Formate annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="ff003-147">Defining format specifiers that enable the string representation of an object’s value to take multiple forms.</span></span> <span data-ttu-id="ff003-148">Der Formatbezeichner "X" in der folgenden Anweisung konvertiert beispielsweise eine ganze Zahl in die Zeichenfolgendarstellung eines Hexadezimalwerts.</span><span class="sxs-lookup"><span data-stu-id="ff003-148">For example, the "X" format specifier in the following statement converts an integer to the string representation of a hexadecimal value.</span></span>

  ```csharp
  int integerValue = 60312;
  Console.WriteLine(integerValue.ToString("X"));   // Displays EB98.
  ```

  ```vb
  Dim integerValue As Integer = 60312
  Console.WriteLine(integerValue.ToString("X"))   ' Displays EB98.
  ```
  
  <span data-ttu-id="ff003-149">Weitere Informationen zu Formatbezeichnern finden Sie im Abschnitt [ToString-Methode und Formatzeichenfolgen](#the-tostring-method-and-format-strings).</span><span class="sxs-lookup"><span data-stu-id="ff003-149">For more information about format specifiers, see the [The ToString method and format strings](#the-tostring-method-and-format-strings) section.</span></span>
  
* <span data-ttu-id="ff003-150">Verwenden von Formatanbietern, die Formatierungskonventionen einer bestimmten Kultur nutzen.</span><span class="sxs-lookup"><span data-stu-id="ff003-150">Using format providers to take advantage of the formatting conventions of a specific culture.</span></span> <span data-ttu-id="ff003-151">Beispielsweise zeigt die folgende Anweisung einen Währungswert unter Verwendung der Formatierungskonventionen der Kultur en-US an.</span><span class="sxs-lookup"><span data-stu-id="ff003-151">For example, the following statement displays a currency value by using the formatting conventions of the en-US culture.</span></span> 

  ```csharp
  double cost = 1632.54; 
  Console.WriteLine(cost.ToString("C", 
                  new System.Globalization.CultureInfo("en-US")));   
  // The example displays the following output:
  //       $1,632.54
  ```

  ```vb
  Dim cost As Double = 1632.54
  Console.WriteLine(cost.ToString("C", New System.Globalization.CultureInfo("en-US")))
  ' The example displays the following output:
  '       $1,632.54
  ```
  
  <span data-ttu-id="ff003-152">Weitere Informationen zum Formatieren mit Formatanbietern finden Sie im Abschnitt [Kulturabhängige Formatierung mit Formatanbietern und der IFormatProvider-Schnittstelle](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface).</span><span class="sxs-lookup"><span data-stu-id="ff003-152">For more information about formatting with format providers, see the [Culture-sensitive formatting with format providers and the IFormatProvider interface](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface) section.</span></span>  
  
* <span data-ttu-id="ff003-153">Implementieren der [IFormattable](xref:System.IFormattable)-Schnittstelle zur Unterstützung der Zeichenfolgenkonvertierung mit der [Convert](xref:System.Convert)-Klasse sowie der zusammengesetzten Formatierung.</span><span class="sxs-lookup"><span data-stu-id="ff003-153">Implementing the [IFormattable](xref:System.IFormattable) interface to support both string conversion with the [Convert](xref:System.Convert) class and composite formatting.</span></span> <span data-ttu-id="ff003-154">Weitere Informationen finden Sie im Abschnitt [IFormattable-Schnittstelle](#the-iformattable-interface).</span><span class="sxs-lookup"><span data-stu-id="ff003-154">For more information, see the [The IFormattable interface](#the-iformattable-interface) section.</span></span>

* <span data-ttu-id="ff003-155">Verwenden der kombinierten Formatierung, um die Zeichenfolgendarstellung eines Werts in einer größeren Zeichenfolge einzubetten.</span><span class="sxs-lookup"><span data-stu-id="ff003-155">Using composite formatting to embed the string representation of a value in a larger string.</span></span> <span data-ttu-id="ff003-156">Weitere Informationen finden Sie im Abschnitt [Zusammengesetzte Formatierung](#composite-formatting).</span><span class="sxs-lookup"><span data-stu-id="ff003-156">For more information, see the [Composite formatting](#composite-formatting) section.</span></span>

* <span data-ttu-id="ff003-157">Implementieren von [ICustomFormatter](xref:System.ICustomFormatter) und [IFormatProvider](xref:System.IFormatProvider), um eine vollständige Formatierungslösung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-157">Implementing [ICustomFormatter](xref:System.ICustomFormatter) and [IFormatProvider](xref:System.IFormatProvider) to provide a complete custom formatting solution.</span></span> <span data-ttu-id="ff003-158">Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte Formatierung mit ICustomFormatter](#custom-formatting-with-icustomformatter).</span><span class="sxs-lookup"><span data-stu-id="ff003-158">For more information, see the [Custom formatting with ICustomFormatter](#custom-formatting-with-icustomformatter) section.</span></span>

<span data-ttu-id="ff003-159">In den folgenden Abschnitten werden diese Methoden zum Konvertieren eines Objekts in seine Zeichenfolgendarstellung ausführlicher erläutert.</span><span class="sxs-lookup"><span data-stu-id="ff003-159">The following sections examine these methods for converting an object to its string representation.</span></span>

## <a name="default-formatting-using-the-tostring-method"></a><span data-ttu-id="ff003-160">Standardformatierung mit der ToString-Methode</span><span class="sxs-lookup"><span data-stu-id="ff003-160">Default formatting using the ToString method</span></span>

<span data-ttu-id="ff003-161">Jeder von [System.Object](xref:System.Object) abgeleitete Typ erbt automatisch eine parameterlose [ToString](xref:System.Object.ToString)-Methode, die standardmäßig den Namen des Typs zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ff003-161">Every type that is derived from [System.Object](xref:System.Object) automatically inherits a parameterless [ToString](xref:System.Object.ToString) method, which returns the name of the type by default.</span></span> <span data-ttu-id="ff003-162">Das folgende Beispiel veranschaulicht die [ToString](xref:System.Object.ToString)-Standardmethode.</span><span class="sxs-lookup"><span data-stu-id="ff003-162">The following example illustrates the default [ToString](xref:System.Object.ToString) method.</span></span> <span data-ttu-id="ff003-163">Dabei wird eine Klasse mit dem Namen `Automobile` ohne Implementierung definiert.</span><span class="sxs-lookup"><span data-stu-id="ff003-163">It defines a class named `Automobile` that has no implementation.</span></span> <span data-ttu-id="ff003-164">Wenn die Klasse instanziiert und die zugehörige [ToString](xref:System.Object.ToString)-Methode aufgerufen wird, wird der Typname angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff003-164">When the class is instantiated and its [ToString](xref:System.Object.ToString) method is called, it displays its type name.</span></span> <span data-ttu-id="ff003-165">Beachten Sie, dass die [ToString](xref:System.Object.ToString)-Methode im Beispiel nicht explizit aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ff003-165">Note that the [ToString](xref:System.Object.ToString) method is not explicitly called in the example.</span></span> <span data-ttu-id="ff003-166">Die [Console.WriteLine(Object)](xref:System.Console.WriteLine(System.Object))-Methode ruft implizit die [ToString](xref:System.Object.ToString)-Methode des Objekts auf, das ihr als Argument übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ff003-166">The [Console.WriteLine(Object)](xref:System.Console.WriteLine(System.Object)) method implicitly calls the [ToString](xref:System.Object.ToString) method of the object passed to it as an argument.</span></span> 

```csharp
using System;

public class Automobile
{
   // No implementation. All members are inherited from Object.
}

public class Example
{
   public static void Main()
   {
      Automobile firstAuto = new Automobile();
      Console.WriteLine(firstAuto);
   }
}
// The example displays the following output:
//       Automobile
```

```vb 
Public Class Automobile
   ' No implementation. All members are inherited from Object.
End Class

Module Example
   Public Sub Main()
      Dim firstAuto As New Automobile()
      Console.WriteLine(firstAuto)
   End Sub
End Module
' The example displays the following output:
'       Automobile
```

<span data-ttu-id="ff003-167">Da alle Typen außer Schnittstellen von [Object](xref:System.Object) abgeleitet werden, wird diese Funktionalität automatisch für Ihre benutzerdefinierten Klassen oder Strukturen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-167">Because all types other than interfaces are derived from [Object](xref:System.Object), this functionality is automatically provided to your custom classes or structures.</span></span> <span data-ttu-id="ff003-168">Die Funktionalität der [ToString](xref:System.Object.ToString)-Standardmethode ist jedoch begrenzt: Sie identifiziert zwar den Typ, stellt jedoch keine Informationen zu einer Instanz des Typs bereit.</span><span class="sxs-lookup"><span data-stu-id="ff003-168">However, the functionality offered by the default [ToString](xref:System.Object.ToString) method, is limited: Although it identifies the type, it fails to provide any information about an instance of the type.</span></span> <span data-ttu-id="ff003-169">Um eine Zeichenfolgendarstellung eines Objekts bereitzustellen, die Informationen zum Objekt enthält, müssen Sie die [ToString](xref:System.Object.ToString)-Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="ff003-169">To provide a string representation of an object that provides information about that object, you must override the [ToString](xref:System.Object.ToString) method.</span></span>

> [!NOTE]
> <span data-ttu-id="ff003-170">Strukturen erben vom [ValueType](xref:System.ValueType), der wiederum vom [Object](xref:System.Object) abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="ff003-170">Structures inherit from [ValueType](xref:System.ValueType), which in turn is derived from [Object](xref:System.Object).</span></span> <span data-ttu-id="ff003-171">[ValueType](xref:System.ValueType) überschreibt zwar [Object.ToString](xref:System.Object.ToString), aber die Implementierung ist identisch.</span><span class="sxs-lookup"><span data-stu-id="ff003-171">Although [ValueType](xref:System.ValueType) overrides [Object.ToString](xref:System.Object.ToString), its implementation is identical.</span></span>

## <a name="overriding-the-tostring-method"></a><span data-ttu-id="ff003-172">Überschreiben der ToString-Methode</span><span class="sxs-lookup"><span data-stu-id="ff003-172">Overriding the ToString method</span></span>

<span data-ttu-id="ff003-173">Das Anzeigen des Namens eines Typs ist oft nur von geringem Nutzen und ermöglicht Consumern der Typen keine Unterscheidung zwischen den einzelnen Instanzen.</span><span class="sxs-lookup"><span data-stu-id="ff003-173">Displaying the name of a type is often of limited use and does not allow consumers of your types to differentiate one instance from another.</span></span> <span data-ttu-id="ff003-174">Sie können jedoch die [ToString](xref:System.Object.ToString)-Methode überschreiben, um eine nützlichere Darstellung eines Objektwerts bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-174">However, you can override the [ToString](xref:System.Object.ToString) method to provide a more useful representation of an object’s value.</span></span> <span data-ttu-id="ff003-175">Das folgende Beispiel definiert ein `Temperature`-Objekt und überschreibt die [ToString](xref:System.Object.ToString)-Methode, um die Temperatur in Grad Celsius anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff003-175">The following example defines a `Temperature` object and overrides its [ToString](xref:System.Object.ToString) method to display the temperature in degrees Celsius.</span></span>

```csharp
using System;

public class Temperature
{
   private decimal temp;

   public Temperature(decimal temperature)
   {
      this.temp = temperature;   
   }

   public override string ToString()
   {
      return this.temp.ToString("N1") + "°C";
   }
}

public class Example
{
   public static void Main()
   {
      Temperature currentTemperature = new Temperature(23.6m);
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString());
   }
}
// The example displays the following output:
//       The current temperature is 23.6°C.
```

```vb
Public Class Temperature
   Private temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.temp = temperature
   End Sub

   Public Overrides Function ToString() As String
      Return Me.temp.ToString("N1") + "°C"   
   End Function
End Class

Module Example
   Public Sub Main()
      Dim currentTemperature As New Temperature(23.6d)
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString())
   End Sub
End Module
' The example displays the following output:
'       The current temperature is 23.6°C.
```

<span data-ttu-id="ff003-176">In .NET wurde die [ToString](xref:System.Object.ToString)-Methode jedes primitiven Werttyps überschrieben, um den Wert des Objekts statt seines Namens anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff003-176">In .NET, the [ToString](xref:System.Object.ToString) method of each primitive value type has been overridden to display the object’s value instead of its name.</span></span> <span data-ttu-id="ff003-177">In der folgenden Tabelle wird die Überschreibung für den jeweiligen primitiven Typ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff003-177">The following table shows the override for each primitive type.</span></span> <span data-ttu-id="ff003-178">Beachten Sie, dass die meisten der überschriebenen Methoden eine andere Überladung der [ToString](xref:System.Object.ToString)-Methode aufrufen und dabei den Formatbezeichner „G“ übergeben, der das allgemeine Format des Typs definiert, sowie ein [IFormatProvider](xref:System.IFormatProvider)-Objekt, das die aktuelle Kultur darstellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-178">Note that most of the overridden methods call another overload of the [ToString](xref:System.Object.ToString) method and pass it the "G" format specifier, which defines the general format for its type, and an [IFormatProvider](xref:System.IFormatProvider) object that represents the current culture.</span></span>

<span data-ttu-id="ff003-179">Typ</span><span class="sxs-lookup"><span data-stu-id="ff003-179">Type</span></span> | <span data-ttu-id="ff003-180">ToString-Überschreibung</span><span class="sxs-lookup"><span data-stu-id="ff003-180">ToString override</span></span>
---- | -----------------
[<span data-ttu-id="ff003-181">Boolean</span><span class="sxs-lookup"><span data-stu-id="ff003-181">Boolean</span></span>](xref:System.Boolean) | <span data-ttu-id="ff003-182">Gibt entweder [Boolean.TrueString](xref:System.Boolean.TrueString) oder [Boolean.FalseString](xref:System.Boolean.FalseString) zurück.</span><span class="sxs-lookup"><span data-stu-id="ff003-182">Returns either [Boolean.TrueString](xref:System.Boolean.TrueString) or [Boolean.FalseString](xref:System.Boolean.FalseString).</span></span>
[<span data-ttu-id="ff003-183">Byte</span><span class="sxs-lookup"><span data-stu-id="ff003-183">Byte</span></span>](xref:System.Byte) | <span data-ttu-id="ff003-184">Ruft `Byte.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Byte](xref:System.Byte)-Wert für die aktuelle Kultur zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-184">Calls `Byte.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Byte](xref:System.Byte) value for the current culture.</span></span>
[<span data-ttu-id="ff003-185">Char</span><span class="sxs-lookup"><span data-stu-id="ff003-185">Char</span></span>](xref:System.Char) | <span data-ttu-id="ff003-186">Gibt das Zeichen als Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="ff003-186">Returns the character as a string.</span></span>
[<span data-ttu-id="ff003-187">DateTime</span><span class="sxs-lookup"><span data-stu-id="ff003-187">DateTime</span></span>](xref:System.DateTime) | <span data-ttu-id="ff003-188">Ruft `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)` auf, um den Datums- und Uhrzeitwert für die aktuelle Kultur zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-188">Calls `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)` to format the date and time value for the current culture.</span></span> 
[<span data-ttu-id="ff003-189">Decimal</span><span class="sxs-lookup"><span data-stu-id="ff003-189">Decimal</span></span>](xref:System.Decimal) | <span data-ttu-id="ff003-190">Ruft `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Decimal](xref:System.Decimal)-Wert für die aktuelle Kultur zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-190">Calls `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Decimal](xref:System.Decimal) value for the current culture.</span></span>
[<span data-ttu-id="ff003-191">Double</span><span class="sxs-lookup"><span data-stu-id="ff003-191">Double</span></span>](xref:System.Double) | <span data-ttu-id="ff003-192">Ruft `Double.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Double](xref:System.Double)-Wert für die aktuelle Kultur zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-192">Calls `Double.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Double](xref:System.Double) value for the current culture.</span></span>
[<span data-ttu-id="ff003-193">Int16</span><span class="sxs-lookup"><span data-stu-id="ff003-193">Int16</span></span>](xref:System.Int16) | <span data-ttu-id="ff003-194">Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Int16](xref:System.Int16)-Wert für die aktuelle Kultur zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-194">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int16](xref:System.Int16) value for the current culture.</span></span>
[<span data-ttu-id="ff003-195">Int32</span><span class="sxs-lookup"><span data-stu-id="ff003-195">Int32</span></span>](xref:System.Int32) | <span data-ttu-id="ff003-196">Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Int32](xref:System.Int32)-Wert für die aktuelle Kultur zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-196">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int32](xref:System.Int32) value for the current culture.</span></span>
[<span data-ttu-id="ff003-197">Int64</span><span class="sxs-lookup"><span data-stu-id="ff003-197">Int64</span></span>](xref:System.Int64) | <span data-ttu-id="ff003-198">Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Int64](xref:System.Int64)-Wert für die aktuelle Kultur zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-198">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int64](xref:System.Int64) value for the current culture.</span></span>
[<span data-ttu-id="ff003-199">SByte</span><span class="sxs-lookup"><span data-stu-id="ff003-199">SByte</span></span>](xref:System.SByte) | <span data-ttu-id="ff003-200">Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [SByte](xref:System.SByte)-</span><span class="sxs-lookup"><span data-stu-id="ff003-200">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [SByte](xref:System.SByte)</span></span> | <span data-ttu-id="ff003-201">Wert für die aktuelle Kultur zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-201">value for the current culture.</span></span>
[<span data-ttu-id="ff003-202">Single</span><span class="sxs-lookup"><span data-stu-id="ff003-202">Single</span></span>](xref:System.Single) | <span data-ttu-id="ff003-203">Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [Single](xref:System.Single)-Wert für die aktuelle Kultur zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-203">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Single](xref:System.Single) value for the current culture.</span></span>
[<span data-ttu-id="ff003-204">UInt32</span><span class="sxs-lookup"><span data-stu-id="ff003-204">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="ff003-205">Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [UInt32](xref:System.UInt32)-Wert für die aktuelle Kultur zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-205">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt32](xref:System.UInt32)value for the current culture.</span></span>
[<span data-ttu-id="ff003-206">UInt32</span><span class="sxs-lookup"><span data-stu-id="ff003-206">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="ff003-207">Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [UInt32](xref:System.UInt32)-Wert für die aktuelle Kultur zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-207">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt32](xref:System.UInt32) value for the current culture.</span></span>
[<span data-ttu-id="ff003-208">UInt64</span><span class="sxs-lookup"><span data-stu-id="ff003-208">UInt64</span></span>](xref:System.UInt64) | <span data-ttu-id="ff003-209">Ruft `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` auf, um den [UInt64](xref:System.UInt64)-Wert für die aktuelle Kultur zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-209">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt64](xref:System.UInt64)  value for the current culture.</span></span>

## <a name="the-tostring-method-and-format-strings"></a><span data-ttu-id="ff003-210">ToString-Methode und Formatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-210">The ToString method and format strings</span></span>

<span data-ttu-id="ff003-211">Wenn ein Objekt über eine einzelne Zeichenfolgendarstellung verfügt, ist das Verwenden der [ToString](xref:System.Object.ToString)-Standardmethode oder das Überschreiben von [ToString](xref:System.Object.ToString) angemessen.</span><span class="sxs-lookup"><span data-stu-id="ff003-211">Relying on the default [ToString](xref:System.Object.ToString) method or overriding [ToString](xref:System.Object.ToString) is appropriate when an object has a single string representation.</span></span> <span data-ttu-id="ff003-212">Der Wert eines Objekts weist jedoch häufig mehrere Darstellungen auf.</span><span class="sxs-lookup"><span data-stu-id="ff003-212">However, the value of an object often has multiple representations.</span></span> <span data-ttu-id="ff003-213">Beispielsweise kann die Temperatur in Grad Fahrenheit, Grad Celsius oder Kelvin ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-213">For example, a temperature can be expressed in degrees Fahrenheit, degrees Celsius, or kelvins.</span></span> <span data-ttu-id="ff003-214">Entsprechend kann der ganzzahlige Wert 10 unterschiedlich dargestellt werden, z. B. als 10, 10.0, 1.0e01 oder $10.00.</span><span class="sxs-lookup"><span data-stu-id="ff003-214">Similarly, the integer value 10 can be represented in numerous ways, including 10, 10.0, 1.0e01, or $10.00.</span></span>

<span data-ttu-id="ff003-215">Damit ein einzelner Wert mehrere Zeichenfolgendarstellungen aufweisen kann, verwendet .NET Formatzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="ff003-215">To enable a single value to have multiple string representations, .NET uses format strings.</span></span> <span data-ttu-id="ff003-216">Eine Formatzeichenfolge ist eine Zeichenfolge, die einen oder mehrere vordefinierte Formatbezeichner enthält. Dies sind einzelne Zeichen oder Gruppen von Zeichen, die definieren, wie die [ToString](xref:System.Object.ToString)-Methode die Ausgabe formatieren soll.</span><span class="sxs-lookup"><span data-stu-id="ff003-216">A format string is a string that contains one or more predefined format specifiers, which are single characters or groups of characters that define how the [ToString](xref:System.Object.ToString) method should format its output.</span></span> <span data-ttu-id="ff003-217">Die Formatzeichenfolge wird dann als Parameter an die [ToString](xref:System.Object.ToString)-Methode des Objekts übergeben und bestimmt, wie die Zeichenfolgendarstellung des Werts dieses Objekts angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff003-217">The format string is then passed as a parameter to the object's [ToString](xref:System.Object.ToString) method and determines how the string representation of that object's value should appear.</span></span>

<span data-ttu-id="ff003-218">Alle numerischen Typen sowie die Datums- und Uhrzeittypen und die Enumerationstypen in .NET unterstützen einen vordefinierten Satz von Formatbezeichnern.</span><span class="sxs-lookup"><span data-stu-id="ff003-218">All numeric types, date and time types, and enumeration types in .NET support a predefined set of format specifiers.</span></span> <span data-ttu-id="ff003-219">Sie können auch Formatzeichenfolgen verwenden, um mehrere Zeichenfolgendarstellungen der anwendungsdefinierten Datentypen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-219">You can also use format strings to define multiple string representations of your application-defined data types.</span></span>

### <a name="standard-format-strings"></a><span data-ttu-id="ff003-220">Standardformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-220">Standard format strings</span></span>

<span data-ttu-id="ff003-221">Standardformatzeichenfolgen enthalten einen einzelnen Formatbezeichner. Dabei handelt es sich um ein alphabetisches Zeichen, das die Zeichenfolgendarstellung des Objekts definiert, auf das es angewendet wird. Außerden enthalten sie einen optionalen Genauigkeitsbezeichner, der angibt, wie viele Stellen in der Ergebniszeichenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-221">A standard format string contains a single format specifier, which is an alphabetic character that defines the string representation of the object to which it is applied, along with an optional precision specifier that affects how many digits are displayed in the result string.</span></span> <span data-ttu-id="ff003-222">Wenn der Genauigkeitsbezeichner nicht angegeben oder nicht unterstützt wird, entspricht ein Standardformatbezeichner einer Standardformatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ff003-222">If the precision specifier is omitted or is not supported, a standard format specifier is equivalent to a standard format string.</span></span> 

<span data-ttu-id="ff003-223">.NET definiert einen Satz von Standardformatbezeichnern für alle numerischen Typen, alle Datums- und Uhrzeittypen und alle Enumerationstypen.</span><span class="sxs-lookup"><span data-stu-id="ff003-223">.NET defines a set of standard format specifiers for all numeric types, all date and time types, and all enumeration types.</span></span> <span data-ttu-id="ff003-224">Beispielsweise definieren die einzelnen Kategorien den Standardformatbezeichner "G", der eine allgemeine Zeichenfolgendarstellung für einen Wert dieses Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="ff003-224">For example, each of these categories supports a "G" standard format specifier, which defines a general string representation of a value of that type.</span></span>

<span data-ttu-id="ff003-225">Standardformatzeichenfolgen für Enumerationstypen steuern die Zeichenfolgendarstellung eines Werts direkt.</span><span class="sxs-lookup"><span data-stu-id="ff003-225">Standard format strings for enumeration types directly control the string representation of a value.</span></span> <span data-ttu-id="ff003-226">Die an die [ToString](xref:System.Object.ToString)-Methode eines Enumerationswerts übergebenen Formatzeichenfolgen bestimmen, ob der Wert mit seinem Zeichenfolgennamen (Formatbezeichner „G“ und „F“), seinem zugrunde liegenden ganzzahligen Wert (Formatbezeichner „D“) oder seinem Hexadezimalwert (Formatbezeichner „X“) angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ff003-226">The format strings passed to an enumeration value’s [ToString](xref:System.Object.ToString) method determine whether the value is displayed using its string name (the "G" and "F" format specifiers), its underlying integral value (the "D" format specifier), or its hexadecimal value (the "X" format specifier).</span></span> <span data-ttu-id="ff003-227">Das folgende Beispiel veranschaulicht die Verwendung von Standardformatzeichenfolgen zum Formatieren eines [DayOfWeek](xref:System.DayOfWeek)-Enumerationswerts.</span><span class="sxs-lookup"><span data-stu-id="ff003-227">The following example illustrates the use of standard format strings to format a [DayOfWeek](xref:System.DayOfWeek) enumeration value.</span></span> 

```csharp
DayOfWeek thisDay = DayOfWeek.Monday;
string[] formatStrings = {"G", "F", "D", "X"};

foreach (string formatString in formatStrings)
   Console.WriteLine(thisDay.ToString(formatString));
// The example displays the following output:
//       Monday
//       Monday
//       1
//       00000001
```

```vb
Dim thisDay As DayOfWeek = DayOfWeek.Monday
Dim formatStrings() As String = {"G", "F", "D", "X"}

For Each formatString As String In formatStrings
   Console.WriteLine(thisDay.ToString(formatString))
Next
' The example displays the following output:
'       Monday
'       Monday
'       1
'       00000001
```

<span data-ttu-id="ff003-228">Weitere Informationen über Enumerationsformatzeichenfolgen finden Sie unter [Enumerationsformatzeichenfolgen](enumeration-format.md).</span><span class="sxs-lookup"><span data-stu-id="ff003-228">For information about enumeration format strings, see [Enumeration format strings](enumeration-format.md).</span></span>

<span data-ttu-id="ff003-229">Standardformatzeichenfolgen für numerische Typen definieren normalerweise eine Ergebniszeichenfolge, deren genaue Darstellung von einem oder mehreren Eigenschaftswerten gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="ff003-229">Standard format strings for numeric types usually define a result string whose precise appearance is controlled by one or more property values.</span></span> <span data-ttu-id="ff003-230">Beispielsweise formatiert der Formatbezeichner "C" eine Zahl als Währungswert.</span><span class="sxs-lookup"><span data-stu-id="ff003-230">For example, the "C" format specifier formats a number as a currency value.</span></span> <span data-ttu-id="ff003-231">Wenn Sie die [ToString](xref:System.Object.ToString)-Methode mit dem Formatbezeichner „C“ als einzigem Parameter aufrufen, werden die folgenden Eigenschaftswerte des [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts der aktuellen Kultur verwendet, um die Zeichenfolgendarstellung des numerischen Werts zu definieren:</span><span class="sxs-lookup"><span data-stu-id="ff003-231">When you call the [ToString](xref:System.Object.ToString) method with the "C" format specifier as the only parameter, the following property values from the current culture’s [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object are used to define the string representation of the numeric value:</span></span>

* <span data-ttu-id="ff003-232">Die [CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol)-Eigenschaft, die das Währungssymbol der aktuellen Kultur angibt.</span><span class="sxs-lookup"><span data-stu-id="ff003-232">The [CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) property, which specifies the current culture’s currency symbol.</span></span>

* <span data-ttu-id="ff003-233">Die [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern)- oder [CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern)-Eigenschaft, die eine Ganzzahl zurückgibt, die Folgendes bestimmt:</span><span class="sxs-lookup"><span data-stu-id="ff003-233">The [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) or [CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern) property, which returns an integer that determines the following:</span></span> 

    * <span data-ttu-id="ff003-234">Die Platzierung des Währungssymbols.</span><span class="sxs-lookup"><span data-stu-id="ff003-234">The placement of the currency symbol.</span></span>
    
    * <span data-ttu-id="ff003-235">Ob negative Werte durch ein führendes negatives Vorzeichen, ein nachfolgendes negatives Vorzeichen oder durch Klammern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-235">Whether negative values are indicated by a leading negative sign, a trailing negative sign, or parentheses.</span></span>
    
    * <span data-ttu-id="ff003-236">Ob zwischen dem numerischen Wert und dem Währungssymbol ein Leerzeichen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ff003-236">Whether a space appears between the numeric value and the currency symbol.</span></span>
    
* <span data-ttu-id="ff003-237">Die [CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits)-Eigenschaft, die die Anzahl der Dezimalstellen in der Ergebniszeichenfolge definiert.</span><span class="sxs-lookup"><span data-stu-id="ff003-237">The [CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits) property, which defines the number of fractional digits in the result string.</span></span>

* <span data-ttu-id="ff003-238">Die [CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator)-Eigenschaft, die das Dezimaltrennzeichen in der Ergebniszeichenfolge definiert.</span><span class="sxs-lookup"><span data-stu-id="ff003-238">The [CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) property, which defines the decimal separator symbol in the result string.</span></span>

* <span data-ttu-id="ff003-239">Die [CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator)-Eigenschaft, die das Gruppentrennzeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="ff003-239">The [CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) property, which defines the group separator symbol.</span></span>

* <span data-ttu-id="ff003-240">Die [CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes)-Eigenschaft, die in jeder Gruppe die Anzahl der Stellen links vom Dezimaltrennzeichen definiert.</span><span class="sxs-lookup"><span data-stu-id="ff003-240">The [CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes) property, which defines the number of digits in each group to the left of the decimal.</span></span>

* <span data-ttu-id="ff003-241">Die [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign)-Eigenschaft, die das negative Vorzeichen bestimmt, das in der Ergebniszeichenfolge verwendet wird, wenn negative Werte nicht mit Klammern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-241">The [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) property, which determines the negative sign used in the result string if parentheses are not used to indicate negative values.</span></span>

<span data-ttu-id="ff003-242">Darüber hinaus enthalten numerische Formatzeichenfolgen möglicherweise einen Genauigkeitsbezeichner.</span><span class="sxs-lookup"><span data-stu-id="ff003-242">In addition, numeric format strings may include a precision specifier.</span></span> <span data-ttu-id="ff003-243">Die Bedeutung dieses Bezeichners ist abhängig von der Formatzeichenfolge, mit der er verwendet wird. In aller Regel wird dadurch jedoch entweder die Gesamtzahl der Stellen oder die Anzahl der Dezimalstellen angegeben, die in der Ergebniszeichenfolge erscheinen soll.</span><span class="sxs-lookup"><span data-stu-id="ff003-243">The meaning of this specifier depends on the format string with which it is used, but it typically indicates either the total number of digits or the number of fractional digits that should appear in the result string.</span></span> <span data-ttu-id="ff003-244">So werden im folgenden Beispiel die numerische Standardzeichenfolge "X4" sowie ein Genauigkeitsbezeichner angegeben, um einen Zeichenfolgenwert mit vier Hexadezimalzahlen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-244">For example, the following example uses the "X4" standard numeric string and a precision specifier to create a string value that has four hexadecimal digits.</span></span>

```csharp
byte[] byteValues = { 12, 163, 255 };
foreach (byte byteValue in byteValues)
   Console.WriteLine(byteValue.ToString("X4"));
// The example displays the following output:
//       000C
//       00A3
//       00FF
```

```vb
Dim byteValues() As Byte = { 12, 163, 255 }
For Each byteValue As Byte In byteValues
   Console.WriteLine(byteValue.ToString("X4"))
Next
' The example displays the following output:
'       000C
'       00A3
'       00FF
```

<span data-ttu-id="ff003-245">Weitere Informationen zu Standard-Zahlenformatzeichenfolgen finden Sie unter [Standard-Zahlenformatzeichenfolgen](standard-numeric.md).</span><span class="sxs-lookup"><span data-stu-id="ff003-245">For more information about standard numeric formatting strings, see [Standard numeric format strings](standard-numeric.md).</span></span> 

<span data-ttu-id="ff003-246">Standardformatzeichenfolgen für Datums- und Uhrzeitwerte sind Aliase für benutzerdefinierte Formatzeichenfolgen, die von einer bestimmten [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Klasse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-246">Standard format strings for date and time values are aliases for custom format strings stored by a particular [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) class.</span></span> <span data-ttu-id="ff003-247">Beispielsweise werden durch Aufrufen der [ToString](xref:System.Object.ToString)-Methode eines Datums- und Uhrzeitwerts mit dem Formatbezeichner „D“ das Datum und die Uhrzeit mit der benutzerdefinierten Formatzeichenfolge angezeigt, die in der [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern)-Eigenschaft der aktuellen Kultur gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ff003-247">For example, calling the [ToString](xref:System.Object.ToString) method of a date and time value with the "D" format specifier displays the date and time by using the custom format string stored in the current culture’s [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) property.</span></span> <span data-ttu-id="ff003-248">(Weitere Informationen zu benutzerdefinierten Formatzeichenfolgen finden Sie im Abschnitt [Benutzerdefinierte Formatzeichenfolgen](#custom-format-strings).) Diese Beziehung wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ff003-248">(For more information about custom format strings, see the [Custom format strings](#custom-format-strings) section.) The following example illustrates this relationship.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      DateTime date1 = new DateTime(2017, 6, 30);
      Console.WriteLine("D Format Specifier:     {0:D}", date1);
      string longPattern = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern;
      Console.WriteLine("'{0}' custom format string:     {1}", 
                        longPattern, date1.ToString(longPattern));
   }
}
// The example displays the following output when run on a system whose
// current culture is en-US:
//    D Format Specifier:     Tuesday, June 30, 2017
//    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2017
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim date1 As Date = #6/30/2009#
      Console.WriteLine("D Format Specifier:     {0:D}", date1)
      Dim longPattern As String = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern
      Console.WriteLine("'{0}' custom format string:     {1}", _
                        longPattern, date1.ToString(longPattern))
   End Sub
End Module
' The example displays the following output when run on a system whose
' current culture is en-US:
'    D Format Specifier:     Tuesday, June 30, 2009
'    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2009
```

<span data-ttu-id="ff003-249">Weitere Informationen zu Standard-Zahlenformatzeichenfolgen finden Sie unter [Standardformatzeichenfolgen für Datum und Uhrzeit](standard-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="ff003-249">For more information about standard date and time format strings, see [Standard date and time format strings](standard-datetime.md).</span></span>

<span data-ttu-id="ff003-250">Sie können Standardformatzeichenfolgen auch verwenden, um die Zeichenfolgendarstellung eines anwendungsdefinierten Objekts anzugeben, die von der `ToString(String)`-Methode des Objekts erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ff003-250">You can also use standard format strings to define the string representation of an application-defined object that is produced by the object’s `ToString(String)` method.</span></span> <span data-ttu-id="ff003-251">Sie können die spezifischen Standardformatbezeichner definieren, die von dem Objekt unterstützt werden, und Sie können angeben, ob die Groß- und Kleinschreibung beachtet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff003-251">You can define the specific standard format specifiers that your object supports, and you can determine whether they are case-sensitive or case-insensitive.</span></span> <span data-ttu-id="ff003-252">Ihre Implementierung der `ToString(String)`-Methode sollte Folgendes unterstützen:</span><span class="sxs-lookup"><span data-stu-id="ff003-252">Your implementation of the `ToString(String)` method should support the following:</span></span>

* <span data-ttu-id="ff003-253">Den Formatbezeichner "G", der ein übliches oder allgemeines Format des Objekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-253">A "G" format specifier that represents a customary or common format of the object.</span></span> <span data-ttu-id="ff003-254">Die parameterlose Überladung der `ToString`-Methode des Objekts sollte die zugehörige `ToString(String)`-Überladung aufrufen und die Standardformatzeichenfolge "G" übergeben.</span><span class="sxs-lookup"><span data-stu-id="ff003-254">The parameterless overload of your object's `ToString` method should call its `ToString(String)` overload and pass it the "G" standard format string.</span></span>

* <span data-ttu-id="ff003-255">Unterstützung für einen Formatbezeichner, der gleich einem NULL-Verweis ist.</span><span class="sxs-lookup"><span data-stu-id="ff003-255">Support for a format specifier that is equal to a null reference.</span></span> <span data-ttu-id="ff003-256">Ein Formatbezeichner, der gleich einem NULL-Verweis ist, sollte als äquivalent mit dem "G"-Formatbezeichner angesehen werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-256">A format specifier that is equal to a null reference should be considered equivalent to the "G" format specifier.</span></span>

<span data-ttu-id="ff003-257">Beispielsweise kann eine `Temperature`-Klasse die Temperatur in Grad Celsius intern speichern und Formatbezeichner verwenden, um den Wert des `Temperature`-Objekts in Grad Celsius, Grad Fahrenheit und Kelvin darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-257">For example, a `Temperature` class can internally store the temperature in degrees Celsius and use format specifiers to represent the value of the `Temperature` object in degrees Celsius, degrees Fahrenheit, and kelvins.</span></span> <span data-ttu-id="ff003-258">Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ff003-258">The following example provides an illustration.</span></span>

```csharp
using System;

public class Temperature
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round(((decimal) (this.m_Temp * 9 / 5 + 32)), 2); }
   }

   public override string ToString()
   {
      return this.ToString("C");
   }

   public string ToString(string format)
   {  
      // Handle null or empty string.
      if (String.IsNullOrEmpty(format)) format = "C";
      // Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant();      

      // Convert temperature to Fahrenheit and return string.
      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2") + " °F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2") + " K";
         // return temperature in Celsius.
         case "G":
         case "C":
            return this.Celsius.ToString("N2") + " °C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}

public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(0m);
      Console.WriteLine(temp1.ToString());
      Console.WriteLine(temp1.ToString("G"));
      Console.WriteLine(temp1.ToString("C"));
      Console.WriteLine(temp1.ToString("F"));
      Console.WriteLine(temp1.ToString("K"));

      Temperature temp2 = new Temperature(-40m);
      Console.WriteLine(temp2.ToString());
      Console.WriteLine(temp2.ToString("G"));
      Console.WriteLine(temp2.ToString("C"));
      Console.WriteLine(temp2.ToString("F"));
      Console.WriteLine(temp2.ToString("K"));

      Temperature temp3 = new Temperature(16m);
      Console.WriteLine(temp3.ToString());
      Console.WriteLine(temp3.ToString("G"));
      Console.WriteLine(temp3.ToString("C"));
      Console.WriteLine(temp3.ToString("F"));
      Console.WriteLine(temp3.ToString("K"));

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3));
   }
}
// The example displays the following output:
//       0.00 °C
//       0.00 °C
//       0.00 °C
//       32.00 °F
//       273.15 K
//       -40.00 °C
//       -40.00 °C
//       -40.00 °C
//       -40.00 °F
//       233.15 K
//       16.00 °C
//       16.00 °C
//       16.00 °C
//       60.80 °F
//       289.15 K
//       The temperature is now 16.00 °C.
```

```vb
Public Class Temperature
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("C")
   End Function

   Public Overloads Function ToString(format As String) As String  
      ' Handle null or empty string.
      If String.IsNullOrEmpty(format) Then format = "C"
      ' Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant()      

      Select Case format
         Case "F"
           ' Convert temperature to Fahrenheit and return string.
            Return Me.Fahrenheit.ToString("N2") & " °F"
         Case "K"
            ' Convert temperature to Kelvin and return string.
            Return Me.Kelvin.ToString("N2") & " K"
         Case "C", "G"
            ' Return temperature in Celsius.
            Return Me.Celsius.ToString("N2") & " °C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(0d)
      Console.WriteLine(temp1.ToString())
      Console.WriteLine(temp1.ToString("G"))
      Console.WriteLine(temp1.ToString("C"))
      Console.WriteLine(temp1.ToString("F"))
      Console.WriteLine(temp1.ToString("K"))

      Dim temp2 As New Temperature(-40d)
      Console.WriteLine(temp2.ToString())
      Console.WriteLine(temp2.ToString("G"))
      Console.WriteLine(temp2.ToString("C"))
      Console.WriteLine(temp2.ToString("F"))
      Console.WriteLine(temp2.ToString("K"))

      Dim temp3 As New Temperature(16d)
      Console.WriteLine(temp3.ToString())
      Console.WriteLine(temp3.ToString("G"))
      Console.WriteLine(temp3.ToString("C"))
      Console.WriteLine(temp3.ToString("F"))
      Console.WriteLine(temp3.ToString("K"))

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3))
   End Sub
End Module
' The example displays the following output:
'       0.00 °C
'       0.00 °C
'       0.00 °C
'       32.00 °F
'       273.15 K
'       -40.00 °C
'       -40.00 °C
'       -40.00 °C
'       -40.00 °F
'       233.15 K
'       16.00 °C
'       16.00 °C
'       16.00 °C
'       60.80 °F
'       289.15 K
'       The temperature is now 16.00 °C.
```

### <a name="custom-format-strings"></a><span data-ttu-id="ff003-259">Benutzerdefinierte Formatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-259">Custom format strings</span></span>

<span data-ttu-id="ff003-260">Zusätzlich zu den Standardformatzeichenfolgen definiert .NET benutzerdefinierte Formatzeichenfolgen für numerische Werte und Datums- und Uhrzeitwerte.</span><span class="sxs-lookup"><span data-stu-id="ff003-260">In addition to the standard format strings, .NET defines custom format strings for both numeric values and date and time values.</span></span> <span data-ttu-id="ff003-261">Eine benutzerdefinierte Formatzeichenfolge besteht aus einem oder mehreren benutzerdefinierten Formatbezeichnern, die die Zeichenfolgendarstellung eines Werts definieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-261">A custom format string consists of one or more custom format specifiers that define the string representation of a value.</span></span> <span data-ttu-id="ff003-262">Beispielsweise konvertiert die benutzerdefinierte Datums- und Uhrzeitformatzeichenfolge "yyyy/mm/dd hh:mm:ss.ffff t zzz" ein Datum für die Kultur en-US wie folgt in die entsprechende Zeichenfolgendarstellung: "2008/11/15 07:45:00.0000 P -08:00".</span><span class="sxs-lookup"><span data-stu-id="ff003-262">For example, the custom date and time format string "yyyy/mm/dd hh:mm:ss.ffff t zzz" converts a date to its string representation in the form "2008/11/15 07:45:00.0000 P -08:00" for the en-US culture.</span></span> <span data-ttu-id="ff003-263">Analog konvertiert die benutzerdefinierte Formatzeichenfolge "0000" den ganzzahligen Wert 12 in "0012".</span><span class="sxs-lookup"><span data-stu-id="ff003-263">Similarly, the custom format string "0000" converts the integer value 12 to "0012".</span></span> <span data-ttu-id="ff003-264">Eine vollständige Liste benutzerdefinierter Formatzeichenfolgen finden Sie unter [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md) und [Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric.md).</span><span class="sxs-lookup"><span data-stu-id="ff003-264">For a complete list of custom format strings, see [Custom date and time format strings](custom-datetime.md) and [Custom numeric format strings](custom-numeric.md).</span></span>

<span data-ttu-id="ff003-265">Wenn eine Formatzeichenfolge aus einem einzelnen benutzerdefinierten Formatbezeichner besteht, sollte dem Formatbezeichner das Prozentsymbol (%) vorangestellt werden, um Verwechslungen mit einem Standardformatbezeichner zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="ff003-265">If a format string consists of a single custom format specifier, the format specifier should be preceded by the percent (%) symbol to avoid confusion with a standard format specifier.</span></span> <span data-ttu-id="ff003-266">Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "M" verwendet, um eine einstellige oder zweistellige Ziffer für einen bestimmten Tag des Monats anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff003-266">The following example uses the "M" custom format specifier to display a one-digit or two-digit number of the month of a particular date.</span></span>

```csharp
DateTime date1 = new DateTime(2009, 9, 8);
Console.WriteLine(date1.ToString("%M"));       
// Displays 9
```

```vb
Dim date1 As Date = #09/08/2009#
Console.WriteLine(date1.ToString("%M"))      ' Displays 9
```

<span data-ttu-id="ff003-267">Viele Standardformatzeichenfolgen für Datums- und Uhrzeitwerte sind Aliase für benutzerdefinierte Formatzeichenfolgen, die von Eigenschaften des [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-267">Many standard format strings for date and time values are aliases for custom format strings that are defined by properties of the [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object.</span></span> <span data-ttu-id="ff003-268">Benutzerdefinierte Formatzeichenfolgen ermöglichen außerdem eine hohe Flexibilität beim Bereitstellen von anwendungsdefinierter Formatierung für numerische Werte oder Datums- und Uhrzeitwerte.</span><span class="sxs-lookup"><span data-stu-id="ff003-268">Custom format strings also offer considerable flexibility in providing application-defined formatting for numeric values or date and time values.</span></span> <span data-ttu-id="ff003-269">Sie können eigene benutzerdefinierte Ergebniszeichenfolgen für numerische Werte und für Datums- und Uhrzeitwerte definieren, indem Sie mehrere benutzerdefinierte Formatbezeichner zu einer einzelnen benutzerdefinierten Formatzeichenfolge kombinieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-269">You can define your own custom result strings for both numeric values and date and time values by combining multiple custom format specifiers into a single custom format string.</span></span> <span data-ttu-id="ff003-270">Im folgenden Beispiel wird eine benutzerdefinierte Formatzeichenfolge definiert, die im Anschluss an den Namen des Monats, den Tag und das Jahr den Tag der Woche in Klammern anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ff003-270">The following example defines a custom format string that displays the day of the week in parentheses after the month name, day, and year.</span></span>

```csharp
string customFormat = "MMMM dd, yyyy (dddd)";
DateTime date1 = new DateTime(2009, 8, 28);
Console.WriteLine(date1.ToString(customFormat));   
// The example displays the following output if run on a system
// whose language is English:
//       August 28, 2009 (Friday) 
```

```vb
Dim customFormat As String = "MMMM dd, yyyy (dddd)"
Dim date1 As Date = #8/28/2009#
Console.WriteLine(date1.ToString(customFormat))   
' The example displays the following output if run on a system
' whose language is English:
'       August 28, 2009 (Friday) 
```

<span data-ttu-id="ff003-271">Das folgende Beispiel definiert eine benutzerdefinierte Formatzeichenfolge, die einen [Int64](xref:System.Int64)-Wert als standardmäßige, siebenstellige US-Telefonnummer mit der Ortsvorwahl anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ff003-271">The following example defines a custom format string that displays an [Int64](xref:System.Int64) value as a standard, seven-digit U.S. telephone number along with its area code.</span></span> 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      long number = 8009999999;
      string fmt = "000-000-0000";
      Console.WriteLine(number.ToString(fmt));
   }
}
// The example displays the following output:
//        800-999-9999
```

```vb
Module Example
   Public Sub Main()
      Dim number As Long = 8009999999
      Dim fmt As String = "000-000-0000"
      Console.WriteLine(number.ToString(fmt))
   End Sub
End Module
' The example displays the following output:

' The example displays the following output:
'       800-999-9999
```

<span data-ttu-id="ff003-272">Standardformatzeichenfolgen decken i. d. R. die meisten der Formatierungsanforderungen für anwendungsdefinierte Typen ab. Sie können jedoch auch benutzerdefinierte Formatbezeichner definieren, um Typen zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-272">Although standard format strings can generally handle most of the formatting needs for your application-defined types, you may also define custom format specifiers to format your types.</span></span> 

### <a name="format-strings-and-net-types"></a><span data-ttu-id="ff003-273">Formatzeichenfolgen und .NET-Typen</span><span class="sxs-lookup"><span data-stu-id="ff003-273">Format strings and .NET types</span></span>

<span data-ttu-id="ff003-274">Alle numerischen Typen (also die Typen [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64) und [BigInteger](xref:System.Numerics.BigInteger)) sowie die Typen [DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset), [TimeSpan](xref:System.TimeSpan) und [Guid](xref:System.Guid) und alle Enumerationstypen unterstützen die Formatierung mit Formatzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="ff003-274">All numeric types (that is, the [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64), and [BigInteger](xref:System.Numerics.BigInteger) types), as well as the [DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset), [TimeSpan](xref:System.TimeSpan), [Guid](xref:System.Guid), and all enumeration types, support formatting with format strings.</span></span> <span data-ttu-id="ff003-275">Informationen zu bestimmten Formatzeichenfolgen, die von jedem Typ unterstützt werden, finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ff003-275">For information on the specific format strings supported by each type, see the following topics:</span></span> 

<span data-ttu-id="ff003-276">Titel</span><span class="sxs-lookup"><span data-stu-id="ff003-276">Title</span></span> | <span data-ttu-id="ff003-277">Definition</span><span class="sxs-lookup"><span data-stu-id="ff003-277">Definition</span></span>
----- | ----------
[<span data-ttu-id="ff003-278">Standard-Zahlenformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-278">Standard numeric format strings</span></span>](standard-numeric.md) | <span data-ttu-id="ff003-279">Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von numerischen Werten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-279">Describes standard format strings that create commonly used string representations of numeric values.</span></span> 
[<span data-ttu-id="ff003-280">Benutzerdefinierte Zahlenformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-280">Custom numeric format strings</span></span>](custom-numeric.md) | <span data-ttu-id="ff003-281">Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für numerische Werte erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-281">Describes custom format strings that create application-specific formats for numeric values.</span></span>
[<span data-ttu-id="ff003-282">Standardformatzeichenfolgen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ff003-282">Standard date and time format strings</span></span>](standard-datetime.md) | <span data-ttu-id="ff003-283">Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von [DateTime](xref:System.DateTime)-Werten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-283">Describes standard format strings that create commonly used string representations of [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="ff003-284">Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ff003-284">Custom date and time format strings</span></span>](custom-datetime.md) | <span data-ttu-id="ff003-285">Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für [DateTime](xref:System.DateTime)-Werte erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-285">Describes custom format strings that create application-specific formats for [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="ff003-286">TimeSpan-Standardformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-286">Standard TimeSpan format Strings</span></span>](standard-timespan.md) | <span data-ttu-id="ff003-287">Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von Zeitintervallen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-287">Describes standard format strings that create commonly used string representations of time intervals.</span></span>
[<span data-ttu-id="ff003-288">Benutzerdefinierte TimeSpan-Formatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-288">Custom TimeSpan format strings</span></span>](custom-timespan.md) | <span data-ttu-id="ff003-289">Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für Zeitintervalle erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-289">Describes custom format strings that create application-specific formats for time intervals.</span></span>
[<span data-ttu-id="ff003-290">Enumerationsformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-290">Enumeration format strings</span></span>](enumeration-format.md) | <span data-ttu-id="ff003-291">Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen Zeichenfolgenentsprechungen von Enumerationswerten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-291">Describes standard format strings that are used to create string representations of enumeration values.</span></span>
<span data-ttu-id="ff003-292">[Guid.ToString(String)](xref:System.Guid.ToString(System.String))</span><span class="sxs-lookup"><span data-stu-id="ff003-292">[Guid.ToString(String)](xref:System.Guid.ToString(System.String))</span></span> | <span data-ttu-id="ff003-293">Beschreibt Standardformatzeichenfolgen für [Guid](xref:System.Guid)-Werte.</span><span class="sxs-lookup"><span data-stu-id="ff003-293">Describes standard format strings for [Guid](xref:System.Guid) values.</span></span>

## <a name="culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface"></a><span data-ttu-id="ff003-294">Kulturabhängige Formatierung mit Formatanbietern und der IFormatProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff003-294">Culture-Sensitive Formatting with Format Providers and the IFormatProvider Interface</span></span>

<span data-ttu-id="ff003-295">Obwohl Sie mit Formatbezeichnern die Formatierung von Objekten anpassen können, sind für eine sinnvolle Zeichenfolgendarstellung von Objekten oft zusätzliche Formatierungsinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ff003-295">Although format specifiers let you customize the formatting of objects, producing a meaningful string representation of objects often requires additional formatting information.</span></span> <span data-ttu-id="ff003-296">Beispielsweise ist für das Formatieren einer Zahl als Währungswert mit der Standardformatzeichenfolge "C" oder mit einer benutzerdefinierten Formatzeichenfolge wie "$ #,#.00" mindestens erforderlich, dass Informationen über das richtige Währungssymbol, das richtige Gruppentrennzeichen und das richtige Dezimaltrennzeichen verfügbar sind, um in die formatierte Zeichenfolge eingeschlossen zu werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-296">For example, formatting a number as a currency value by using either the "C" standard format string or a custom format string such as "$ #,#.00" requires, at a minimum, information about the correct currency symbol, group separator, and decimal separator to be available to include in the formatted string.</span></span> <span data-ttu-id="ff003-297">In .NET werden diese zusätzlichen Formatierungsinformationen durch die [IFormatProvider](xref:System.IFormatProvider)-Schnittstelle verfügbar gemacht. Diese wird als Parameter für eine oder mehrere Überladungen der `ToString`-Methode von numerischen Typen sowie von Datums- und Uhrzeittypen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-297">In .NET, this additional formatting information is made available through the [IFormatProvider](xref:System.IFormatProvider) interface, which is provided as a parameter to one or more overloads of the `ToString` method of numeric types and date and time types.</span></span> <span data-ttu-id="ff003-298">[IFormatProvider](xref:System.IFormatProvider)-Implementierungen werden in .NET verwendet, um eine kulturabhängige Formatierung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ff003-298">[IFormatProvider](xref:System.IFormatProvider) implementations are used in .NET to support culture-specific formatting.</span></span> <span data-ttu-id="ff003-299">Das folgende Beispiel veranschaulicht, wie sich die Zeichenfolgendarstellung eines Objekts ändert, wenn die Formatierung mit drei [IFormatProvider](xref:System.IFormatProvider)-Objekten erfolgt, die verschiedene Kulturen darstellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-299">The following example illustrates how the string representation of an object changes when it is formatted with three [IFormatProvider](xref:System.IFormatProvider) objects that represent different cultures.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      decimal value = 1603.42m;
      Console.WriteLine(value.ToString("C3", new CultureInfo("en-US")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("fr-FR")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("de-DE")));
   }
}
// The example displays the following output:
//       $1,603.420
//       1 603,420 €
//       1.603,420 €
```

```vb
Imports System.Globalization

Public Module Example
   Public Sub Main()
      Dim value As Decimal = 1603.42d
      Console.WriteLine(value.ToString("C3", New CultureInfo("en-US")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("fr-FR")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("de-DE")))
   End Sub
End Module
' The example displays the following output:
'       $1,603.420
'       1 603,420 €
'       1.603,420 €
```

<span data-ttu-id="ff003-300">Die [IFormatProvider](xref:System.IFormatProvider)-Schnittstelle enthält eine Methode: [GetFormat(Type)](xref:System.IFormatProvider.GetFormat(System.Type)). Diese weist einen einzigen Parameter auf, der den Typ des Objekts angibt, das Formatierungsinformationen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-300">The [IFormatProvider](xref:System.IFormatProvider) interface includes one method, [GetFormat(Type)](xref:System.IFormatProvider.GetFormat(System.Type)), which has a single parameter that specifies the type of object that provides formatting information.</span></span> <span data-ttu-id="ff003-301">Wenn die Methode ein Objekt dieses Typs bereitstellen kann, wird dieses zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ff003-301">If the method can provide an object of that type, it returns it.</span></span> <span data-ttu-id="ff003-302">Andernfalls wird ein NULL-Verweis zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ff003-302">Otherwise, it returns a null reference.</span></span>

<span data-ttu-id="ff003-303">[IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) ist eine Rückrufmethode.</span><span class="sxs-lookup"><span data-stu-id="ff003-303">[IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) is a callback method.</span></span> <span data-ttu-id="ff003-304">Wenn Sie eine `ToString`-Methodenüberladung aufrufen, die einen [IFormatProvider](xref:System.IFormatProvider)-Parameter enthält, wird die [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Methode dieses [IFormatProvider](xref:System.IFormatProvider)-Objekts aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ff003-304">When you call a `ToString` method overload that includes an [IFormatProvider](xref:System.IFormatProvider) parameter, it calls the [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method of that [IFormatProvider](xref:System.IFormatProvider) object.</span></span> <span data-ttu-id="ff003-305">Die [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Methode ist dafür zuständig, ein Objekt zurückzugeben, das die notwendigen Formatierungsinformationen, wie vom *formatType*-Parameter angegeben, für die `ToString`-Methode bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-305">The [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method is responsible for returning an object that provides the necessary formatting information, as specified by its *formatType* parameter, to the `ToString` method.</span></span> 

<span data-ttu-id="ff003-306">Eine Reihe von Formatierungs- oder Zeichenfolgenkonvertierungsmethoden enthalten einen Parameter vom Typ [IFormatProvider](xref:System.IFormatProvider). In vielen Fällen wird der Wert des Parameters beim Aufrufen der Methode jedoch ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ff003-306">A number of formatting or string conversion methods include a parameter of type [IFormatProvider](xref:System.IFormatProvider), but in many cases the value of the parameter is ignored when the method is called.</span></span> <span data-ttu-id="ff003-307">In der folgenden Tabelle sind einige Formatierungsmethoden aufgeführt, die den Parameter und den Typ des [Type](xref:System.Type)-Objekts verwenden, das an die [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ff003-307">The following table lists some of the formatting methods that use the parameter and the type of the [Type](xref:System.Type) object that they pass to the [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method.</span></span> 

<span data-ttu-id="ff003-308">Methode</span><span class="sxs-lookup"><span data-stu-id="ff003-308">Method</span></span> | <span data-ttu-id="ff003-309">Typ des *formatType*-Parameters</span><span class="sxs-lookup"><span data-stu-id="ff003-309">Type of *formatType* parameter</span></span>
------ | ------------------------------
<span data-ttu-id="ff003-310">`ToString`-Methode für numerische Typen</span><span class="sxs-lookup"><span data-stu-id="ff003-310">`ToString` method of numeric types</span></span> | [<span data-ttu-id="ff003-311">System.Globalization.NumberFormatInfo</span><span class="sxs-lookup"><span data-stu-id="ff003-311">System.Globalization.NumberFormatInfo</span></span>](xref:System.Globalization.NumberFormatInfo)
<span data-ttu-id="ff003-312">`ToString`-Methode für Datums- und Uhrzeittypen</span><span class="sxs-lookup"><span data-stu-id="ff003-312">`ToString` method of date and time types</span></span> | [<span data-ttu-id="ff003-313">System.Globalization.DateTimeFormatInfo</span><span class="sxs-lookup"><span data-stu-id="ff003-313">System.Globalization.DateTimeFormatInfo</span></span>](xref:System.Globalization.DateTimeFormatInfo)
<span data-ttu-id="ff003-314">[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="ff003-314">[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))</span></span> | [<span data-ttu-id="ff003-315">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="ff003-315">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)
<span data-ttu-id="ff003-316">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="ff003-316">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span></span> | [<span data-ttu-id="ff003-317">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="ff003-317">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)

<span data-ttu-id="ff003-318">.NET stellt drei Klassen bereit, die [IFormatProvider](xref:System.IFormatProvider) implementieren:</span><span class="sxs-lookup"><span data-stu-id="ff003-318">.NET provides three classes that implement [IFormatProvider](xref:System.IFormatProvider):</span></span> 

* <span data-ttu-id="ff003-319">[DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), eine Klasse, die Formatierungsinformationen für Datums- und Uhrzeitwerte für eine bestimmte Kultur bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-319">[DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), a class that provides formatting information for date and time values for a specific culture.</span></span> <span data-ttu-id="ff003-320">Die [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Implementierung der Klasse gibt eine Instanz von sich selbst zurück.</span><span class="sxs-lookup"><span data-stu-id="ff003-320">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation returns an instance of itself.</span></span>

* <span data-ttu-id="ff003-321">[NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), eine Klasse, die numerische Formatierungsinformationen für eine bestimmte Kultur bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-321">[NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), a class that provides numeric formatting information for a specific culture.</span></span> <span data-ttu-id="ff003-322">Die [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Implementierung der Klasse gibt eine Instanz von sich selbst zurück.</span><span class="sxs-lookup"><span data-stu-id="ff003-322">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation returns an instance of itself.</span></span>

* <span data-ttu-id="ff003-323">[CultureInfo](xref:System.Globalization.CultureInfo).</span><span class="sxs-lookup"><span data-stu-id="ff003-323">[CultureInfo](xref:System.Globalization.CultureInfo).</span></span> <span data-ttu-id="ff003-324">Die zugehörige [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Implementierung kann ein [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt zurückgeben, um numerische Formatierungsinformationen bereitzustellen, oder ein [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt, um Formatierungsinformationen für Datums- und Uhrzeitwerte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-324">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation can return either a [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object to provide numeric formatting information or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object to provide formatting information for date and time values.</span></span> 

<span data-ttu-id="ff003-325">Sie können auch einen eigenen Formatanbieter implementieren, um eine dieser Klassen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="ff003-325">You can also implement your own format provider to replace any one of these classes.</span></span> <span data-ttu-id="ff003-326">Die `GetFormat`-Methode Ihrer Implementierung muss jedoch ein Objekt eines in der vorangehenden Tabelle aufgeführten Typs zurückgeben, um Formatierungsinformationen für die `ToString`-Methode bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-326">However, your implementation’s `GetFormat` method must return an object of the type listed in the previous table if it has to provide formatting information to the `ToString` method.</span></span>

### <a name="culture-sensitive-formatting-of-numeric-values"></a><span data-ttu-id="ff003-327">Kulturabhängige Formatierung von numerischen Werten</span><span class="sxs-lookup"><span data-stu-id="ff003-327">Culture-sensitive formatting of numeric values</span></span>

<span data-ttu-id="ff003-328">Standardmäßig ist die Formatierung von numerischen Werten kulturabhängig.</span><span class="sxs-lookup"><span data-stu-id="ff003-328">By default, the formatting of numeric values is culture-sensitive.</span></span> <span data-ttu-id="ff003-329">Wenn Sie beim Aufrufen einer Formatierungsmethode keine Kultur angeben, werden die Formatierungskonventionen der aktuellen Threadkultur verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff003-329">If you do not specify a culture when you call a formatting method, the formatting conventions of the current thread culture are used.</span></span> <span data-ttu-id="ff003-330">Dies wird im folgenden Beispiel veranschaulicht, das die aktuelle Threadkultur viermal ändert und anschließend die [Decimal.ToString(String)](xref:System.Decimal.ToString(System.String))-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="ff003-330">This is illustrated in the following example, which changes the current thread culture four times and then calls the [Decimal.ToString(String)](xref:System.Decimal.ToString(System.String)) method.</span></span> <span data-ttu-id="ff003-331">In allen Fällen gibt die Ergebniszeichenfolge die Formatierungskonventionen der aktuellen Kultur wieder.</span><span class="sxs-lookup"><span data-stu-id="ff003-331">In each case, the result string reflects the formatting conventions of the current culture.</span></span> <span data-ttu-id="ff003-332">Dies liegt daran, dass die `ToString`- und `ToString(String)`-Methoden die Aufrufe der `ToString(String, IFormatProvider)`-Methode jedes numerischen Typs umschließen.</span><span class="sxs-lookup"><span data-stu-id="ff003-332">This is because the `ToString` and `ToString(String)` methods wrap calls to each numeric type's `ToString(String, IFormatProvider)` method.</span></span> 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      Decimal value = 1043.17m;

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(value.ToString("C2"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       $1,043.17
//       
//       The current culture is fr-FR
//       1 043,17 €
//       
//       The current culture is es-MX
//       $1,043.17
//       
//       The current culture is de-DE
//       1.043,17 €
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim value As Decimal = 1043.17d 

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(value.ToString("C2"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       $1,043.17
'       
'       The current culture is fr-FR
'       1 043,17 €
'       
'       The current culture is es-MX
'       $1,043.17
'       
'       The current culture is de-DE
'       1.043,17 €
```

<span data-ttu-id="ff003-333">Sie können einen numerischen Wert für eine bestimmte Kultur auch formatieren, indem Sie eine `ToString`-Überladung aufrufen, die einen *provider*-Parameter aufweist, und ihr eins der folgenden Objekte übergeben:</span><span class="sxs-lookup"><span data-stu-id="ff003-333">You can also format a numeric value for a specific culture by calling a `ToString` overload that has a *provider* parameter and passing it either of the following:</span></span> 

* <span data-ttu-id="ff003-334">Ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, das die Kultur darstellt, deren Formatierungskonventionen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ff003-334">A [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the culture whose formatting conventions are to be used.</span></span> <span data-ttu-id="ff003-335">Die zugehörige [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type))-Methode gibt den Wert der [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat)-Eigenschaft zurück, bei der es sich um das [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt handelt, das kulturspezifische Formatierungsinformationen für numerische Werte bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-335">Its [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns the value of the [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) property, which is the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that provides culture-specific formatting information for numeric values.</span></span>

* <span data-ttu-id="ff003-336">Ein [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt, das die kulturspezifischen Formatierungskonventionen definiert, die verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ff003-336">A [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that defines the culture-specific formatting conventions to be used.</span></span> <span data-ttu-id="ff003-337">Die zugehörige [GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type))-Methode gibt eine Instanz von sich selbst zurück.</span><span class="sxs-lookup"><span data-stu-id="ff003-337">Its [GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) method returns an instance of itself.</span></span>

<span data-ttu-id="ff003-338">Im folgenden Beispiel werden [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekte verwendet, die die Kulturen „Englisch (USA)“ und „Englisch (Vereinigtes Königreich)“ sowie die neutralen Kulturen „Französisch“ und „Russisch“ darstellen, um eine Gleitkommazahl zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-338">The following example uses [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) objects that represent the English (United States) and English (Great Britain) cultures and the French and Russian neutral cultures to format a floating-point number.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      Double value = 1043.62957;
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         NumberFormatInfo nfi = CultureInfo.CreateSpecificCulture(name).NumberFormat;
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 1,043.630
//       en-GB: 1,043.630
//       ru:    1 043,630
//       fr:    1 043,630
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As Double = 1043.62957
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim nfi As NumberFormatInfo = CultureInfo.CreateSpecificCulture(name).NumberFormat
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 1,043.630
'       en-GB: 1,043.630
'       ru:    1 043,630
'       fr:    1 043,630
```

### <a name="culture-sensitive-formatting-of-date-and-time-values"></a><span data-ttu-id="ff003-339">Kulturabhängige Formatierung von Datums- und Uhrzeitwerten</span><span class="sxs-lookup"><span data-stu-id="ff003-339">Culture-sensitive formatting of date and time values</span></span>

<span data-ttu-id="ff003-340">Standardmäßig ist die Formatierung von Daten- und Uhrzeitwerten kulturabhängig.</span><span class="sxs-lookup"><span data-stu-id="ff003-340">By default, the formatting of date and time values is culture-sensitive.</span></span> <span data-ttu-id="ff003-341">Wenn Sie beim Aufrufen einer Formatierungsmethode keine Kultur angeben, werden die Formatierungskonventionen der aktuellen Threadkultur verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff003-341">If you do not specify a culture when you call a formatting method, the formatting conventions of the current thread culture are used.</span></span> <span data-ttu-id="ff003-342">Dies wird im folgenden Beispiel veranschaulicht, das die aktuelle Threadkultur viermal ändert und anschließend die [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String))-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="ff003-342">This is illustrated in the following example, which changes the current thread culture four times and then calls the [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)) method.</span></span> <span data-ttu-id="ff003-343">In allen Fällen gibt die Ergebniszeichenfolge die Formatierungskonventionen der aktuellen Kultur wieder.</span><span class="sxs-lookup"><span data-stu-id="ff003-343">In each case, the result string reflects the formatting conventions of the current culture.</span></span> <span data-ttu-id="ff003-344">Dies liegt daran, dass die Methoden [DateTime.ToString()](xref:System.DateTime.ToString), [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)), [DateTimeOffset.ToString()](xref:System.DateTimeOffset.ToString(System.String)) und [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) Aufrufe der Methoden [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) und [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) umschließen.</span><span class="sxs-lookup"><span data-stu-id="ff003-344">This is because the [DateTime.ToString()](xref:System.DateTime.ToString), [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)), [DateTimeOffset.ToString()](xref:System.DateTimeOffset.ToString(System.String)), and [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) methods wrap calls to the [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) and [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) methods.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      DateTime dateToFormat = new DateTime(2012, 5, 28, 11, 30, 0);

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(dateToFormat.ToString("F"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       Monday, May 28, 2012 11:30:00 AM
//       
//       The current culture is fr-FR
//       lundi 28 mai 2012 11:30:00
//       
//       The current culture is es-MX
//       lunes, 28 de mayo de 2012 11:30:00 a.m.
//       
//       The current culture is de-DE
//       Montag, 28. Mai 2012 11:30:00
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim dateToFormat As Date = #5/28/2012 11:30AM#

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(dateToFormat.ToString("F"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       Monday, May 28, 2012 11:30:00 AM
'       
'       The current culture is fr-FR
'       lundi 28 mai 2012 11:30:00
'       
'       The current culture is es-MX
'       lunes, 28 de mayo de 2012 11:30:00 a.m.
'       
'       The current culture is de-DE
'       Montag, 28. Mai 2012 11:30:00
```

<span data-ttu-id="ff003-345">Sie können einen Datums- und Uhrzeitwert für eine bestimmte Kultur auch formatieren, indem Sie eine [DateTime.ToString](xref:System.DateTime.ToString(System.String,System.IFormatProvider))- oder [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider))-Überladung aufrufen, die einen provider-Parameter aufweist, und ihr eins der folgenden Objekte übergeben:</span><span class="sxs-lookup"><span data-stu-id="ff003-345">You can also format a date and time value for a specific culture by calling a [DateTime.ToString](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) or [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) overload that has a provider parameter and passing it either of the following:</span></span> 

* <span data-ttu-id="ff003-346">Ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, das die Kultur darstellt, deren Formatierungskonventionen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ff003-346">A [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the culture whose formatting conventions are to be used.</span></span> <span data-ttu-id="ff003-347">Die zugehörige [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type))-Methode gibt den Wert der [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat)-Eigenschaft zurück, bei der es sich um das [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt handelt, das kulturspezifische Formatierungsinformationen für numerische Werte bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-347">Its [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns the value of the [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) property, which is the [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that provides culture-specific formatting information for numeric values.</span></span>

* <span data-ttu-id="ff003-348">Ein [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt, das die kulturspezifischen Formatierungskonventionen definiert, die verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ff003-348">A [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that defines the culture-specific formatting conventions to be used.</span></span> <span data-ttu-id="ff003-349">Die zugehörige [GetFormat](xref:System.Globalization.DateTimeFormatInfo.GetFormat(System.Type))-Methode gibt eine Instanz von sich selbst zurück.</span><span class="sxs-lookup"><span data-stu-id="ff003-349">Its [GetFormat](xref:System.Globalization.DateTimeFormatInfo.GetFormat(System.Type)) method returns an instance of itself.</span></span>

<span data-ttu-id="ff003-350">Im folgenden Beispiel werden [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekte verwendet, die die Kulturen „Englisch (USA)“ und „Englisch (Vereinigtes Königreich)“ sowie die neutralen Kulturen „Französisch“ und „Russisch“ darstellen, um ein Datum zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-350">The following example uses [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) objects that represent the English (United States) and English (Great Britain) cultures and the French and Russian neutral cultures to format a date.</span></span> 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      DateTime dat1 = new DateTime(2012, 5, 28, 11, 30, 0);
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         DateTimeFormatInfo dtfi = CultureInfo.CreateSpecificCulture(name).DateTimeFormat;
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 5/28/2012 11:30:00 AM
//       en-GB: 28/05/2012 11:30:00
//       ru: 28.05.2012 11:30:00
//       fr: 28/05/2012 11:30:00
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dat1 As Date = #5/28/2012 11:30AM#
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim dtfi As DateTimeFormatInfo = CultureInfo.CreateSpecificCulture(name).DateTimeFormat
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 5/28/2012 11:30:00 AM
'       en-GB: 28/05/2012 11:30:00
'       ru: 28.05.2012 11:30:00
'       fr: 28/05/2012 11:30:00
```

## <a name="the-iformattable-interface"></a><span data-ttu-id="ff003-351">IFormattable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff003-351">The IFormattable interface</span></span>

<span data-ttu-id="ff003-352">Typen, die die `ToString`-Methode mit einer Formatzeichenfolge und einem [IFormatProvider](xref:System.IFormatProvider)-Parameter überladen, implementieren üblicherweise auch die [IFormattable](xref:System.IFormattable)-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ff003-352">Typically, types that overload the `ToString` method with a format string and an [IFormatProvider](xref:System.IFormatProvider) parameter also implement the [IFormattable](xref:System.IFormattable) interface.</span></span> <span data-ttu-id="ff003-353">Diese Schnittstelle verfügt über einen einzelnen Member, [IFormattable.ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)), der sowohl eine Formatzeichenfolge als auch einen Formatanbieter als Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="ff003-353">This interface has a single member, [IFormattable.ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)), that includes both a format string and a format provider as parameters.</span></span>

<span data-ttu-id="ff003-354">Das Implementieren der [IFormattable](xref:System.IFormattable)-Schnittstelle für die anwendungsdefinierte Klasse bietet zwei Vorteile:</span><span class="sxs-lookup"><span data-stu-id="ff003-354">Implementing the [IFormattable](xref:System.IFormattable) interface for your application-defined class offers two advantages:</span></span> 

* <span data-ttu-id="ff003-355">Unterstützung der Zeichenfolgenkonvertierung durch die [Convert](xref:System.Convert)-Klasse.</span><span class="sxs-lookup"><span data-stu-id="ff003-355">Support for string conversion by the [Convert](xref:System.Convert) class.</span></span> <span data-ttu-id="ff003-356">Aufrufe der Methoden [Convert.ToString(Object)](xref:System.Convert.ToString(System.Object)) und [Convert.ToString(Object, IFormatProvider)](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) rufen automatisch Ihre [IFormattable](xref:System.IFormattable)-Implementierung auf.</span><span class="sxs-lookup"><span data-stu-id="ff003-356">Calls to the [Convert.ToString(Object)](xref:System.Convert.ToString(System.Object)) and [Convert.ToString(Object, IFormatProvider)](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) methods call your [IFormattable](xref:System.IFormattable) implementation automatically.</span></span>

* <span data-ttu-id="ff003-357">Unterstützung für kombinierte Formatierung.</span><span class="sxs-lookup"><span data-stu-id="ff003-357">Support for composite formatting.</span></span> <span data-ttu-id="ff003-358">Wenn ein Formatelement, das eine Formatzeichenfolge enthält, verwendet wird, um den benutzerdefinierten Typ zu formatieren, ruft die Common Language Runtime automatisch Ihre [IFormattable](xref:System.IFormattable)-Implementierung auf und übergibt die Formatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ff003-358">If a format item that includes a format string is used to format your custom type, the Common Language Runtime automatically calls your [IFormattable](xref:System.IFormattable) implementation and passes it the format string.</span></span> <span data-ttu-id="ff003-359">Weitere Informationen zur zusammengesetzten Formatierung mit Methoden wie `String.Format` oder `Console.WriteLine` finden Sie im Abschnitt [Zusammengesetzte Formatierung](#composite-formatting).</span><span class="sxs-lookup"><span data-stu-id="ff003-359">For more information about composite formatting with methods such as `String.Format` or `Console.WriteLine`, see the [Composite formatting](#composite-formatting) section.</span></span>

<span data-ttu-id="ff003-360">Im folgenden Beispiel wird eine `Temperature`-Klasse definiert, die die [IFormattable](xref:System.IFormattable)-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="ff003-360">The following example defines a `Temperature` class that implements the [IFormattable](xref:System.IFormattable) interface.</span></span> <span data-ttu-id="ff003-361">Die Formatbezeichner "C" oder "G" werden darin unterstützt, um die Temperatur in Celsius anzuzeigen, der Formatbezeichner "F", um die Temperatur in Fahrenheit anzuzeigen, und der Formatbezeichner "KB", um die Temperatur in Kelvin anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff003-361">It supports the "C" or "G" format specifiers to display the temperature in Celsius, the "F" format specifier to display the temperature in Fahrenheit, and the "K" format specifier to display the temperature in Kelvin.</span></span>

```csharp
using System;
using System.Globalization;

public class Temperature : IFormattable
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round((decimal) this.m_Temp * 9 / 5 + 32, 2); }
   }

   public override string ToString()
   {
      return this.ToString("G", null);
   }

   public string ToString(string format)
   {
      return this.ToString(format, null);
   }

   public string ToString(string format, IFormatProvider provider)  
   {
      // Handle null or empty arguments.
      if (String.IsNullOrEmpty(format)) format = "G";
      // Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant();

      if (provider == null) provider = NumberFormatInfo.CurrentInfo;

      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2", provider) + "°F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2", provider) + "K";
         // Return temperature in Celsius.
         case "C":
         case "G":
            return this.Celsius.ToString("N2", provider) + "°C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}
```

```vb
Imports System.Globalization

Public Class Temperature : Implements IFormattable
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("G", Nothing)
   End Function

   Public Overloads Function ToString(format As String) As String
      Return Me.ToString(format, Nothing)
   End Function

   Public Overloads Function ToString(format As String, provider As IFormatProvider) As String _  
      Implements IFormattable.ToString

      ' Handle null or empty arguments.
      If String.IsNullOrEmpty(format) Then format = "G"
      ' Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant()

      If provider Is Nothing Then provider = NumberFormatInfo.CurrentInfo

      Select Case format
         ' Convert temperature to Fahrenheit and return string.
         Case "F"
            Return Me.Fahrenheit.ToString("N2", provider) & "°F"
         ' Convert temperature to Kelvin and return string.
         Case "K"
            Return Me.Kelvin.ToString("N2", provider) & "K"
         ' Return temperature in Celsius.
         Case "C", "G"
            Return Me.Celsius.ToString("N2", provider) & "°C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class
```

<span data-ttu-id="ff003-362">Im folgenden Beispiel wird ein `Temperature`-Objekt instanziiert.</span><span class="sxs-lookup"><span data-stu-id="ff003-362">The following example instantiates a `Temperature` object.</span></span> <span data-ttu-id="ff003-363">Anschließend wird die [ToString](xref:System.Convert.ToString(System.Object,System.IFormatProvider))-Methode aufgerufen, und es werden mehrere zusammengesetzte Formatzeichenfolgen verwendet, um andere Zeichenfolgendarstellungen eines `Temperature`-Objekts zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ff003-363">It then calls the [ToString](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) method and uses several composite format strings to obtain different string representations of a `Temperature` object.</span></span> <span data-ttu-id="ff003-364">Die einzelnen Methoden rufen jeweils die [IFormattable](xref:System.IFormattable)-Implementierung der `Temperature`-Klasse auf.</span><span class="sxs-lookup"><span data-stu-id="ff003-364">Each of these method calls, in turn, calls the [IFormattable](xref:System.IFormattable) implementation of the `Temperature` class.</span></span>

```csharp
public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(22m);
      Console.WriteLine(Convert.ToString(temp1, new CultureInfo("ja-JP")));
      Console.WriteLine("Temperature: {0:K}", temp1);
      Console.WriteLine("Temperature: {0:F}", temp1);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), "Temperature: {0:F}", temp1));
   }
}
// The example displays the following output:
//       22.00°C
//       Temperature: 295.15°K
//       Temperature: 71.60°F
//       Temperature: 71,60°F
```

```vb
Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(22d)
      Console.WriteLine(Convert.ToString(temp1, New CultureInfo("ja-JP")))
      Console.WriteLine("Temperature: {0:K}", temp1)
      Console.WriteLine("Temperature: {0:F}", temp1)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), "Temperature: {0:F}", temp1)) 
   End Sub
End Module
' The example displays the following output:
'       22.00°C
'       Temperature: 295.15°K
'       Temperature: 71.60°F
'       Temperature: 71,60°F
```

## <a name="composite-formatting"></a><span data-ttu-id="ff003-365">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="ff003-365">Composite formatting</span></span>

<span data-ttu-id="ff003-366">Einige Methoden wie `String.Format` und `StringBuilder.AppendFormat` unterstützen die kombinierte Formatierung.</span><span class="sxs-lookup"><span data-stu-id="ff003-366">Some methods, such as `String.Format` and `StringBuilder.AppendFormat`, support composite formatting.</span></span> <span data-ttu-id="ff003-367">Eine kombinierte Formatzeichenfolge ist eine Vorlage, die verwendet wird, um eine einzelne Zeichenfolge zurückzugeben, die die Zeichenfolgendarstellung von 0 (null), einem oder mehreren Objekten beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="ff003-367">A composite format string is a kind of template that returns a single string that incorporates the string representation of zero, one, or more objects.</span></span> <span data-ttu-id="ff003-368">Jedes Objekt wird in der kombinierten Formatzeichenfolge durch ein indiziertes Formatelement dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-368">Each object is represented in the composite format string by an indexed format item.</span></span> <span data-ttu-id="ff003-369">Der Index des Formatelements entspricht der Position des Objekts, das es in der Parameterliste der Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-369">The index of the format item corresponds to the position of the object that it represents in the method's parameter list.</span></span> <span data-ttu-id="ff003-370">Indizes sind nullbasiert.</span><span class="sxs-lookup"><span data-stu-id="ff003-370">Indexes are zero-based.</span></span> <span data-ttu-id="ff003-371">Beispielsweise wird im folgenden Aufruf der `String.Format`-Methode das erste Formatelement `{0:D}` durch die Zeichenfolgendarstellung von `thatDate` ersetzt. Das zweite Formatelement `{1}` wird durch die Zeichenfolgendarstellung `item1` ersetzt, und das dritte Formatelement `{2:C2}` wird durch die Zeichenfolgendarstellung von `item1.Value` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="ff003-371">For example, in the following call to the `String.Format` method, the first format item, `{0:D}`, is replaced by the string representation of `thatDate`; the second format item, `{1}`, is replaced by the string representation of `item1`; and the third format item, `{2:C2}`, is replaced by the string representation of `item1.Value`.</span></span>

```csharp
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", 
                       thatDate, item1, item1.Value);
Console.WriteLine(result);                            
// The example displays output like the following if run on a system
// whose current culture is en-US:
//       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

```vb
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", _
                       thatDate, item1, item1.Value)
Console.WriteLine(result)                            
' The example displays output like the following if run on a system
' whose current culture is en-US:
'       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

<span data-ttu-id="ff003-372">Zusätzlich zum Ersetzen eines Formatelements durch die Zeichenfolgendarstellung seines entsprechenden Objekts können Sie mit Formatelementen auch Folgendes steuern:</span><span class="sxs-lookup"><span data-stu-id="ff003-372">In addition to replacing a format item with the string representation of its corresponding object, format items also let you control the following:</span></span> 

* <span data-ttu-id="ff003-373">Die spezifische Art, in der ein Objekt als Zeichenfolge dargestellt wird, wenn das Objekt die [IFormattable](xref:System.IFormattable)-Schnittstelle implementiert und Formatzeichenfolgen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ff003-373">The specific way in which an object is represented as a string, if the object implements the [IFormattable](xref:System.IFormattable) interface and supports format strings.</span></span> <span data-ttu-id="ff003-374">Zu diesem Zweck geben Sie nach dem Index des Formatelements einen Doppelpunkt (:) ein, gefolgt von einer gültigen Formatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ff003-374">You do this by following the format item's index with a : (colon) followed by a valid format string.</span></span> <span data-ttu-id="ff003-375">Im vorherigen Beispiel wurde hierzu ein Datumswert mit der Formatzeichenfolge „d“ (kurzes Datumsmuster) formatiert (z.B. `{0:d}`), und ein numerischer Wert wurde mit der Formatzeichenfolge „C2“ formatiert (z.B. `{2:C2}`, um die Zahl als Währungswert mit zwei Dezimalstellen darzustellen).</span><span class="sxs-lookup"><span data-stu-id="ff003-375">The previous example did this by formatting a date value with the "d" (short date pattern) format string (for example, `{0:d}`) and by formatting a numeric value with the "C2" format string (for example, `{2:C2}` to represent the number as a currency value with two fractional decimal digits).</span></span> 

* <span data-ttu-id="ff003-376">Die Breite des Felds, das die Zeichenfolgendarstellung des Objekts enthält, und die Ausrichtung der Zeichenfolgendarstellung in diesem Feld.</span><span class="sxs-lookup"><span data-stu-id="ff003-376">The width of the field that contains the object's string representation, and the alignment of the string representation in that field.</span></span> <span data-ttu-id="ff003-377">Hierzu geben Sie nach dem Index des Formatelements ein Komma (,) ein, gefolgt von der Feldbreite.</span><span class="sxs-lookup"><span data-stu-id="ff003-377">You do this by following the format item's index with a , (comma) followed the field width.</span></span> <span data-ttu-id="ff003-378">Die Zeichenfolge wird rechtsbündig in dem Feld ausgerichtet, wenn die Feldbreite ein positiver Wert ist, und linksbündig, wenn die Feldbreite ein negativer Wert ist.</span><span class="sxs-lookup"><span data-stu-id="ff003-378">The string is right-aligned in the field if the field width is a positive value, and it is left-aligned if the field width is a negative value.</span></span> <span data-ttu-id="ff003-379">Im folgenden Beispiel werden Datumswerte in einem 20 Zeichen breiten Feld linksbündig ausgerichtet, und Dezimalwerte mit einer Hinterkommastelle werden in einem 11 Zeichen breiten Feld rechtsbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="ff003-379">The following example left-aligns date values in a 20-character field, and it right-aligns decimal values with one fractional digit in an 11-character field.</span></span> 

```csharp
DateTime startDate = new DateTime(2015, 8, 28, 6, 0, 0);
decimal[] temps = { 73.452m, 68.98m, 72.6m, 69.24563m,
                   74.1m, 72.156m, 72.228m };
Console.WriteLine("{0,-20} {1,11}\n", "Date", "Temperature");
for (int ctr = 0; ctr < temps.Length; ctr++)
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps[ctr]);

// The example displays the following output:
//       Date                 Temperature
//
//       8/28/2015 6:00 AM           73.5
//       8/29/2015 6:00 AM           69.0
//       8/30/2015 6:00 AM           72.6
//       8/31/2015 6:00 AM           69.2
//       9/1/2015 6:00 AM            74.1
//       9/2/2015 6:00 AM            72.2
//       9/3/2015 6:00 AM            72.2
```

```vb
Dim startDate As New Date(2015, 8, 28, 6, 0, 0)
Dim temps() As Decimal = { 73.452, 68.98, 72.6, 69.24563,
                           74.1, 72.156, 72.228 }
Console.WriteLine("{0,-20} {1,11}", "Date", "Temperature")
Console.WriteLine()
For ctr As Integer = 0 To temps.Length - 1
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps(ctr))
Next
' The example displays the following output:
'       Date                 Temperature
'
'       8/28/2015 6:00 AM           73.5
'       8/29/2015 6:00 AM           69.0
'       8/30/2015 6:00 AM           72.6
'       8/31/2015 6:00 AM           69.2
'       9/1/2015 6:00 AM            74.1
'       9/2/2015 6:00 AM            72.2
'       9/3/2015 6:00 AM            72.2
```

<span data-ttu-id="ff003-380">Beachten Sie, dass, wenn sowohl die Ausrichtungszeichenfolge-Komponente als auch die Formatzeichenfolgen-Komponente vorhanden ist, die erste der letzteren vorausgeht (z. B. `{0,-20:g}`).</span><span class="sxs-lookup"><span data-stu-id="ff003-380">Note that, if both the alignment string component and the format string component are present, the former precedes the latter (for example, `{0,-20:g}`.</span></span> 

<span data-ttu-id="ff003-381">Weitere Informationen zur zusammengesetzten Formatierung finden Sie unter [Zusammengesetzte Formatierung](composite-format.md).</span><span class="sxs-lookup"><span data-stu-id="ff003-381">For more information about composite formatting, see [Composite formatting](composite-format.md).</span></span>

## <a name="custom-formatting-with-icustomformatter"></a><span data-ttu-id="ff003-382">Benutzerdefinierte Formatierung mit ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="ff003-382">Custom formatting with ICustomFormatter</span></span>

<span data-ttu-id="ff003-383">Zwei zusammengesetzte Formatierungsmethoden, [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object[])) und [StringBuilder.AppendFormat(IFormatProvider, String, Object[])](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)), enthalten einen Parameter für den Formatanbieter, der eine benutzerdefinierte Formatierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ff003-383">Two composite formatting methods, [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object[])) and [StringBuilder.AppendFormat(IFormatProvider, String, Object[])](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)), include a format provider parameter that supports custom formatting.</span></span> <span data-ttu-id="ff003-384">Wenn eine dieser Formatierungsmethoden aufgerufen wird, übergibt sie ein [Type](xref:System.Type)-Objekt, das eine [ICustomFormatter](xref:System.ICustomFormatter)-Schnittstelle für die `GetFormat`-Methode des Formatanbieters darstellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-384">When either of these formatting methods is called, it passes a [Type](xref:System.Type) object that represents an [ICustomFormatter](xref:System.ICustomFormatter) interface to the format provider’s `GetFormat` method.</span></span> <span data-ttu-id="ff003-385">Die `GetFormat`-Methode ist dann dafür zuständig, die [ICustomFormatter](xref:System.ICustomFormatter)-Implementierung zurückzugeben, die die benutzerdefinierte Formatierung bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-385">The `GetFormat` method is then responsible for returning the [ICustomFormatter](xref:System.ICustomFormatter) implementation that provides custom formatting.</span></span>

<span data-ttu-id="ff003-386">Die [ICustomFormatter](xref:System.ICustomFormatter)-Schnittstelle verfügt über eine einzelne Methode, [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)), die von einer zusammengesetzten Formatierungsmethode automatisch einmal für jedes Formatelement in einer zusammengesetzten Formatzeichenfolge aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ff003-386">The [ICustomFormatter](xref:System.ICustomFormatter) interface has a single method, [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)), that is called automatically by a composite formatting method, once for each format item in a composite format string.</span></span> <span data-ttu-id="ff003-387">Die [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider))-Methode verfügt über drei Parameter: eine Formatzeichenfolge, die das *formatString*-Argument in einem Formatelement darstellt, ein Objekt zum Formatieren und ein [IFormatProvider](xref:System.IFormatProvider)-Objekt, das Formatierungsdienste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ff003-387">The [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method has three parameters: a format string, which represents the *formatString* argument in a format item, an object to format, and an [IFormatProvider](xref:System.IFormatProvider) object that provides formatting services.</span></span> <span data-ttu-id="ff003-388">In der Regel implementiert die Klasse, die [ICustomFormatter](xref:System.ICustomFormatter) implementiert, auch [IFormatProvider](xref:System.IFormatProvider). Dieser letzte Parameter stellt daher einen Verweis auf die benutzerdefinierte Formatierungsklasse selbst dar.</span><span class="sxs-lookup"><span data-stu-id="ff003-388">Typically, the class that implements [ICustomFormatter](xref:System.ICustomFormatter) also implements [IFormatProvider](xref:System.IFormatProvider), so this last parameter is a reference to the custom formatting class itself.</span></span> <span data-ttu-id="ff003-389">Die Methode gibt eine benutzerdefinierte formatierte Zeichenfolgendarstellung des Objekts zurück, das formatiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff003-389">The method returns a custom formatted string representation of the object to be formatted.</span></span> <span data-ttu-id="ff003-390">Wenn die Methode das Objekt nicht formatieren kann, sollte ein NULL-Verweis zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-390">If the method cannot format the object, it should return a null reference.</span></span>

<span data-ttu-id="ff003-391">Im folgenden Beispiel wird eine [ICustomFormatter](xref:System.ICustomFormatter)-Implementierung mit dem Namen `ByteByByteFormatter` bereitgestellt, die ganzzahlige Werte als Sequenz von zweistelligen Hexadezimalwerten gefolgt von einem Leerzeichen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ff003-391">The following example provides an [ICustomFormatter](xref:System.ICustomFormatter) implementation named `ByteByByteFormatter` that displays integer values as a sequence of two-digit hexadecimal values followed by a space.</span></span>

```csharp
public class ByteByByteFormatter : IFormatProvider, ICustomFormatter
{
   public object GetFormat(Type formatType)
   { 
      if (formatType == typeof(ICustomFormatter))
         return this;
      else
         return null;
   }

   public string Format(string format, object arg, 
                          IFormatProvider formatProvider)
   {   
      if (! formatProvider.Equals(this)) return null;

      // Handle only hexadecimal format string.
      if (! format.StartsWith("X")) return null;

      byte[] bytes;
      string output = null;

      // Handle only integral types.
      if (arg is Byte) 
         bytes = BitConverter.GetBytes((Byte) arg);
      else if (arg is Int16)
         bytes = BitConverter.GetBytes((Int16) arg);
      else if (arg is Int32)
         bytes = BitConverter.GetBytes((Int32) arg);
      else if (arg is Int64)   
         bytes = BitConverter.GetBytes((Int64) arg);
      else if (arg is SByte)
         bytes = BitConverter.GetBytes((SByte) arg);
      else if (arg is UInt16)
         bytes = BitConverter.GetBytes((UInt16) arg);
      else if (arg is UInt32)
         bytes = BitConverter.GetBytes((UInt32) arg);
      else if (arg is UInt64)
         bytes = BitConverter.GetBytes((UInt64) arg);
      else
         return null;

      for (int ctr = bytes.Length - 1; ctr >= 0; ctr--)
         output += String.Format("{0:X2} ", bytes[ctr]);   

      return output.Trim();
   }
}
```

```vb
Public Class ByteByByteFormatter : Implements IFormatProvider, ICustomFormatter
   Public Function GetFormat(formatType As Type) As Object _
                   Implements IFormatProvider.GetFormat
      If formatType Is GetType(ICustomFormatter) Then
         Return Me
      Else
         Return Nothing
      End If
   End Function

   Public Function Format(fmt As String, arg As Object, 
                          formatProvider As IFormatProvider) As String _
                          Implements ICustomFormatter.Format

      If Not formatProvider.Equals(Me) Then Return Nothing

      ' Handle only hexadecimal format string.
      If Not fmt.StartsWith("X") Then 
            Return Nothing
      End If

      ' Handle only integral types.
      If Not typeof arg Is Byte AndAlso
         Not typeof arg Is Int16 AndAlso
         Not typeof arg Is Int32 AndAlso
         Not typeof arg Is Int64 AndAlso
         Not typeof arg Is SByte AndAlso
         Not typeof arg Is UInt16 AndAlso
         Not typeof arg Is UInt32 AndAlso
         Not typeof arg Is UInt64 Then _
            Return Nothing

      Dim bytes() As Byte = BitConverter.GetBytes(arg)
      Dim output As String = Nothing

      For ctr As Integer = bytes.Length - 1 To 0 Step -1
         output += String.Format("{0:X2} ", bytes(ctr))   
      Next

      Return output.Trim()
   End Function
End Class
```

<span data-ttu-id="ff003-392">Im folgenden Beispiel werden mit der `ByteByByteFormatter`-Klasse Ganzzahlwerte formatiert.</span><span class="sxs-lookup"><span data-stu-id="ff003-392">The following example uses the `ByteByByteFormatter` class to format integer values.</span></span> <span data-ttu-id="ff003-393">Beachten Sie, dass die [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider))-Methode im zweiten Aufruf der [String.Format(IFormatProvider, String, Object[])](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider))-Methode mehr als einmal aufgerufen wird und dass der [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Standardanbieter im dritten Methodenaufruf verwendet wird, da die `.ByteByByteFormatter.Format`-Methode die Formatzeichenfolge „N0“ nicht erkennt und einen NULL-Verweis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ff003-393">Note that the [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method is called more than once in the second [String.Format(IFormatProvider, String, Object[])](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method call, and that the default [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) provider is used in the third method call because the `.ByteByByteFormatter.Format` method does not recognize the "N0" format string and returns a null reference.</span></span>

```csharp
public class Example
{
   public static void Main()
   {
      long value = 3210662321; 
      byte value1 = 214;
      byte value2 = 19;

      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X}", value));
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 & value2));                                
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0,10:N0}", value));
   }
}
// The example displays the following output:
//       00 00 00 00 BF 5E D1 B1
//       00 D6 And 00 13 = 00 12 (018)
//       3,210,662,321
```

```vb
Public Module Example
   Public Sub Main()
      Dim value As Long = 3210662321 
      Dim value1 As Byte = 214
      Dim value2 As Byte = 19

      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X}", value)))
      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 And value2)))                                
      Console.WriteLine(String.Format(New ByteByByteFormatter(), "{0,10:N0}", value))
   End Sub
End Module
' The example displays the following output:
'       00 00 00 00 BF 5E D1 B1
'       00 D6 And 00 13 = 00 12 (018)
'       3,210,662,321
```

## <a name="related-topics"></a><span data-ttu-id="ff003-394">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ff003-394">Related topics</span></span>

<span data-ttu-id="ff003-395">Titel</span><span class="sxs-lookup"><span data-stu-id="ff003-395">Title</span></span> | <span data-ttu-id="ff003-396">Definition</span><span class="sxs-lookup"><span data-stu-id="ff003-396">Definition</span></span>
----- | ----------
[<span data-ttu-id="ff003-397">Standard-Zahlenformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-397">Standard numeric format strings</span></span>](standard-numeric.md) | <span data-ttu-id="ff003-398">Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von numerischen Werten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-398">Describes standard format strings that create commonly used string representations of numeric values.</span></span> 
[<span data-ttu-id="ff003-399">Benutzerdefinierte Zahlenformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-399">Custom numeric format strings</span></span>](custom-numeric.md) | <span data-ttu-id="ff003-400">Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für numerische Werte erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-400">Describes custom format strings that create application-specific formats for numeric values.</span></span>
[<span data-ttu-id="ff003-401">Standardformatzeichenfolgen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ff003-401">Standard date and time format strings</span></span>](standard-datetime.md) |  <span data-ttu-id="ff003-402">Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von [DateTime](xref:System.DateTime)-Werten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-402">Describes standard format strings that create commonly used string representations of [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="ff003-403">Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ff003-403">Custom date and time format strings</span></span>](custom-datetime.md) | <span data-ttu-id="ff003-404">Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für [DateTime](xref:System.DateTime)-Werte erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-404">Describes custom format strings that create application-specific formats for [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="ff003-405">TimeSpan-Standardformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-405">Standard TimeSpan format strings</span></span>](standard-timespan.md) | <span data-ttu-id="ff003-406">Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen häufig verwendete Zeichenfolgenentsprechungen von Zeitintervallen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-406">Describes standard format strings that create commonly used string representations of time intervals.</span></span>
[<span data-ttu-id="ff003-407">Benutzerdefinierte TimeSpan-Formatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-407">Custom TimeSpan format strings</span></span>](custom-timespan.md) | <span data-ttu-id="ff003-408">Beschreibt benutzerdefinierte Formatzeichenfolgen, die anwendungsspezifische Formate für Zeitintervalle erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff003-408">Describes custom format strings that create application-specific formats for time intervals.</span></span>
[<span data-ttu-id="ff003-409">Enumerationsformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-409">Enumeration format strings</span></span>](enumeration-format.md) | <span data-ttu-id="ff003-410">Beschreibt als Standard verwendete Formatzeichenfolgen, mit denen Zeichenfolgenentsprechungen von Enumerationswerten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-410">Describes standard format strings that are used to create string representations of enumeration values.</span></span>
[<span data-ttu-id="ff003-411">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="ff003-411">Composite formatting</span></span>](composite-format.md) | <span data-ttu-id="ff003-412">Beschreibt die Einbettung eines oder mehrerer formatierter Werte in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ff003-412">Describes how to embed one or more formatted values in a string.</span></span> <span data-ttu-id="ff003-413">Die Zeichenfolge kann anschließend in der Konsole angezeigt oder in einen Stream geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-413">The string can subsequently be displayed on the console or written to a stream.</span></span>
[<span data-ttu-id="ff003-414">Durchführen von Formatierungsvorgängen</span><span class="sxs-lookup"><span data-stu-id="ff003-414">Performing formatting operations</span></span>](performing-formatting-operations.md) | <span data-ttu-id="ff003-415">Enthält Themen, in denen schrittweise Anleitungen zum Ausführen bestimmter Formatierungsvorgänge vorgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-415">Lists topics that provide step-by-step instructions for performing specific formatting operations.</span></span>
[<span data-ttu-id="ff003-416">Analysieren von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ff003-416">Parsing strings</span></span>](parsing-strings.md) | <span data-ttu-id="ff003-417">Beschreibt, wie Objekte mit den Werten initialisiert werden, die durch Zeichenfolgenentsprechungen dieser Objekte beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ff003-417">Describes how to initialize objects to the values described by string representations of those objects.</span></span> <span data-ttu-id="ff003-418">Das Verarbeiten ist die Umkehroperation zum Formatieren.</span><span class="sxs-lookup"><span data-stu-id="ff003-418">Parsing is the inverse operation of formatting.</span></span>

## <a name="reference"></a><span data-ttu-id="ff003-419">Verweis</span><span class="sxs-lookup"><span data-stu-id="ff003-419">Reference</span></span>

[<span data-ttu-id="ff003-420">System.IFormattable</span><span class="sxs-lookup"><span data-stu-id="ff003-420">System.IFormattable</span></span>](xref:System.IFormattable)

[<span data-ttu-id="ff003-421">System.IFormatProvider</span><span class="sxs-lookup"><span data-stu-id="ff003-421">System.IFormatProvider</span></span>](xref:System.IFormatProvider)

[<span data-ttu-id="ff003-422">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="ff003-422">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)

