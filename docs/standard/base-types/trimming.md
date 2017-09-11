---
title: Herausnehmen und Entfernen von Zeichen aus Zeichenfolgen
description: Herausnehmen und Entfernen von Zeichen aus Zeichenfolgen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 95d818bc-2661-43f6-adb8-13b53abf9682
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 2508dd93f7ece9274180bec8f4b6ac92a62e9bf8
ms.contentlocale: de-de
ms.lasthandoff: 01/18/2017

---

# <a name="trimming-and-removing-characters-from-strings"></a><span data-ttu-id="8448b-104">Herausnehmen und Entfernen von Zeichen aus Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="8448b-104">Trimming and removing characters from strings</span></span>

<span data-ttu-id="8448b-105">Wenn Sie einen Satz in einzelne Wörter auflösen, erhalten Sie möglicherweise Wörter mit Leerzeichen (auch als Leerräume bezeichnet) auf beiden Seiten des jeweiligen Wortes.</span><span class="sxs-lookup"><span data-stu-id="8448b-105">If you are parsing a sentence into individual words, you might end up with words that have blank spaces (also called white spaces) on either end of the word.</span></span> <span data-ttu-id="8448b-106">In diesem Fall können Sie eine der Entfernungsmethoden aus der [System.String](xref:System.String)-Klasse verwenden, um an einer bestimmten Position der Zeichenfolge eine beliebige Anzahl von Leerzeichen oder anderen Zeichen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="8448b-106">In this situation, you can use one of the trim methods in the [System.String](xref:System.String) class to remove any number of spaces or other characters from a specified position in the string.</span></span> <span data-ttu-id="8448b-107">In der folgenden Tabelle sind die verfügbaren Entfernungsmethoden aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8448b-107">The following table describes the available trim methods.</span></span>

