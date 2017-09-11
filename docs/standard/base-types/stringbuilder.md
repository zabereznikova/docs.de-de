---
title: Verwenden der StringBuilder-Klasse
description: Verwenden der StringBuilder-Klasse
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: f4f5d1c7-d84d-4867-810f-2708cd6de0da
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 076e10e095b50cc96187f2ec13ade2365d83dad3
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="using-the-stringbuilder-class"></a><span data-ttu-id="47a7a-104">Verwenden der StringBuilder-Klasse</span><span class="sxs-lookup"><span data-stu-id="47a7a-104">Using the StringBuilder class</span></span>

<span data-ttu-id="47a7a-105">Das [String](xref:System.String)-Objekt ist nicht änderbar.</span><span class="sxs-lookup"><span data-stu-id="47a7a-105">The [String](xref:System.String) object is immutable.</span></span> <span data-ttu-id="47a7a-106">Jedes Mal, wenn Sie eine der Methoden in der [System.String](xref:System.String)-Klasse verwenden, erstellen Sie ein neues Zeichenfolgenobjekt im Arbeitsspeicher, das eine neue Zuordnung von Speicherplatz für dieses neue Objekt erfordert.</span><span class="sxs-lookup"><span data-stu-id="47a7a-106">Every time you use one of the methods in the [System.String](xref:System.String) class, you create a new string object in memory, which requires a new allocation of space for that new object.</span></span> <span data-ttu-id="47a7a-107">In Fällen, in denen Sie wiederholte Änderungen an einer Zeichenfolge vornehmen müssen, kann der Aufwand, der mit dem Erstellen eines neuen [String](xref:System.String)-Objekts verbunden ist, erheblich sein.</span><span class="sxs-lookup"><span data-stu-id="47a7a-107">In situations where you need to perform repeated modifications to a string, the overhead associated with creating a new [String](xref:System.String) object can be costly.</span></span> <span data-ttu-id="47a7a-108">Die [System.Text.StringBuilder](xref:System.Text.StringBuilder)-Klasse kann verwendet werden, wenn Sie eine Zeichenfolge ändern möchten, ohne ein neues Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="47a7a-108">The [System.Text.StringBuilder](xref:System.Text.StringBuilder) class can be used when you want to modify a string without creating a new object.</span></span> <span data-ttu-id="47a7a-109">Beispielsweise lässt sich durch Verwenden der [StringBuilder](xref:System.Text.StringBuilder)-Klasse die Leistung steigern, wenn zahlreiche Zeichenfolgen in einer Schleife verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="47a7a-109">For example, using the [StringBuilder](xref:System.Text.StringBuilder) class can boost performance when concatenating many strings together in a loop.</span></span>

## <a name="importing-the-systemtext-namespace"></a><span data-ttu-id="47a7a-110">Importieren des System.Text-Namespace</span><span class="sxs-lookup"><span data-stu-id="47a7a-110">Importing the System.Text Namespace</span></span>

<span data-ttu-id="47a7a-111">Die [StringBuilder](xref:System.Text.StringBuilder)-Klasse befindet sich im [System.Text](xref:System.Text)-Namespace.</span><span class="sxs-lookup"><span data-stu-id="47a7a-111">The [StringBuilder](xref:System.Text.StringBuilder) class is found in the [System.Text](xref:System.Text) namespace.</span></span> <span data-ttu-id="47a7a-112">Wenn Sie in Ihrem Code nicht den vollqualifizierten Typnamen bereitstellen möchten, können Sie den [System.Text](xref:System.Text)-Namespace importieren:</span><span class="sxs-lookup"><span data-stu-id="47a7a-112">To avoid having to provide a fully qualified type name in your code, you can import the [System.Text](xref:System.Text) namespace:</span></span> 

```csharp
using System;
using System.Text;
```

```vb
Imports System.Text
```

## <a name="instantiating-a-stringbuilder-object"></a><span data-ttu-id="47a7a-113">Instanziieren eines StringBuilder-Objekts</span><span class="sxs-lookup"><span data-stu-id="47a7a-113">Instantiating a StringBuilder Object</span></span>

