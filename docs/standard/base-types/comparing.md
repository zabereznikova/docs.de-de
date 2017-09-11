---
title: Vergleichen von Zeichenfolgen
description: Vergleichen von Zeichenfolgen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 920ee5e8-3d61-4941-b5af-fc50eaee427c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 47ee37886fa2662a89730e9d52ee04987e37da2f
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="comparing-strings"></a><span data-ttu-id="23a5e-104">Vergleichen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="23a5e-104">Comparing strings</span></span>

<span data-ttu-id="23a5e-105">.NET stellt mehrere Methoden bereit, um Werte von Zeichenfolgen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="23a5e-105">.NET provides several methods to compare the values of strings.</span></span> <span data-ttu-id="23a5e-106">In der folgenden Tabelle werden die Methoden zum Vergleichen von Werten aufgeführt und beschrieben.</span><span class="sxs-lookup"><span data-stu-id="23a5e-106">The following table lists and describes the value-comparison methods.</span></span>

<span data-ttu-id="23a5e-107">Methodenname</span><span class="sxs-lookup"><span data-stu-id="23a5e-107">Method name</span></span> | <span data-ttu-id="23a5e-108">Verwendung</span><span class="sxs-lookup"><span data-stu-id="23a5e-108">Use</span></span>
----------- | ---
<span data-ttu-id="23a5e-109">[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="23a5e-109">[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))</span></span> | <span data-ttu-id="23a5e-110">Vergleicht die Werte zweier Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="23a5e-110">Compares the values of two strings.</span></span> <span data-ttu-id="23a5e-111">Gibt einen Ganzzahlwert zurück.</span><span class="sxs-lookup"><span data-stu-id="23a5e-111">Returns an integer value.</span></span>
<span data-ttu-id="23a5e-112">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="23a5e-112">[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))</span></span> | <span data-ttu-id="23a5e-113">Vergleicht zwei Zeichenfolgen, ohne die Einstellungen der lokalen Kultur zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="23a5e-113">Compares two strings without regard to local culture.</span></span> <span data-ttu-id="23a5e-114">Gibt einen Ganzzahlwert zurück.</span><span class="sxs-lookup"><span data-stu-id="23a5e-114">Returns an integer value.</span></span>
<span data-ttu-id="23a5e-115">[String.CompareTo](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="23a5e-115">[String.CompareTo](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="23a5e-116">Vergleicht das aktuelle Zeichenfolgenobjekt mit einer anderen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="23a5e-116">Compares the current string object to another string.</span></span> <span data-ttu-id="23a5e-117">Gibt einen Ganzzahlwert zurück.</span><span class="sxs-lookup"><span data-stu-id="23a5e-117">Returns an integer value.</span></span>
<span data-ttu-id="23a5e-118">[String.StartsWith](xref:System.String.StartsWith(System.String))</span><span class="sxs-lookup"><span data-stu-id="23a5e-118">[String.StartsWith](xref:System.String.StartsWith(System.String))</span></span> | <span data-ttu-id="23a5e-119">Stellt fest, ob eine Zeichenfolge mit der übergebenen Zeichenfolge beginnt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-119">Determines whether a string begins with the string passed.</span></span> <span data-ttu-id="23a5e-120">Gibt einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="23a5e-120">Returns a Boolean value.</span></span>
<span data-ttu-id="23a5e-121">[String.EndsWith](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="23a5e-121">[String.EndsWith](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="23a5e-122">Stellt fest, ob eine Zeichenfolge mit der übergebenen Zeichenfolge endet.</span><span class="sxs-lookup"><span data-stu-id="23a5e-122">Determines whether a string ends with the string passed.</span></span> <span data-ttu-id="23a5e-123">Gibt einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="23a5e-123">Returns a Boolean value.</span></span>
<span data-ttu-id="23a5e-124">[String.Equals](xref:System.String.CompareTo(System.String))</span><span class="sxs-lookup"><span data-stu-id="23a5e-124">[String.Equals](xref:System.String.CompareTo(System.String))</span></span> | <span data-ttu-id="23a5e-125">Stellt fest, ob zwei Zeichenfolgen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="23a5e-125">Determines whether two strings are the same.</span></span> <span data-ttu-id="23a5e-126">Gibt einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="23a5e-126">Returns a Boolean value.</span></span>
<span data-ttu-id="23a5e-127">[String.IndexOf](xref:System.String.IndexOf(System.Char))</span><span class="sxs-lookup"><span data-stu-id="23a5e-127">[String.IndexOf](xref:System.String.IndexOf(System.Char))</span></span> | <span data-ttu-id="23a5e-128">Gibt ausgehend vom Anfang der zu überprüfenden Zeichenfolge die Indexposition eines Zeichens oder einer Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="23a5e-128">Returns the index position of a character or string, starting from the beginning of the string you are examining.</span></span> <span data-ttu-id="23a5e-129">Gibt einen Ganzzahlwert zurück.</span><span class="sxs-lookup"><span data-stu-id="23a5e-129">Returns an integer value.</span></span>
<span data-ttu-id="23a5e-130">[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char))</span><span class="sxs-lookup"><span data-stu-id="23a5e-130">[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char))</span></span> | <span data-ttu-id="23a5e-131">Gibt ausgehend vom Ende der zu überprüfenden Zeichenfolge die Indexposition eines Zeichens oder einer Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="23a5e-131">Returns the index position of a character or string, starting from the end of the string you are examining.</span></span> <span data-ttu-id="23a5e-132">Gibt einen Ganzzahlwert zurück.</span><span class="sxs-lookup"><span data-stu-id="23a5e-132">Returns an integer value.</span></span>

## <a name="compare"></a><span data-ttu-id="23a5e-133">Vergleichen</span><span class="sxs-lookup"><span data-stu-id="23a5e-133">Compare</span></span>

<span data-ttu-id="23a5e-134">Die statische [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode bietet umfassende Möglichkeiten zum Vergleichen von zwei Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="23a5e-134">The static [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method provides a thorough way of comparing two strings.</span></span> <span data-ttu-id="23a5e-135">Bei dieser Methode werden unterschiedliche Kulturen berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-135">This method is culturally aware.</span></span> <span data-ttu-id="23a5e-136">Sie können diese Funktion verwenden, um zwei Zeichenfolgen oder zwei untergeordnete Zeichenfolgen zweier Zeichenfolgen miteinander zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="23a5e-136">You can use this function to compare two strings or substrings of two strings.</span></span> <span data-ttu-id="23a5e-137">Zusätzlich sind Überladungen verfügbar, mit denen die Groß-/Kleinschreibung sowie abweichende Kulturen berücksichtigt bzw. ignoriert werden können.</span><span class="sxs-lookup"><span data-stu-id="23a5e-137">Additionally, overloads are provided that regard or disregard case and cultural variance.</span></span> <span data-ttu-id="23a5e-138">In der folgenden Tabelle sind die drei ganzzahligen Werte aufgeführt, die von dieser Methode zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="23a5e-138">The following table shows the three integer values that this method might return.</span></span> 

<span data-ttu-id="23a5e-139">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="23a5e-139">Return value</span></span> | <span data-ttu-id="23a5e-140">Bedingung</span><span class="sxs-lookup"><span data-stu-id="23a5e-140">Condition</span></span>
------------ | ---------
<span data-ttu-id="23a5e-141">Eine negative ganze Zahl</span><span class="sxs-lookup"><span data-stu-id="23a5e-141">A negative integer</span></span> | <span data-ttu-id="23a5e-142">Die erste Zeichenfolge steht in der Sortierreihenfolge vor der zweiten Zeichenfolge, oder die erste Zeichenfolge ist `null`.</span><span class="sxs-lookup"><span data-stu-id="23a5e-142">The first string precedes the second string in the sort order, or the first string is `null`.</span></span>
<span data-ttu-id="23a5e-143">0</span><span class="sxs-lookup"><span data-stu-id="23a5e-143">0</span></span> | <span data-ttu-id="23a5e-144">Die erste Zeichenfolge und die zweite Zeichenfolge sind gleich, oder beide Zeichenfolgen sind `null`.</span><span class="sxs-lookup"><span data-stu-id="23a5e-144">The first string and the second string are equal, or both strings are `null`.</span></span>
<span data-ttu-id="23a5e-145">Eine positive ganze Zahl oder 1.</span><span class="sxs-lookup"><span data-stu-id="23a5e-145">A positive integer, or 1</span></span> | <span data-ttu-id="23a5e-146">Die erste Zeichenfolge folgt in der Sortierreihenfolge der zweiten Zeichenfolge, oder die zweite Zeichenfolge ist NULL.</span><span class="sxs-lookup"><span data-stu-id="23a5e-146">The first string follows the second string in the sort order, or the second string is null.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="23a5e-147">Die [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode ist hauptsächlich für die Anordnung oder Sortierung von Zeichenfolgen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-147">The [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="23a5e-148">Sie sollten die [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode nicht verwenden, um einen Übereinstimmungstest auszuführen (also um explizit nach dem Rückgabewert 0 zu suchen, ohne dass dabei berücksichtigt wird, ob eine Zeichenfolge kleiner oder größer als die andere ist).</span><span class="sxs-lookup"><span data-stu-id="23a5e-148">You should not use the [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="23a5e-149">Um zu bestimmen, ob zwei Zeichenfolgen gleich sind, verwenden Sie stattdessen die [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison))-Methode.</span><span class="sxs-lookup"><span data-stu-id="23a5e-149">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="23a5e-150">Im folgenden Beispiel wird die [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode verwendet, um das Verhältnis der Werte von zwei Zeichenfolgen festzustellen.</span><span class="sxs-lookup"><span data-stu-id="23a5e-150">The following example uses the [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to determine the relative values of two strings.</span></span>

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.Compare(string1, "Hello World?"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.Compare(string1, "Hello World?"))
```

<span data-ttu-id="23a5e-151">In diesem Beispiel wird `-1` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-151">This example displays `-1` to the console.</span></span>

## <a name="compareordinal"></a><span data-ttu-id="23a5e-152">CompareOrdinal</span><span class="sxs-lookup"><span data-stu-id="23a5e-152">CompareOrdinal</span></span>

<span data-ttu-id="23a5e-153">Mithilfe der [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode werden zwei Zeichenfolgenobjekte verglichen, ohne dass die Einstellungen der lokalen Kultur berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="23a5e-153">The [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method compares two string objects without considering the local culture.</span></span> <span data-ttu-id="23a5e-154">Die Rückgabewerte dieser Methode stimmen mit den Werten überein, die von der in der vorherigen Tabelle beschriebenen `Compare`-Methode zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="23a5e-154">The return values of this method are identical to the values returned by the `Compare` method in the previous table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23a5e-155">Die [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode ist hauptsächlich für die Anordnung oder Sortierung von Zeichenfolgen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-155">The [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="23a5e-156">Sie sollten die [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32))-Methode nicht verwenden, um einen Übereinstimmungstest auszuführen (also um explizit nach dem Rückgabewert 0 zu suchen, ohne dass dabei berücksichtigt wird, ob eine Zeichenfolge kleiner oder größer als die andere ist).</span><span class="sxs-lookup"><span data-stu-id="23a5e-156">You should not use the [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="23a5e-157">Um zu bestimmen, ob zwei Zeichenfolgen gleich sind, verwenden Sie stattdessen die [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison))-Methode.</span><span class="sxs-lookup"><span data-stu-id="23a5e-157">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="23a5e-158">Im folgenden Beispiel wird die `CompareOrdinal`-Methode verwendet, um die Werte von zwei Zeichenfolgen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="23a5e-158">The following example uses the `CompareOrdinal` method to compare the values of two strings.</span></span>

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"))
```

<span data-ttu-id="23a5e-159">In diesem Beispiel wird `-32` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-159">This example displays `-32` to the console.</span></span>

## <a name="compareto"></a><span data-ttu-id="23a5e-160">CompareTo</span><span class="sxs-lookup"><span data-stu-id="23a5e-160">CompareTo</span></span>

<span data-ttu-id="23a5e-161">Mit der [String.CompareTo](xref:System.String.CompareTo(System.String))-Methode wird die im aktuellen Zeichenfolgenobjekt gekapselte Zeichenfolge mit einer anderen Zeichenfolge oder einem anderen Objekt verglichen.</span><span class="sxs-lookup"><span data-stu-id="23a5e-161">The [String.CompareTo](xref:System.String.CompareTo(System.String)) method compares the string that the current string object encapsulates to another string or object.</span></span> <span data-ttu-id="23a5e-162">Die Rückgabewerte dieser Methode stimmen mit den Werten überein, die von der in der vorherigen Tabelle beschriebenen `String.Compare`-Methode zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="23a5e-162">The return values of this method are identical to the values returned by the `String.Compare` method in the previous table.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23a5e-163">Die [String.CompareTo](xref:System.String.CompareTo(System.String))-Methode ist hauptsächlich für die Anordnung oder Sortierung von Zeichenfolgen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-163">The [String.CompareTo](xref:System.String.CompareTo(System.String)) method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="23a5e-164">Sie sollten die [String.CompareTo](xref:System.String.CompareTo(System.String))-Methode nicht verwenden, um einen Übereinstimmungstest auszuführen (also um explizit nach dem Rückgabewert 0 zu suchen, ohne dass dabei berücksichtigt wird, ob eine Zeichenfolge kleiner oder größer als die andere ist).</span><span class="sxs-lookup"><span data-stu-id="23a5e-164">You should not use the [String.CompareTo](xref:System.String.CompareTo(System.String)) method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="23a5e-165">Um zu bestimmen, ob zwei Zeichenfolgen gleich sind, verwenden Sie stattdessen die [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison))-Methode.</span><span class="sxs-lookup"><span data-stu-id="23a5e-165">Instead, to determine whether two strings are equal, use the [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)) method.</span></span>

<span data-ttu-id="23a5e-166">Im folgenden Beispiel wird die `String.CompareTo`-Methode verwendet, um das `string1`-Objekt mit dem `string2`-Objekt zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="23a5e-166">The following example uses the `String.CompareTo` method to compare the `string1` object to the `string2` object.</span></span>

```csharp
string string1 = "Hello World";
string string2 = "Hello World!";
int MyInt = string1.CompareTo(string2);
Console.WriteLine( MyInt );
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World!"
Dim MyInt As Integer = string1.CompareTo(string2)
Console.WriteLine(MyInt)
```

<span data-ttu-id="23a5e-167">In diesem Beispiel wird `-1` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-167">This example displays `-1` to the console.</span></span>

## <a name="equals"></a><span data-ttu-id="23a5e-168">gleich</span><span class="sxs-lookup"><span data-stu-id="23a5e-168">Equals</span></span>

<span data-ttu-id="23a5e-169">Mit der [String.Equals](xref:System.String.CompareTo(System.String))-Methode lässt sich auf einfache Weise feststellen, ob zwei Zeichenfolgen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="23a5e-169">The [String.Equals](xref:System.String.CompareTo(System.String)) method can easily determine if two strings are the same.</span></span> <span data-ttu-id="23a5e-170">Diese Methode, bei der die Groß-/Kleinschreibung beachtet wird, gibt den booleschen Wert `true` oder `false` zurück.</span><span class="sxs-lookup"><span data-stu-id="23a5e-170">This case-sensitive method returns a `true` or `false` Boolean value.</span></span> <span data-ttu-id="23a5e-171">Wie das nächste Beispiel zeigt, kann die Methode einer bestehenden Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="23a5e-171">It can be used from an existing class, as illustrated in the next example.</span></span> <span data-ttu-id="23a5e-172">Im folgenden Beispiel wird mithilfe der `Equals`-Methode festgestellt, ob ein Zeichenfolgenobjekt den Ausdruck „Hello World“ enthält.</span><span class="sxs-lookup"><span data-stu-id="23a5e-172">The following example uses the `Equals` method to determine whether a string object contains the phrase "Hello World".</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.Equals("Hello World"));
```

```vb
Dim string1 As String = "Hello World"
Console.WriteLine(string1.Equals("Hello World"))
```

<span data-ttu-id="23a5e-173">In diesem Beispiel wird `true` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-173">This example displays `true` to the console.</span></span>

<span data-ttu-id="23a5e-174">Diese Methode kann auch als statische Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="23a5e-174">This method can also be used as a static method.</span></span> <span data-ttu-id="23a5e-175">Im folgenden Beispiel werden zwei Zeichenfolgenobjekte mithilfe einer statischen Methode verglichen.</span><span class="sxs-lookup"><span data-stu-id="23a5e-175">The following example compares two string objects using a static method.</span></span>

```csharp
string string1 = "Hello World";
string string2 = "Hello World";
Console.WriteLine(String.Equals(string1, string2));
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World"
Console.WriteLine(String.Equals(string1, string2))
```

<span data-ttu-id="23a5e-176">In diesem Beispiel wird `true` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-176">This example displays `true` to the console.</span></span>

## <a name="startswith-and-endswith"></a><span data-ttu-id="23a5e-177">"StartsWith" und "EndsWith"</span><span class="sxs-lookup"><span data-stu-id="23a5e-177">StartsWith and EndsWith</span></span>

<span data-ttu-id="23a5e-178">Mit der [String.StartsWith](xref:System.String.StartsWith(System.String))-Methode können Sie feststellen, ob ein Zeichenfolgenobjekt mit den gleichen Zeichen beginnt, die eine andere Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="23a5e-178">You can use the [String.StartsWith](xref:System.String.StartsWith(System.String)) method to determine whether a string object begins with the same characters that encompass another string.</span></span> <span data-ttu-id="23a5e-179">Diese Methode, bei der die Groß-/Kleinschreibung beachtet wird, gibt `true` zurück, wenn das aktuelle Zeichenfolgenobjekt mit der übergebenen Zeichenfolge beginnt, und sie gibt `false` zurück, wenn dies nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="23a5e-179">This case-sensitive method returns `true` if the current string object begins with the passed string and `false` if it does not.</span></span> <span data-ttu-id="23a5e-180">Im folgenden Beispiel wird mithilfe dieser Methode festgestellt, ob ein Zeichenfolgenobjekt mit "Hello" beginnt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-180">The following example uses this method to determine if a string object begins with "Hello".</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.StartsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.StartsWith("Hello"))
```

<span data-ttu-id="23a5e-181">In diesem Beispiel wird `true` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-181">This example displays `true` to the console.</span></span>

<span data-ttu-id="23a5e-182">Bei der [String.EndsWith](xref:System.String.CompareTo(System.String))-Methode wird eine übergebene Zeichenfolge mit den Zeichen am Ende des aktuellen Zeichenfolgenobjekts verglichen.</span><span class="sxs-lookup"><span data-stu-id="23a5e-182">The [String.EndsWith](xref:System.String.CompareTo(System.String)) method compares a passed string to the characters that exist at the end of the current string object.</span></span> <span data-ttu-id="23a5e-183">Auch sie gibt einen booleschen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="23a5e-183">It also returns a Boolean value.</span></span> <span data-ttu-id="23a5e-184">Im folgenden Beispiel wird das Ende einer Zeichenfolge mithilfe der `EndsWith`-Methode überprüft.</span><span class="sxs-lookup"><span data-stu-id="23a5e-184">The following example checks the end of a string using the `EndsWith` method.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.EndsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.EndsWith("Hello"))
```

<span data-ttu-id="23a5e-185">In diesem Beispiel wird `false` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-185">This example displays `false` to the console.</span></span>

## <a name="indexof-and-lastindexof"></a><span data-ttu-id="23a5e-186">"IndexOf" und "LastIndexOf"</span><span class="sxs-lookup"><span data-stu-id="23a5e-186">IndexOf and LastIndexOf</span></span>

<span data-ttu-id="23a5e-187">Mit der [String.IndexOf](xref:System.String.IndexOf(System.Char))-Methode können Sie die Position feststellen, an der ein bestimmtes Zeichen in einer Zeichenfolge erstmalig vorkommt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-187">You can use the [String.IndexOf](xref:System.String.IndexOf(System.Char)) method to determine the position of the first occurrence of a particular character within a string.</span></span> <span data-ttu-id="23a5e-188">Bei dieser Methode, die die Groß-/Kleinschreibung beachtet, beginnt die Zählung am Anfang einer Zeichenfolge; sie gibt die Position eines übergebenen Zeichens auf der Grundlage eines nullbasierten Indizes zurück.</span><span class="sxs-lookup"><span data-stu-id="23a5e-188">This case-sensitive method starts counting from the beginning of a string and returns the position of a passed character using a zero-based index.</span></span> <span data-ttu-id="23a5e-189">Wenn das Zeichen nicht gefunden wird, wird der Wert –1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="23a5e-189">If the character cannot be found, a value of –1 is returned.</span></span>

<span data-ttu-id="23a5e-190">Im folgenden Beispiel wird die `IndexOf`-Methode verwendet, um in einer Zeichenfolge nach dem ersten Vorkommnis des Zeichens '`l`' zu suchen.</span><span class="sxs-lookup"><span data-stu-id="23a5e-190">The following example uses the `IndexOf` method to search for the first occurrence of the '`l`' character in a string.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.IndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.IndexOf("l"))
```

<span data-ttu-id="23a5e-191">In diesem Beispiel wird `2` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-191">This example displays `2` to the console.</span></span>

<span data-ttu-id="23a5e-192">Die [String.LastIndexOf](xref:System.String.LastIndexOf(System.Char))-Methode ist vergleichbar mit der `String.IndexOf`-Methode, außer dass sie die Position zurückgibt, an der ein bestimmtes Zeichen innerhalb einer Zeichenfolge letztmalig vorkommt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-192">The [String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) method is similar to the `String.IndexOf` method except that it returns the position of the last occurrence of a particular character within a string.</span></span> <span data-ttu-id="23a5e-193">Sie beachtet die Groß-/Kleinschreibung und verwendet einen nullbasierten Index.</span><span class="sxs-lookup"><span data-stu-id="23a5e-193">It is case-sensitive and uses a zero-based index.</span></span> 

<span data-ttu-id="23a5e-194">Im folgenden Beispiel wird die `LastIndexOf`-Methode verwendet, um in einer Zeichenfolge nach dem letzten Vorkommnis des Zeichens '`l`' zu suchen.</span><span class="sxs-lookup"><span data-stu-id="23a5e-194">The following example uses the `LastIndexOf` method to search for the last occurrence of the '`l`' character in a string.</span></span>

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.LastIndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.LastIndexOf("l"))
```

<span data-ttu-id="23a5e-195">In diesem Beispiel wird `9` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-195">This example displays `9` to the console.</span></span>

<span data-ttu-id="23a5e-196">Beide Methoden sind hilfreich, wenn sie in Verbindung mit der [String.Remove](xref:System.String.Remove(System.Int32))-Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="23a5e-196">Both methods are useful when used in conjunction with the [String.Remove](xref:System.String.Remove(System.Int32)) method.</span></span> <span data-ttu-id="23a5e-197">Sie können die `IndexOf`-Methode oder die `LastIndexOf`-Methode verwenden, um die Position eines Zeichens abzurufen, und diese Position dann an die `Remove method` übergeben, um ein Zeichen oder ein Wort zu entfernen, das mit diesem Zeichen beginnt.</span><span class="sxs-lookup"><span data-stu-id="23a5e-197">You can use either the `IndexOf` or `LastIndexOf` methods to retrieve the position of a character, and then supply that position to the `Remove method` in order to remove a character or a word that begins with that character.</span></span>

## <a name="see-also"></a><span data-ttu-id="23a5e-198">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23a5e-198">See Also</span></span>

[<span data-ttu-id="23a5e-199">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="23a5e-199">Basic string operations</span></span>](basic-string-operations.md)













