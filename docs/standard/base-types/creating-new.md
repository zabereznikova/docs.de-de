---
title: Erstellen neuer Zeichenfolgen
description: Erstellen neuer Zeichenfolgen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 639397c7-e694-43e0-845b-1681c62bd9fd
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 793b5bc4b26967104459fa2559c6127bb82f3a9d
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="creating-new-strings"></a><span data-ttu-id="1d28d-104">Erstellen neuer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="1d28d-104">Creating new strings</span></span>

<span data-ttu-id="1d28d-105">.NET ermöglicht das Erstellen von Zeichenfolgen mithilfe einer einfachen Zuweisung und überlädt auch einen Klassenkonstruktor, um die Zeichenfolgenerstellung mithilfe einer Reihe verschiedener Parameter zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-105">.NET  allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="1d28d-106">.NET stellt auch verschiedene Methoden in der [System.String](xref:System.String)-Klasse bereit, die durch Kombinieren verschiedener Zeichenfolgen, Zeichenfolgenarrays oder Objekte neue Zeichenfolgenobjekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-106">.NET also provides several methods in the [System.String](xref:System.String) class that create new string objects by combining several strings, arrays of strings, or objects.</span></span> 

## <a name="creating-strings-using-assignment"></a><span data-ttu-id="1d28d-107">Erstellen von Zeichenfolgen mithilfe von Zuweisung</span><span class="sxs-lookup"><span data-stu-id="1d28d-107">Creating Strings Using Assignment</span></span>

<span data-ttu-id="1d28d-108">Die einfachste Möglichkeit, ein neues [String](xref:System.String)-Objekt zu erstellen, ist die Zuweisung eines Zeichenfolgenliterals zu einem [String](xref:System.String)-Objekt.</span><span class="sxs-lookup"><span data-stu-id="1d28d-108">The easiest way to create a new [String](xref:System.String) object is simply to assign a string literal to a [String](xref:System.String) object.</span></span> 

## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="1d28d-109">Erstellen von Zeichenfolgen mithilfe eines Klassenkonstruktors</span><span class="sxs-lookup"><span data-stu-id="1d28d-109">Creating Strings Using a Class Constructor</span></span>

<span data-ttu-id="1d28d-110">Sie können Überladungen des [String](xref:System.String)-Klassenkonstruktors verwenden, um Zeichenfolgen aus Zeichenarrays zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-110">You can use overloads of the [String](xref:System.String) class constructor to create strings from character arrays.</span></span> <span data-ttu-id="1d28d-111">Sie können auch eine neue Zeichenfolge erstellen, indem Sie ein bestimmtes Zeichen eine angegebene Anzahl von Malen duplizieren.</span><span class="sxs-lookup"><span data-stu-id="1d28d-111">You can also create a new string by duplicating a particular character a specified number of times.</span></span> 

## <a name="methods-that-return-strings"></a><span data-ttu-id="1d28d-112">Methoden, die Zeichenfolgen zurückgeben</span><span class="sxs-lookup"><span data-stu-id="1d28d-112">Methods that Return Strings</span></span>

<span data-ttu-id="1d28d-113">Die folgende Tabelle führt verschiedene nützliche Methoden auf, die neue Zeichenfolgenobjekte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1d28d-113">The following table lists several useful methods that return new string objects.</span></span>