<span data-ttu-id="47a7a-114">Sie können eine neue Instanz der [StringBuilder](xref:System.Text.StringBuilder)-Klasse erstellen, indem Sie Ihre Variable mit einer der Methoden für überladene Konstruktoren initialisieren, wie im folgenden Beispiel verdeutlicht.</span><span class="sxs-lookup"><span data-stu-id="47a7a-114">You can create a new instance of the [StringBuilder](xref:System.Text.StringBuilder) class by initializing your variable with one of the overloaded constructor methods, as illustrated in the following example.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
```

## <a name="setting-the-capacity-and-length"></a><span data-ttu-id="47a7a-115">Festlegen von Kapazität und Länge</span><span class="sxs-lookup"><span data-stu-id="47a7a-115">Setting the Capacity and Length</span></span>

<span data-ttu-id="47a7a-116">Obwohl ein [StringBuilder](xref:System.Text.StringBuilder)-Objekt ein dynamisches Objekt ist, das es Ihnen ermöglicht, die Anzahl der Zeichen in der darin gekapselten Zeichenfolge zu erweitern, können Sie einen Wert für die maximale Anzahl von Zeichen festlegen, die das Objekt enthalten darf.</span><span class="sxs-lookup"><span data-stu-id="47a7a-116">Although the [StringBuilder](xref:System.Text.StringBuilder) is a dynamic object that allows you to expand the number of characters in the string that it encapsulates, you can specify a value for the maximum number of characters that it can hold.</span></span> <span data-ttu-id="47a7a-117">Dieser Wert wird als die Kapazität des Objekts bezeichnet und darf nicht mit der Länge der Zeichenfolge verwechselt werden, die im aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="47a7a-117">This value is called the capacity of the object and should not be confused with the length of the string that the current [StringBuilder](xref:System.Text.StringBuilder) holds.</span></span> <span data-ttu-id="47a7a-118">Sie könnten z.B. eine neue Instanz der [StringBuilder](xref:System.Text.StringBuilder)-Klasse mit der Zeichenfolge „Hello“ erstellen, die eine Länge von 5 Zeichen hat, und Sie könnten angeben, dass das Objekt eine maximale Kapazität von 25 Zeichen hat.</span><span class="sxs-lookup"><span data-stu-id="47a7a-118">For example, you might create a new instance of the [StringBuilder](xref:System.Text.StringBuilder) class with the string "Hello", which has a length of 5, and you might specify that the object has a maximum capacity of 25.</span></span> <span data-ttu-id="47a7a-119">Wenn das [StringBuilder](xref:System.Text.StringBuilder)-Objekt geändert wird, ordnet es für sich selbst keine neue Größe zu, bis die Kapazität erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="47a7a-119">When you modify the [StringBuilder](xref:System.Text.StringBuilder), it does not reallocate size for itself until the capacity is reached.</span></span> <span data-ttu-id="47a7a-120">Tritt dieser Fall ein, wird der neue Speicherplatz automatisch zugeordnet, und die Kapazität wird verdoppelt.</span><span class="sxs-lookup"><span data-stu-id="47a7a-120">When this occurs, the new space is allocated automatically and the capacity is doubled.</span></span> <span data-ttu-id="47a7a-121">Sie können die Kapazität der [StringBuilder](xref:System.Text.StringBuilder)-Klasse angeben, indem Sie einen der überladenen Konstruktoren verwenden.</span><span class="sxs-lookup"><span data-stu-id="47a7a-121">You can specify the capacity of the [StringBuilder](xref:System.Text.StringBuilder) class using one of the overloaded constructors.</span></span> <span data-ttu-id="47a7a-122">Im folgenden Beispiel wird festgelegt, dass das `MyStringBuilder`-Objekt auf maximal 25 Zeichen erweitert werden kann.</span><span class="sxs-lookup"><span data-stu-id="47a7a-122">The following example specifies that the `MyStringBuilder` object can be expanded to a maximum of 25 spaces.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!", 25);
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!", 25) 
```

<span data-ttu-id="47a7a-123">Darüber hinaus können Sie die [Capacity](xref:System.Text.StringBuilder.Capacity)-Eigenschaft mit Lese-/Schreibzugriff verwenden, um die maximale Länge Ihres Objekts festzulegen.</span><span class="sxs-lookup"><span data-stu-id="47a7a-123">Additionally, you can use the read/write [Capacity](xref:System.Text.StringBuilder.Capacity) property to set the maximum length of your object.</span></span> <span data-ttu-id="47a7a-124">Im folgenden Beispiel wird die [Capacity](xref:System.Text.StringBuilder.Capacity)-Eigenschaft verwendet, um die maximale Objektlänge zu definieren.</span><span class="sxs-lookup"><span data-stu-id="47a7a-124">The following example uses the [Capacity](xref:System.Text.StringBuilder.Capacity) property to define the maximum object length.</span></span>

