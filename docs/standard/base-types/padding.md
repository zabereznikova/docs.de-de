---
title: "Auffüllen von Zeichenfolgen"
description: "Auffüllen von Zeichenfolgen"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 1c8b3b44-d370-49e1-90b5-64ac81c02ae91c8b3b44-d370-49e1-90b5-64ac81c02ae9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: bc3cc9028b232cc2ba6ca3130c4bdb261c4a0a42
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="padding-strings"></a><span data-ttu-id="b4d93-104">Auffüllen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="b4d93-104">Padding strings</span></span>

<span data-ttu-id="b4d93-105">Verwenden Sie eine der folgenden [System.String](xref:System.String)-Methoden, um eine neue Zeichenfolge zu erstellen, die aus einer ursprünglichen Zeichenfolge besteht, die mit voran- oder nachgestellten Zeichen auf eine angegebene Gesamtlänge aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="b4d93-105">Use one of the following [System.String](xref:System.String) methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="b4d93-106">Als Auffüllzeichen können Leerzeichen oder ein angegebenes Zeichen verwendet werden, sodass die Zeichenfolge entweder rechtsbündig oder linksbündig ausgerichtet angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b4d93-106">The padding character can be spaces or a specified character, and consequently appears to be either right-aligned or left-aligned.</span></span>

<span data-ttu-id="b4d93-107">Methodenname</span><span class="sxs-lookup"><span data-stu-id="b4d93-107">Method name</span></span> | <span data-ttu-id="b4d93-108">Verwendung</span><span class="sxs-lookup"><span data-stu-id="b4d93-108">Use</span></span>
----------- | ---
<span data-ttu-id="b4d93-109">[String.PadLeft](xref:System.String.PadLeft(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="b4d93-109">[String.PadLeft](xref:System.String.PadLeft(System.Int32))</span></span> | <span data-ttu-id="b4d93-110">Füllt eine Zeichenfolge mit vorangestellten Zeichen auf, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="b4d93-110">Pads a string with leading characters to a specified total length.</span></span>
<span data-ttu-id="b4d93-111">[String.PadRight](xref:System.String.PadRight(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="b4d93-111">[String.PadRight](xref:System.String.PadRight(System.Int32))</span></span> | <span data-ttu-id="b4d93-112">Füllt eine Zeichenfolge mit nachgestellten Zeichen auf, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="b4d93-112">Pads a string with trailing characters to a specified total length.</span></span>

## <a name="padleft"></a><span data-ttu-id="b4d93-113">PadLeft</span><span class="sxs-lookup"><span data-stu-id="b4d93-113">PadLeft</span></span>

<span data-ttu-id="b4d93-114">Die [String.PadLeft](xref:System.String.PadLeft(System.Int32))-Methode erstellt eine neue Zeichenfolge durch die Verkettung einer ausreichenden Anzahl vorangestellter Auffüllzeichen mit einer ursprünglichen Zeichenfolge, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="b4d93-114">The [String.PadLeft](xref:System.String.PadLeft(System.Int32)) method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="b4d93-115">Die [String.PadLeft(Int32)](xref:System.String.PadLeft(System.Int32))-Methode verwendet Leerzeichen als Auffüllzeichen, und mit der Methode [String.PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) können Sie Ihre eigenen Auffüllzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="b4d93-115">The [String.PadLeft(Int32)](xref:System.String.PadLeft(System.Int32)) method uses white space as the padding character and the [String.PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) method enables you to specify your own padding character.</span></span>

<span data-ttu-id="b4d93-116">Im folgenden Codebeispiel wird über die Methode [PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) eine neue Zeichenfolge erstellt, die&20; Zeichen lang ist.</span><span class="sxs-lookup"><span data-stu-id="b4d93-116">The following code example uses the [PadLeft(Int32, Char)](xref:System.String.PadLeft(System.Int32,System.Char)) method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="b4d93-117">In diesem Beispiel wird „`--------Hello World!`“ auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4d93-117">The example displays "`--------Hello World!`" to the console.</span></span>

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadLeft(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadLeft(20, "-"c))
```

## <a name="padright"></a><span data-ttu-id="b4d93-118">PadRight</span><span class="sxs-lookup"><span data-stu-id="b4d93-118">PadRight</span></span>

<span data-ttu-id="b4d93-119">Die [String.PadRight](xref:System.String.PadRight(System.Int32))-Methode erstellt eine neue Zeichenfolge durch die Verkettung einer ausreichenden Anzahl nachgestellter Auffüllzeichen mit einer ursprünglichen Zeichenfolge, um eine angegebene Gesamtlänge zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="b4d93-119">The [String.PadRight](xref:System.String.PadRight(System.Int32)) method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="b4d93-120">Die [String.PadRight(Int32)](xref:System.String.PadRight(System.Int32))-Methode verwendet Leerzeichen als Auffüllzeichen, und mit der Methode [String.PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) können Sie Ihre eigenen Auffüllzeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="b4d93-120">The [String.PadRight(Int32)](xref:System.String.PadRight(System.Int32)) method uses white space as the padding character and the [String.PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) method enables you to specify your own padding character.</span></span>

<span data-ttu-id="b4d93-121">Im folgenden Codebeispiel wird über die Methode [PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) eine neue Zeichenfolge erstellt, die&20; Zeichen lang ist.</span><span class="sxs-lookup"><span data-stu-id="b4d93-121">The following code example uses the [PadRight(Int32, Char)](xref:System.String.PadRight(System.Int32,System.Char)) method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="b4d93-122">In diesem Beispiel wird „`Hello World!--------`“ auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4d93-122">The example displays "`Hello World!--------`" to the console.</span></span>

```csharp
string MyString = "Hello World!";
Console.WriteLine(MyString.PadRight(20, '-'));
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.PadRight(20, "-"c))
```

## <a name="see-also"></a><span data-ttu-id="b4d93-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4d93-123">See Also</span></span>

[<span data-ttu-id="b4d93-124">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="b4d93-124">Basic string operations</span></span>](basic-string-operations.md)


