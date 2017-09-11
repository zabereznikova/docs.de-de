---
title: "Ändern der Groß-/Kleinschreibung"
description: "Ändern der Groß-/Kleinschreibung"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 646c5afd-8aec-4393-9c00-f68ad2580c68
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 023f40969095627242d3652add853eb999c30c4b
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="changing-case"></a><span data-ttu-id="d132e-104">Ändern der Groß-/Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="d132e-104">Changing case</span></span>

<span data-ttu-id="d132e-105">Wenn Sie eine Anwendung schreiben, die Benutzereingaben akzeptiert, können Sie nicht sicher sein, ob die Daten in Groß- oder Kleinschreibung eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d132e-105">If you write an application that accepts input from a user, you can never be sure what case he or she will use to enter the data.</span></span> <span data-ttu-id="d132e-106">Häufig möchten Sie, dass Zeichenfolgen in einheitlicher Schreibung vorliegen, insbesondere, wenn sie in der Benutzeroberfläche angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d132e-106">Often, you want strings to be cased consistently, particularly if you are displaying them in the user interface.</span></span> <span data-ttu-id="d132e-107">In der folgenden Tabelle werden zwei Methoden zur Änderung der Groß-/Kleinschreibung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d132e-107">The following table describes two case-changing methods.</span></span>

<span data-ttu-id="d132e-108">Methodenname</span><span class="sxs-lookup"><span data-stu-id="d132e-108">Method name</span></span> | <span data-ttu-id="d132e-109">Verwendung</span><span class="sxs-lookup"><span data-stu-id="d132e-109">Use</span></span>
----------- | ---
[<span data-ttu-id="d132e-110">String.ToUpper</span><span class="sxs-lookup"><span data-stu-id="d132e-110">String.ToUpper</span></span>](xref:System.String.ToUpper) | <span data-ttu-id="d132e-111">Konvertiert alle Zeichen in einer Zeichenfolge in Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="d132e-111">Converts all characters in a string to uppercase.</span></span>
[<span data-ttu-id="d132e-112">String.ToLower</span><span class="sxs-lookup"><span data-stu-id="d132e-112">String.ToLower</span></span>](xref:System.String.ToLower) | <span data-ttu-id="d132e-113">Konvertiert alle Zeichen in einer Zeichenfolge in Kleinbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="d132e-113">Converts all characters in a string to lowercase.</span></span>

> [!WARNING]  
> <span data-ttu-id="d132e-114">Beachten Sie, dass die `String.ToUpper`- und die `String.ToLower`-Methode nicht dazu verwendet werden sollten, Zeichenfolgen zu konvertieren, um diese zu vergleichen oder auf Gleichheit zu testen.</span><span class="sxs-lookup"><span data-stu-id="d132e-114">Note that the `String.ToUpper` and `String.ToLower` methods should not be used to convert strings in order to compare them or test them for equality.</span></span> 

## <a name="comparing-strings-of-mixed-case"></a><span data-ttu-id="d132e-115">Vergleichen von Zeichenfolgen in gemischter Schreibung</span><span class="sxs-lookup"><span data-stu-id="d132e-115">Comparing strings of mixed case</span></span>

<span data-ttu-id="d132e-116">Um Zeichenfolgen in gemischter Schreibung zu vergleichen, um zu bestimmen, ob sie gleich sind, rufen Sie eine der Überladungen der [String](xref:System)`Equals`-Methode mit einem *comparisonType*-Parameter auf, und geben Sie entweder den Wert von [StringComparison.CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) oder [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) für das *comparisonType*-Argument an.</span><span class="sxs-lookup"><span data-stu-id="d132e-116">To compare strings of mixed case to determine whether they are equal, their, call one of the overloads of the [String](xref:System) `Equals` method with a *comparisonType* parameter, and provide a value of either [StringComparison.CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) or [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) for the *comparisonType* argument.</span></span> 

<span data-ttu-id="d132e-117">Weitere Informationen finden Sie unter [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen in .NET Framework](best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="d132e-117">For more information, see [Best Practices for Using Strings](best-practices.md).</span></span> 

## <a name="toupper"></a><span data-ttu-id="d132e-118">ToUpper</span><span class="sxs-lookup"><span data-stu-id="d132e-118">ToUpper</span></span>

<span data-ttu-id="d132e-119">Die [String.ToUpper](xref:System.String.ToUpper)-Methode ändert alle Zeichen in einer Zeichenfolge in Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="d132e-119">The [String.ToUpper](xref:System.String.ToUpper) method changes all characters in a string to uppercase.</span></span> <span data-ttu-id="d132e-120">Im folgenden Beispiel wird die Zeichenfolge „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="d132e-120">The following example converts the string "Hello World!"</span></span> <span data-ttu-id="d132e-121">von gemischter Schreibung in Großbuchstaben konvertiert.</span><span class="sxs-lookup"><span data-stu-id="d132e-121">from mixed case to uppercase.</span></span>

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToUpper());
// This example displays the following output:
//       HELLO WORLD!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToUpper())
' This example displays the following output:
'       HELLO WORLD!
```

## <a name="tolower"></a><span data-ttu-id="d132e-122">ToLower</span><span class="sxs-lookup"><span data-stu-id="d132e-122">ToLower</span></span>

<span data-ttu-id="d132e-123">Die [String.ToLower](xref:System.String.ToLower)-Methode entspricht der vorherigen Methode mit dem Unterschied, dass sie alle Zeichen in einer Zeichenfolge in Kleinbuchstaben konvertiert.</span><span class="sxs-lookup"><span data-stu-id="d132e-123">The [String.ToLower](xref:System.String.ToLower) method is similar to the previous method, but instead converts all the characters in a string to lowercase.</span></span> <span data-ttu-id="d132e-124">Im folgenden Beispiel wird die Zeichenfolge „Hello World!“</span><span class="sxs-lookup"><span data-stu-id="d132e-124">The following example converts the string "Hello World!"</span></span> <span data-ttu-id="d132e-125">in Kleinbuchstaben konvertiert.</span><span class="sxs-lookup"><span data-stu-id="d132e-125">to lowercase.</span></span>

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToLower());
// This example displays the following output:
//       hello world!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToLower())
' This example displays the following output:
'       hello world!
```

## <a name="see-also"></a><span data-ttu-id="d132e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d132e-126">See Also</span></span>

[<span data-ttu-id="d132e-127">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="d132e-127">Basic string operations</span></span>](basic-string-operations.md)