```csharp
MyStringBuilder.Capacity = 25;
```

```vb
MyStringBuilder.Capacity = 25
```

<span data-ttu-id="47a7a-125">Mithilfe der [EnsureCapacity](xref:System.Text.StringBuilder.EnsureCapacity(System.Int32))-Methode kann die Kapazität des aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekts überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="47a7a-125">The [EnsureCapacity](xref:System.Text.StringBuilder.EnsureCapacity(System.Int32)) method can be used to check the capacity of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="47a7a-126">Ist die Kapazität größer als der übergebene Wert, wird keine Änderung vorgenommen. Ist die Kapazität dagegen kleiner als der übergebene Wert, wird die aktuelle Kapazität entsprechend dem übergebenen Wert geändert.</span><span class="sxs-lookup"><span data-stu-id="47a7a-126">If the capacity is greater than the passed value, no change is made; however, if the capacity is smaller than the passed value, the current capacity is changed to match the passed value.</span></span>

<span data-ttu-id="47a7a-127">Die [Length](xref:System.Text.StringBuilder.Length)-Eigenschaft kann auch angezeigt oder festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="47a7a-127">The [Length](xref:System.Text.StringBuilder.Length) property can also be viewed or set.</span></span> <span data-ttu-id="47a7a-128">Wenn Sie für die [Length](xref:System.Text.StringBuilder.Length)-Eigenschaft einen Wert festlegen, der größer ist als der Wert der [Capacity](xref:System.Text.StringBuilder.Capacity)-Eigenschaft, wird die [Capacity](xref:System.Text.StringBuilder.Capacity)-Eigenschaft automatisch auf den Wert der [Length](xref:System.Text.StringBuilder.Length)-Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="47a7a-128">If you set the [Length](xref:System.Text.StringBuilder.Length) property to a value that is greater than the [Capacity](xref:System.Text.StringBuilder.Capacity) property, the [Capacity](xref:System.Text.StringBuilder.Capacity) property is automatically changed to the same value as the [Length](xref:System.Text.StringBuilder.Length) property.</span></span> <span data-ttu-id="47a7a-129">Ist die [Length](xref:System.Text.StringBuilder.Length)-Eigenschaft auf einen Wert festgelegt, der kleiner als die Länge der Zeichenfolge im aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekt ist, wird die Zeichenfolge gekürzt.</span><span class="sxs-lookup"><span data-stu-id="47a7a-129">Setting the [Length](xref:System.Text.StringBuilder.Length) property to a value that is less than the length of the string within the current [StringBuilder](xref:System.Text.StringBuilder) shortens the string.</span></span>

## <a name="modifying-the-stringbuilder-string"></a><span data-ttu-id="47a7a-130">Ändern der StringBuilder-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="47a7a-130">Modifying the StringBuilder String</span></span>

<span data-ttu-id="47a7a-131">In der folgenden Tabelle sind die Methoden aufgeführt, mit denen Sie den Inhalt eines [StringBuilder](xref:System.Text.StringBuilder)-Objekts ändern können.</span><span class="sxs-lookup"><span data-stu-id="47a7a-131">The following table lists the methods you can use to modify the contents of a [StringBuilder](xref:System.Text.StringBuilder).</span></span>