<span data-ttu-id="1d28d-114">Methodenname</span><span class="sxs-lookup"><span data-stu-id="1d28d-114">Method name</span></span> | <span data-ttu-id="1d28d-115">Verwendung</span><span class="sxs-lookup"><span data-stu-id="1d28d-115">Use</span></span>
----------- | ---
<span data-ttu-id="1d28d-116">[String.Format](xref:System.String.Format(System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="1d28d-116">[String.Format](xref:System.String.Format(System.String,System.Object))</span></span> | <span data-ttu-id="1d28d-117">Erstellt eine formatierte Zeichenfolge aus einem Satz von Eingabeobjekten.</span><span class="sxs-lookup"><span data-stu-id="1d28d-117">Builds a formatted string from a set of input objects.</span></span>
<span data-ttu-id="1d28d-118">[String.Concat](xref:System.String.Concat(System.String,System.String))</span><span class="sxs-lookup"><span data-stu-id="1d28d-118">[String.Concat](xref:System.String.Concat(System.String,System.String))</span></span> | <span data-ttu-id="1d28d-119">Erstellt Zeichenfolgen aus mindestens zwei Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-119">Builds strings from two or more strings.</span></span>
<span data-ttu-id="1d28d-120">[String.Join](xref:System.String.Join(System.String,System.String[]))</span><span class="sxs-lookup"><span data-stu-id="1d28d-120">[String.Join](xref:System.String.Join(System.String,System.String[]))</span></span> |<span data-ttu-id="1d28d-121">Erstellt eine neue Zeichenfolge durch Kombinieren eines Arrays aus Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-121">Builds a new string by combining an array of strings.</span></span>
<span data-ttu-id="1d28d-122">[String.Insert](xref:System.String.Insert(System.Int32,System.String))</span><span class="sxs-lookup"><span data-stu-id="1d28d-122">[String.Insert](xref:System.String.Insert(System.Int32,System.String))</span></span> | <span data-ttu-id="1d28d-123">Erstellt eine neue Zeichenfolge durch Einfügen einer Zeichenfolge in den angegebenen Index einer vorhandenen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1d28d-123">Builds a new string by inserting a string into the specified index of an existing string.</span></span>
<span data-ttu-id="1d28d-124">[String.CopyTo](xref:System.String.CopyTo(System.Int32,System.Char[],System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="1d28d-124">[String.CopyTo](xref:System.String.CopyTo(System.Int32,System.Char[],System.Int32,System.Int32))</span></span> | <span data-ttu-id="1d28d-125">Kopiert angegebene Zeichen in einer Zeichenfolge in eine bestimmte Position in einem Array aus Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-125">Copies specified characters in a string into a specified position in an array of characters.</span></span>

### <a name="format"></a><span data-ttu-id="1d28d-126">Format</span><span class="sxs-lookup"><span data-stu-id="1d28d-126">Format</span></span>

<span data-ttu-id="1d28d-127">Sie können die `String.Format`-Methode verwenden, um formatierte Zeichenfolgen zu erstellen und Zeichenfolgen zu verketten, die mehrere Objekte darstellen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-127">You can use the `String.Format` method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="1d28d-128">Diese Methode konvertiert automatisch alle übergebenen Objekte in eine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1d28d-128">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="1d28d-129">Wenn Ihre Anwendung z.B. dem Benutzer einen [Int32](xref:System.Int32)-Wert und einen [DateTime](xref:System.DateTime)-Wert anzeigen soll, können Sie ganz einfach mithilfe der `Format`-Methode eine Zeichenfolge erstellen, um diese Werte darzustellen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-129">For example, if your application must display an [Int32](xref:System.Int32) value and a [DateTime](xref:System.DateTime) value to the user, you can easily construct a string to represent these values using the `Format` method.</span></span> <span data-ttu-id="1d28d-130">Informationen zu den mit dieser Methode verwendeten Formatierungskonventionen finden Sie im Abschnitt [Zusammengesetzte Formatierung](composite-format.md).</span><span class="sxs-lookup"><span data-stu-id="1d28d-130">For information about formatting conventions used with this method, see the section on [composite formatting](composite-format.md).</span></span>

<span data-ttu-id="1d28d-131">Das folgende Beispiel verwendet die `Format`-Methode, um eine Zeichenfolge zu erstellen, die eine ganzzahlige Variable verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d28d-131">The following example uses the `Format` method to create a string that uses an integer variable.</span></span>

```csharp
int numberOfFleas = 12;
string miscInfo = String.Format("Your dog has {0} fleas. " +
                                "It is time to get a flea collar. " + 
                                "The current universal date is: {1:u}.", 
                                numberOfFleas, DateTime.Now);
Console.WriteLine(miscInfo);
// The example displays the following output:
//       Your dog has 12 fleas. It is time to get a flea collar. 
//       The current universal date is: 2008-03-28 13:31:40Z.
```

```vb
Dim numberOfFleas As Integer = 12
Dim miscInfo As String = String.Format("Your dog has {0} fleas. " & _
                                       "It is time to get a flea collar. " & _ 
                                       "The current universal date is: {1:u}.", _ 
                                       numberOfFleas, Date.Now)
Console.WriteLine(miscInfo)
' The example displays the following output:
'       Your dog has 12 fleas. It is time to get a flea collar. 
'       The current universal date is: 2008-03-28 13:31:40Z.
```

<span data-ttu-id="1d28d-132">In diesem Beispiel zeigt [DateTime.Now](xref:System.DateTime.Now) das aktuelle Datum und die aktuelle Uhrzeit so an, wie es von der mit dem aktuellen Thread verknüpften Kultur angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="1d28d-132">In this example, [DateTime.Now](xref:System.DateTime.Now) displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>

### <a name="concat"></a><span data-ttu-id="1d28d-133">Concat</span><span class="sxs-lookup"><span data-stu-id="1d28d-133">Concat</span></span>

<span data-ttu-id="1d28d-134">Die `String.Concat`-Methode kann verwendet werden, um ganz einfach aus mindestens zwei vorhandenen Objekten ein neues Zeichenfolgenobjekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-134">The `String.Concat` method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="1d28d-135">Die Methode bietet eine sprachunabhängige Möglichkeit zum Verketten von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-135">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="1d28d-136">Diese Methode akzeptiert alle von `System.Object` abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-136">This method accepts any class that derives from `System.Object`.</span></span> <span data-ttu-id="1d28d-137">Das folgende Beispiel erstellt eine Zeichenfolge aus zwei vorhandenen Zeichenfolgenobjekten und einem Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-137">The following example creates a string from two existing string objects and a separating character.</span></span>

```csharp
string helloString1 = "Hello";
string helloString2 = "World!";
Console.WriteLine(String.Concat(helloString1, ' ', helloString2));
// The example displays the following output:
//      Hello World!
```

```vb
Dim helloString1 As String = "Hello"
Dim helloString2 As String = "World!"
Console.WriteLine(String.Concat(helloString1, " "c, helloString2))
' The example displays the following output:
'      Hello World!
```

### <a name="join"></a><span data-ttu-id="1d28d-138">Join</span><span class="sxs-lookup"><span data-stu-id="1d28d-138">Join</span></span>

<span data-ttu-id="1d28d-139">Die `String.Join`-Methode erstellt eine neue Zeichenfolge aus einem Array aus Zeichenfolgen und einem Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-139">The `String.Join` method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="1d28d-140">Diese Methode ist nützlich, wenn Sie mehrere Zeichenfolgen miteinander verketten möchten. Sie erstellt eine Liste, die z.B. durch ein Komma getrennt sein kann.</span><span class="sxs-lookup"><span data-stu-id="1d28d-140">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>

<span data-ttu-id="1d28d-141">Das folgende Beispiel verwendet ein Leerzeichen, um ein Zeichenfolgenarray zu binden.</span><span class="sxs-lookup"><span data-stu-id="1d28d-141">The following example uses a space to bind a string array.</span></span>

```csharp
string[] words = {"Hello", "and", "welcome", "to", "my" , "world!"};
Console.WriteLine(String.Join(" ", words));
// The example displays the following output:
//      Hello and welcome to my world!
```

```vb
Dim words() As String = {"Hello", "and", "welcome", "to", "my" , "world!"}
Console.WriteLine(String.Join(" ", words))
' The example displays the following output:
'      Hello and welcome to my world!
```

### <a name="insert"></a><span data-ttu-id="1d28d-142">Insert</span><span class="sxs-lookup"><span data-stu-id="1d28d-142">Insert</span></span>

<span data-ttu-id="1d28d-143">Die `String.Insert`-Methode erstellt eine neue Zeichenfolge, indem sie eine Zeichenfolge an einer angegebenen Position in einer anderen Zeichenfolge einfügt.</span><span class="sxs-lookup"><span data-stu-id="1d28d-143">The `String.Insert` method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="1d28d-144">Diese Methode verwendet einen nullbasierten Index.</span><span class="sxs-lookup"><span data-stu-id="1d28d-144">This method uses a zero-based index.</span></span> <span data-ttu-id="1d28d-145">Das folgende Beispiel fügt eine Zeichenfolge an der fünften Indexposition von `MyString` ein und erstellt mit diesem Wert eine neue Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1d28d-145">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>

```csharp
string sentence = "Once a time.";   
 Console.WriteLine(sentence.Insert(4, " upon"));
 // The example displays the following output:
 //      Once upon a time.
```

```vb
Dim sentence As String = "Once a time."   
 Console.WriteLine(sentence.Insert(4, " upon"))
 ' The example displays the 
```

### <a name="copyto"></a><span data-ttu-id="1d28d-146">CopyTo</span><span class="sxs-lookup"><span data-stu-id="1d28d-146">CopyTo</span></span>

<span data-ttu-id="1d28d-147">Die `String.CopyTo`-Methode kopiert Teile einer Zeichenfolge in ein Zeichenarray.</span><span class="sxs-lookup"><span data-stu-id="1d28d-147">The `String.CopyTo` method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="1d28d-148">Sie können sowohl den Startindex der Zeichenfolge als auch die Anzahl der zu kopierenden Zeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="1d28d-148">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="1d28d-149">Diese Methode akzeptiert den Quellindex, ein Array aus Zeichen, den Zielindex und die Anzahl der zu kopierenden Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1d28d-149">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="1d28d-150">Alle Indizes sind nullbasiert.</span><span class="sxs-lookup"><span data-stu-id="1d28d-150">All indexes are zero-based.</span></span>

<span data-ttu-id="1d28d-151">Das folgende Beispiel verwendet die `CopyTo`-Methode, um die Zeichen des Worts „Hello“ aus einem Zeichenfolgenobjekt in die erste Indexposition eines Zeichenarrays zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="1d28d-151">The following example uses the `CopyTo` method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>

```csharp
string greeting = "Hello World!";
char[] charArray = {'W','h','e','r','e'};
Console.WriteLine("The original character array: {0}", new string(charArray));
greeting.CopyTo(0, charArray,0 ,5);
Console.WriteLine("The new character array: {0}", new string(charArray));
// The example displays the following output:
//       The original character array: Where
//       The new character array: Hello
```

```vb
Dim greeting As String = "Hello World!"
Dim charArray() As Char = {"W"c, "h"c, "e"c, "r"c, "e"c}
Console.WriteLine("The original character array: {0}", New String(charArray))
greeting.CopyTo(0, charArray,0 ,5)
Console.WriteLine("The new character array: {0}", New String(charArray))
' The example displays the following output:
'       The original character array: Where
'       The new character array: Hello
```

## <a name="see-also"></a><span data-ttu-id="1d28d-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d28d-152">See Also</span></span>

[<span data-ttu-id="1d28d-153">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="1d28d-153">Basic string operations</span></span>](basic-string-operations.md)

[<span data-ttu-id="1d28d-154">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="1d28d-154">Composite formatting</span></span>](composite-format.md)