<span data-ttu-id="8448b-108">Methodenname</span><span class="sxs-lookup"><span data-stu-id="8448b-108">Method name</span></span> | <span data-ttu-id="8448b-109">Verwendung</span><span class="sxs-lookup"><span data-stu-id="8448b-109">Use</span></span>
----------- | ---
[<span data-ttu-id="8448b-110">String.Trim</span><span class="sxs-lookup"><span data-stu-id="8448b-110">String.Trim</span></span>](xref:System.String.Trim) | <span data-ttu-id="8448b-111">Entfernt in einem Zeichenarray angegebene Leerzeichen am Anfang und Ende einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8448b-111">Removes white spaces or characters specified in an array of characters from the beginning and end of a string.</span></span>
<span data-ttu-id="8448b-112">[String.TrimEnd](xref:System.String.TrimEnd(System.Char[]))</span><span class="sxs-lookup"><span data-stu-id="8448b-112">[String.TrimEnd](xref:System.String.TrimEnd(System.Char[]))</span></span> | <span data-ttu-id="8448b-113">Entfernt in einem Zeichenarray angegebene Zeichen am Ende einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8448b-113">Removes characters specified in an array of characters from the end of a string.</span></span>
<span data-ttu-id="8448b-114">[String.TrimStart](xref:System.String.TrimStart(System.Char[]))</span><span class="sxs-lookup"><span data-stu-id="8448b-114">[String.TrimStart](xref:System.String.TrimStart(System.Char[]))</span></span> | <span data-ttu-id="8448b-115">Entfernt in einem Zeichenarray angegebene Zeichen am Anfang einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8448b-115">Removes characters specified in an array of characters from the beginning of a string.</span></span>
<span data-ttu-id="8448b-116">[String.Remove](xref:System.String.Remove(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="8448b-116">[String.Remove](xref:System.String.Remove(System.Int32))</span></span> | <span data-ttu-id="8448b-117">Entfernt eine festgelegte Anzahl von Zeichen an der angegebenen Indexposition in einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8448b-117">Removes a specified number of characters from a specified index position in a string.</span></span>


## <a name="trim"></a><span data-ttu-id="8448b-118">Trim</span><span class="sxs-lookup"><span data-stu-id="8448b-118">Trim</span></span>

<span data-ttu-id="8448b-119">Wie das folgende Beispiel zeigt, lassen sich mit der [String.Trim](xref:System.String.Trim)-Methode Leerzeichen an beiden Enden einer Zeichenfolge auf einfache Weise entfernen.</span><span class="sxs-lookup"><span data-stu-id="8448b-119">You can easily remove white spaces from both ends of a string by using the [String.Trim](xref:System.String.Trim) method, as shown in the following example.</span></span>

```csharp
string MyString = " Big   ";
Console.WriteLine("Hello{0}World!", MyString);
string TrimString = MyString.Trim();
Console.WriteLine("Hello{0}World!", TrimString);
//       The example displays the following output:
//             Hello Big   World!
//             HelloBigWorld!
```

```vb
Dim MyString As String = " Big   "
Console.WriteLine("Hello{0}World!", MyString)
Dim TrimString As String = MyString.Trim()
Console.WriteLine("Hello{0}World!", TrimString)
' The example displays the following output:
'       Hello Big   World!
'       HelloBigWorld!
```

<span data-ttu-id="8448b-120">Sie können auch Zeichen am Anfang und am Ende einer Zeichenfolge entfernen, die Sie in einem Zeichenarray angeben.</span><span class="sxs-lookup"><span data-stu-id="8448b-120">You can also remove characters that you specify in a character array from the beginning and end of a string.</span></span> <span data-ttu-id="8448b-121">Im folgenden Beispiel werden Leerzeichen, Punkte und Sternchen entfernt.</span><span class="sxs-lookup"><span data-stu-id="8448b-121">The following example removes white-space characters, periods, and asterisks.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String header = "* A Short String. *";
      Console.WriteLine(header);
      Console.WriteLine(header.Trim( new Char[] { ' ', '*', '.' } ));
   }
}
// The example displays the following output:
//       * A Short String. *
//       A Short String
```

```vb
Module Example
   Public Sub Main()
      Dim header As String = "* A Short String. *"
      Console.WriteLine(header)
      Console.WriteLine(header.Trim( { " "c, "*"c, "."c } ))
   End Sub
End Module
' The example displays the following output:
'       * A Short String. *
'       A Short String
```

## <a name="trimend"></a><span data-ttu-id="8448b-122">TrimEnd</span><span class="sxs-lookup"><span data-stu-id="8448b-122">TrimEnd</span></span>

<span data-ttu-id="8448b-123">Mit der [String.TrimEnd](xref:System.String.TrimEnd(System.Char[]))-Methode werden Zeichen am Ende einer Zeichenfolge entfernt, wodurch ein neues Zeichenfolgenobjekt entsteht.</span><span class="sxs-lookup"><span data-stu-id="8448b-123">The [String.TrimEnd](xref:System.String.TrimEnd(System.Char[])) method removes characters from the end of a string, creating a new string object.</span></span> <span data-ttu-id="8448b-124">An diese Methode wird ein Zeichenarray übergeben, das die zu entfernenden Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="8448b-124">An array of characters is passed to this method to specify the characters to be removed.</span></span> <span data-ttu-id="8448b-125">Die Reihenfolge der Elemente im Zeichenarray hat keine Auswirkungen auf den Entfernungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="8448b-125">The order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="8448b-126">Der Vorgang wird beendet, sobald ein nicht im Array angegebenes Zeichen gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="8448b-126">The trim stops when a character not specified in the array is found.</span></span>

<span data-ttu-id="8448b-127">Im folgenden Beispiel werden die letzten Buchstaben einer Zeichenfolge mit der TrimEnd-Methode entfernt.</span><span class="sxs-lookup"><span data-stu-id="8448b-127">The following example removes the last letters of a string using the TrimEnd method.</span></span> <span data-ttu-id="8448b-128">In diesem Beispiel werden die Positionen der Zeichen `'r'` und `'W'` vertauscht, um zu veranschaulichen, dass die Reihenfolge der Zeichen im Array keine Rolle spielt.</span><span class="sxs-lookup"><span data-stu-id="8448b-128">In this example, the position of the `'r'` character and the `'W'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span> <span data-ttu-id="8448b-129">Beachten Sie, dass durch diesen Code das letzte Wort von `MyString` sowie ein Teil des ersten Wortes entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="8448b-129">Notice that this code removes the last word of `MyString` plus part of the first.</span></span>