<span data-ttu-id="47a7a-132">Methodenname</span><span class="sxs-lookup"><span data-stu-id="47a7a-132">Method name</span></span> | <span data-ttu-id="47a7a-133">Verwendung</span><span class="sxs-lookup"><span data-stu-id="47a7a-133">Use</span></span>
----------- | ---
<span data-ttu-id="47a7a-134">[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char))</span><span class="sxs-lookup"><span data-stu-id="47a7a-134">[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char))</span></span> | <span data-ttu-id="47a7a-135">Fügt Informationen an das Ende des aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekts an.</span><span class="sxs-lookup"><span data-stu-id="47a7a-135">Appends information to the end of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="47a7a-136">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="47a7a-136">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span></span> | <span data-ttu-id="47a7a-137">Ersetzt einen in einer Zeichenfolge übergebenen Formatbezeichner durch formatierten Text.</span><span class="sxs-lookup"><span data-stu-id="47a7a-137">Replaces a format specifier passed in a string with formatted text.</span></span>
<span data-ttu-id="47a7a-138">[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char))</span><span class="sxs-lookup"><span data-stu-id="47a7a-138">[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char))</span></span> | <span data-ttu-id="47a7a-139">Fügt eine Zeichenfolge oder ein Objekt in den angegebenen Index des aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekts ein.</span><span class="sxs-lookup"><span data-stu-id="47a7a-139">Inserts a string or object into the specified index of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="47a7a-140">[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="47a7a-140">[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))</span></span> | <span data-ttu-id="47a7a-141">Entfernt eine angegebene Anzahl von Zeichen aus dem aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekt.</span><span class="sxs-lookup"><span data-stu-id="47a7a-141">Removes a specified number of characters from the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="47a7a-142">[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char))</span><span class="sxs-lookup"><span data-stu-id="47a7a-142">[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char))</span></span> | <span data-ttu-id="47a7a-143">Ersetzt ein angegebenes Zeichen an einem angegebenen Index.</span><span class="sxs-lookup"><span data-stu-id="47a7a-143">Replaces a specified character at a specified index.</span></span>

### <a name="append"></a><span data-ttu-id="47a7a-144">Anfügen</span><span class="sxs-lookup"><span data-stu-id="47a7a-144">Append</span></span>

<span data-ttu-id="47a7a-145">Mithilfe der [StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char))-Methode kann Text oder eine Zeichenfolgendarstellung eines Objekts am Ende einer Zeichenfolge hinzugefügt werden, die durch das aktuelle [StringBuilder](xref:System.Text.StringBuilder)-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="47a7a-145">The [StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) method can be used to add text or a string representation of an object to the end of a string represented by the current [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="47a7a-146">Im folgenden Beispiel wird ein [StringBuilder](xref:System.Text.StringBuilder)-Objekt auf „Hello World“ initialisiert und anschließend Text am Ende des Objekts angefügt.</span><span class="sxs-lookup"><span data-stu-id="47a7a-146">The following example initializes a [StringBuilder](xref:System.Text.StringBuilder) to "Hello World" and then appends some text to the end of the object.</span></span> <span data-ttu-id="47a7a-147">Speicherplatz wird automatisch nach Bedarf zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="47a7a-147">Space is allocated automatically as needed.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Append(" What a beautiful day.");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World! What a beautiful day.
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Append(" What a beautiful day.")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World! What a beautiful day.
```

### <a name="appendformat"></a><span data-ttu-id="47a7a-148">AppendFormat</span><span class="sxs-lookup"><span data-stu-id="47a7a-148">AppendFormat</span></span>

<span data-ttu-id="47a7a-149">Die [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))-Methode fügt Text am Ende des [StringBuilder](xref:System.Text.StringBuilder)-Objekts hinzu.</span><span class="sxs-lookup"><span data-stu-id="47a7a-149">The [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) method adds text to the end of the [StringBuilder](xref:System.Text.StringBuilder) object.</span></span> <span data-ttu-id="47a7a-150">Die Methode unterstützt die Funktion für die zusammengesetzte Formatierung (weitere Informationen finden Sie unter [Zusammengesetzte Formatierung](composite-format.md)) durch Aufrufen der [IFormattable](xref:System.IFormattable)-Implementierung der Objekte, die formatiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="47a7a-150">It supports the composite formatting feature (for more information, see [Composite Formatting](composite-format.md)) by calling the [IFormattable](xref:System.IFormattable) implementation of the object or objects to be formatted.</span></span> <span data-ttu-id="47a7a-151">Daher akzeptiert sie die Standardformatzeichenfolgen für numerische Werte, Datums- und Uhrzeitwerte sowie Enumerationswerte, die benutzerdefinierten Formatzeichenfolgen für numerische Werte sowie Datums- und Uhrzeitwerte und die Formatzeichenfolgen, die für benutzerdefinierte Typen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="47a7a-151">Therefore, it accepts the standard format strings for numeric, date and time, and enumeration values, the custom format strings for numeric and date and time values, and the format strings defined for custom types.</span></span> <span data-ttu-id="47a7a-152">(Weitere Informationen zur Formatierung finden Sie unter [Formatieren von Typen](formatting-types.md).) Sie können diese Methode verwenden, um das Format von Variablen anzupassen und diese Werte an ein [StringBuilder](xref:System.Text.StringBuilder)-Objekt anzufügen.</span><span class="sxs-lookup"><span data-stu-id="47a7a-152">(For information about formatting, see [Formatting Types](formatting-types.md).) You can use this method to customize the format of variables and append those values to a [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="47a7a-153">Im folgenden Beispiel wird die AppendFormat-Methode verwendet, um einen als Währungsbetrag formatierten ganzzahligen Wert am Ende eines [StringBuilder](xref:System.Text.StringBuilder)-Objekts einzufügen.</span><span class="sxs-lookup"><span data-stu-id="47a7a-153">The following example uses the AppendFormat method to place an integer value formatted as a currency value at the end of a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
int MyInt = 25; 
StringBuilder MyStringBuilder = new StringBuilder("Your total is ");
MyStringBuilder.AppendFormat("{0:C} ", MyInt);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Your total is $25.00
```

```vb
Dim MyInt As Integer = 25
Dim MyStringBuilder As New StringBuilder("Your total is ")
MyStringBuilder.AppendFormat("{0:C} ", MyInt)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'     Your total is $25.00 
```

### <a name="insert"></a><span data-ttu-id="47a7a-154">Insert</span><span class="sxs-lookup"><span data-stu-id="47a7a-154">Insert</span></span>

<span data-ttu-id="47a7a-155">Mit der [StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char))-Methode wird an einer angegebenen Position im aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekt eine Zeichenfolge oder ein Objekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="47a7a-155">The [StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) method adds a string or object to a specified position in the current [StringBuilder](xref:System.Text.StringBuilder) object.</span></span> <span data-ttu-id="47a7a-156">Im folgenden Beispiel wird mit dieser Methode ein Wort an der sechsten Position eines [StringBuilder](xref:System.Text.StringBuilder)-Objekts eingefügt.</span><span class="sxs-lookup"><span data-stu-id="47a7a-156">The following example uses this method to insert a word into the sixth position of a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Insert(6,"Beautiful ");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello Beautiful World!
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Insert(6, "Beautiful ")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'      Hello Beautiful World!
```

### <a name="remove"></a><span data-ttu-id="47a7a-157">Remove</span><span class="sxs-lookup"><span data-stu-id="47a7a-157">Remove</span></span>

<span data-ttu-id="47a7a-158">Über die [StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))-Methode können Sie, beginnend bei einem angegebenen nullbasierten Index, eine bestimmte Anzahl von Zeichen aus dem aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekt entfernen.</span><span class="sxs-lookup"><span data-stu-id="47a7a-158">You can use the [StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) method to remove a specified number of characters from the current [StringBuilder](xref:System.Text.StringBuilder) object, beginning at a specified zero-based index.</span></span> <span data-ttu-id="47a7a-159">Im folgenden Beispiel wird die [Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))-Methode verwendet, um ein [StringBuilder](xref:System.Text.StringBuilder)-Objekt zu kürzen.</span><span class="sxs-lookup"><span data-stu-id="47a7a-159">The following example uses the [Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) method to shorten a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Remove(5,7);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Remove(5, 7)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello
```

### <a name="replace"></a><span data-ttu-id="47a7a-160">Ersetzen</span><span class="sxs-lookup"><span data-stu-id="47a7a-160">Replace</span></span>