```csharp
string MyString = "Hello World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="8448b-130">Durch diesen Code wird `He` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8448b-130">This code displays `He` to the console.</span></span>

<span data-ttu-id="8448b-131">Im folgenden Beispiel wird das letzte Wort einer Zeichenfolge mit der [TrimEnd](xref:System.String.TrimEnd(System.Char[]))-Methode entfernt.</span><span class="sxs-lookup"><span data-stu-id="8448b-131">The following example removes the last word of a string using the [TrimEnd](xref:System.String.TrimEnd(System.Char[])) method.</span></span> <span data-ttu-id="8448b-132">Im Code folgt auf das Wort `Hello` ein Komma. Da das Komma im Zeichenarray nicht als zu entfernendes Zeichen angegeben ist, wird der Vorgang beim Komma beendet.</span><span class="sxs-lookup"><span data-stu-id="8448b-132">In this code, a comma follows the word `Hello` and, because the comma is not specified in the array of characters to trim, the trim ends at the comma.</span></span>

```csharp
string MyString = "Hello, World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello, World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="8448b-133">Durch diesen Code wird `Hello,` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8448b-133">This code displays `Hello,` to the console.</span></span>

## <a name="trimstart"></a><span data-ttu-id="8448b-134">TrimStart</span><span class="sxs-lookup"><span data-stu-id="8448b-134">TrimStart</span></span>

<span data-ttu-id="8448b-135">Die [String.TrimStart](xref:System.String.TrimStart(System.Char[]))-Methode ist mit der [String.TrimEnd](xref:System.String.TrimEnd(System.Char[]))-Methode vergleichbar, außer dass eine neue Zeichenfolge erstellt wird, indem Zeichen am Anfang eines bestehenden Zeichenfolgenobjekts entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="8448b-135">The [String.TrimStart](xref:System.String.TrimStart(System.Char[])) method is similar to the [String.TrimEnd](xref:System.String.TrimEnd(System.Char[])) method except that it creates a new string by removing characters from the beginning of an existing string object.</span></span> <span data-ttu-id="8448b-136">An die [TrimStart](xref:System.String.TrimStart(System.Char[]))-Methode wird ein Zeichenarray übergeben, das die zu entfernenden Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="8448b-136">An array of characters is passed to the [TrimStart](xref:System.String.TrimStart(System.Char[])) method to specify the characters to be removed.</span></span> <span data-ttu-id="8448b-137">Wie bei der [TrimEnd](xref:System.String.TrimEnd(System.Char[]))-Methode hat die Reihenfolge der Elemente im Zeichenarray keine Auswirkungen auf den Entfernungsvorgang.</span><span class="sxs-lookup"><span data-stu-id="8448b-137">As with the [TrimEnd](xref:System.String.TrimEnd(System.Char[])) method, the order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="8448b-138">Der Vorgang wird beendet, sobald ein nicht im Array angegebenes Zeichen gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="8448b-138">The trim stops when a character not specified in the array is found.</span></span>