<span data-ttu-id="47a7a-161">Die [StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Ersetzt ein angegebenes Zeichen an einem angegebenen Index.</span><span class="sxs-lookup"><span data-stu-id="47a7a-161">The [StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Replaces a specified character at a specified index.</span></span>
<span data-ttu-id="47a7a-162">-Methode kann verwendet werden, um Zeichen im [StringBuilder](xref:System.Text.StringBuilder)-Objekt durch ein anderes angegebenes Zeichen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="47a7a-162">method can be used to replace characters within the [StringBuilder](xref:System.Text.StringBuilder) object with another specified character.</span></span> <span data-ttu-id="47a7a-163">Im folgenden Beispiel wird die [Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Ersetzt ein angegebenes Zeichen an einem angegebenen Index.</span><span class="sxs-lookup"><span data-stu-id="47a7a-163">The following example uses the [Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Replaces a specified character at a specified index.</span></span>
<span data-ttu-id="47a7a-164">-Methode verwendet, um in einem [StringBuilder](xref:System.Text.StringBuilder)-Objekt nach allen Vorkommen des Ausrufezeichens (!) zu suchen und diese durch das Fragezeichen (?) zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="47a7a-164">method to search a [StringBuilder](xref:System.Text.StringBuilder) object for all instances of the exclamation point character (!) and replace them with the question mark character (?).</span></span>
 
 ```csharp
 StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Replace('!', '?');
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World?
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Replace("!"c, "?"c)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World?
```

## <a name="converting-a-stringbuilder-object-to-a-string"></a><span data-ttu-id="47a7a-165">Konvertieren eines StringBuilder-Objekts in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="47a7a-165">Converting a StringBuilder Object to a String</span></span>

<span data-ttu-id="47a7a-166">Sie müssen das [StringBuilder](xref:System.Text.StringBuilder)-Objekt in ein [String](xref:System.String)-Objekt konvertieren, bevor Sie die vom [StringBuilder](xref:System.Text.StringBuilder)-Objekt dargestellte Zeichenfolge an eine Methode übergeben können, die einen [String](xref:System.String)-Parameter hat, oder bevor Sie sie in der Benutzeroberfläche anzeigen.</span><span class="sxs-lookup"><span data-stu-id="47a7a-166">You must convert the [StringBuilder](xref:System.Text.StringBuilder) object to a [String](xref:System.String) object before you can pass the string represented by the [StringBuilder](xref:System.Text.StringBuilder) object to a method that has a [String](xref:System.String) parameter or display it in the user interface.</span></span> <span data-ttu-id="47a7a-167">Diese Konvertierung führen Sie aus, indem Sie die [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString)-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="47a7a-167">You do this conversion by calling the [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) method.</span></span> <span data-ttu-id="47a7a-168">Im folgenden Beispiel werden einige [StringBuilder](xref:System.Text.StringBuilder)-Methoden aufgerufen, und anschließend wird die [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString)-Methode aufgerufen, um die Zeichenfolge anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="47a7a-168">The following example calls a number of [StringBuilder](xref:System.Text.StringBuilder) methods and then calls the [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) method to display the string.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      StringBuilder sb = new StringBuilder();
      bool flag = true;
      string[] spellings = { "recieve", "receeve", "receive" };
      sb.AppendFormat("Which of the following spellings is {0}:", flag);
      sb.AppendLine();
      for (int ctr = 0; ctr <= spellings.GetUpperBound(0); ctr++) {
         sb.AppendFormat("   {0}. {1}", ctr, spellings[ctr]);
         sb.AppendLine();
      }
      sb.AppendLine();
      Console.WriteLine(sb.ToString());
   }
}
// The example displays the following output:
//       Which of the following spellings is True:
//          0. recieve
//          1. receeve
//          2. receive
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim sb As New StringBuilder()
      Dim flag As Boolean = True
      Dim spellings() As String = { "recieve", "receeve", "receive" }
      sb.AppendFormat("Which of the following spellings is {0}:", flag)
      sb.AppendLine()
      For ctr As Integer = 0 To spellings.GetUpperBound(0)
         sb.AppendFormat("   {0}. {1}", ctr, spellings(ctr))
         sb.AppendLine()
      Next
      sb.AppendLine()
      Console.WriteLine(sb.ToString())
   End Sub
End Module
' The example displays the following output:
'       Which of the following spellings is True:
'          0. recieve
'          1. receeve
'          2. receive
```

## <a name="see-also"></a><span data-ttu-id="47a7a-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47a7a-169">See Also</span></span>

[<span data-ttu-id="47a7a-170">System.Text.StringBuilder</span><span class="sxs-lookup"><span data-stu-id="47a7a-170">System.Text.StringBuilder</span></span>](xref:System.Text.StringBuilder)

[<span data-ttu-id="47a7a-171">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="47a7a-171">Basic string operations</span></span>](basic-string-operations.md)

[<span data-ttu-id="47a7a-172">Formatierung von Typen</span><span class="sxs-lookup"><span data-stu-id="47a7a-172">Formatting types</span></span>](formatting-types.md)