<span data-ttu-id="8448b-139">Im folgenden Beispiel wird das erste Wort einer Zeichenfolge entfernt.</span><span class="sxs-lookup"><span data-stu-id="8448b-139">The following example removes the first word of a string.</span></span> <span data-ttu-id="8448b-140">In diesem Beispiel werden die Positionen der Zeichen `'l'` und `'H'` vertauscht, um zu veranschaulichen, dass die Reihenfolge der Zeichen im Array keine Rolle spielt.</span><span class="sxs-lookup"><span data-stu-id="8448b-140">In this example, the position of the `'l'` character and the `'H'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span>

```csharp
string MyString = "Hello World!";
char[] MyChar = {'e', 'H','l','o',' ' };
string NewString = MyString.TrimStart(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"e","H","l","o"," " }
Dim NewString As String = MyString.TrimStart(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="8448b-141">Durch diesen Code wird `World!` auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8448b-141">This code displays `World!` to the console.</span></span>

## <a name="remove"></a><span data-ttu-id="8448b-142">Remove</span><span class="sxs-lookup"><span data-stu-id="8448b-142">Remove</span></span>

<span data-ttu-id="8448b-143">Mit der [String.Remove](xref:System.String.Remove(System.Int32))-Methode wird an einer festgelegten Position innerhalb einer bestehenden Zeichenfolge eine festgelegte Anzahl von Zeichen entfernt.</span><span class="sxs-lookup"><span data-stu-id="8448b-143">The [String.Remove](xref:System.String.Remove(System.Int32)) method removes a specified number of characters that begin at a specified position in an existing string.</span></span> <span data-ttu-id="8448b-144">Diese Methode setzt einen nullbasierten Index voraus.</span><span class="sxs-lookup"><span data-stu-id="8448b-144">This method assumes a zero-based index.</span></span>

<span data-ttu-id="8448b-145">Im folgenden Beispiel werden ausgehend von der fünften Position des nullbasierten Zeichenfolgenindizes zehn Zeichen aus einer Zeichenfolge entfernt.</span><span class="sxs-lookup"><span data-stu-id="8448b-145">The following example removes ten characters from a string beginning at position five of a zero-based index of the string.</span></span>

```csharp
string MyString = "Hello Beautiful World!";
Console.WriteLine(MyString.Remove(5,10));
// The example displays the following output:
//         Hello World!  
```

```vb
Dim MyString As String = "Hello Beautiful World!"
Console.WriteLine(MyString.Remove(5,10))
' The example displays the following output:
'         Hello World!
```

<span data-ttu-id="8448b-146">Sie können auch ein bestimmtes Zeichen oder eine Teilzeichenfolge aus einer Zeichenfolge entfernen, indem Sie die [String.Replace(String, String)](xref:System.String.Replace(System.String,System.String))-Methode aufrufen und eine leere Zeichenfolge ([String.Empty](xref:System.String.Empty)) zum Ersetzen angeben.</span><span class="sxs-lookup"><span data-stu-id="8448b-146">You can also remove a specified character or substring from a string by calling the [String.Replace(String, String)](xref:System.String.Replace(System.String,System.String)) method and specifying an empty string ([String.Empty](xref:System.String.Empty)) as the replacement.</span></span> <span data-ttu-id="8448b-147">Im folgenden Beispiel werden alle Kommas in einer Zeichenfolge entfernt.</span><span class="sxs-lookup"><span data-stu-id="8448b-147">The following example removes all commas from a string.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String phrase = "a cold, dark night";
      Console.WriteLine("Before: {0}", phrase);
      phrase = phrase.Replace(",", "");
      Console.WriteLine("After: {0}", phrase);
   }
}
// The example displays the following output:
//       Before: a cold, dark night
//       After: a cold dark night
```

```vb
Module Example
   Public Sub Main()
      Dim phrase As String = "a cold, dark night"
      Console.WriteLine("Before: {0}", phrase)
      phrase = phrase.Replace(",", "")
      Console.WriteLine("After: {0}", phrase)
   End Sub
End Module
' The example displays the following output:
'       Before: a cold, dark night
'       After: a cold dark night
```

## <a name="see-also"></a><span data-ttu-id="8448b-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8448b-148">See Also</span></span>

[<span data-ttu-id="8448b-149">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="8448b-149">Basic string operations</span></span>](basic-string-operations.md)


