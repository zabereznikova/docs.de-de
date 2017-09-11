---
title: Analysieren anderer Zeichenfolgen in .NET
description: Analysieren anderer Zeichenfolgen in .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 67670b10-3df4-45ea-8908-5ba3f056887c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: db80cc5f37e814f224ff76b14a906bb4d41064fb
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-other-strings-in-net"></a><span data-ttu-id="9e4ae-104">Analysieren anderer Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="9e4ae-104">Parsing other strings in .NET</span></span>

<span data-ttu-id="9e4ae-105">Neben den numerischen und den [DateTime](xref:System.DateTime)-Zeichenfolgen können Sie auch Zeichenfolgen, die die Typen [Char](xref:System.Char), [Boolean](xref:System.Boolean) und [Enum](xref:System.Enum) darstellen, in Datentypen analysieren.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-105">In addition to numeric and [DateTime](xref:System.DateTime) strings, you can also parse strings that represent the types [Char](xref:System.Char), [Boolean](xref:System.Boolean), and [Enum](xref:System.Enum) into data types.</span></span>

## <a name="char"></a><span data-ttu-id="9e4ae-106">Char</span><span class="sxs-lookup"><span data-stu-id="9e4ae-106">Char</span></span>

<span data-ttu-id="9e4ae-107">Die statische Parse-Methode, die dem [Char](xref:System.Char)-Datentyp zugeordnet ist, eignet sich zum Konvertieren einer Zeichenfolge mit einem einzigen Zeichen in den entsprechenden Unicode-Wert.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-107">The static parse method associated with the [Char](xref:System.Char) data type is useful for converting a string that contains a single character into its Unicode value.</span></span> <span data-ttu-id="9e4ae-108">Im folgenden Codebeispiel wird eine Zeichenfolge in ein Unicode-Zeichen analysiert.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-108">The following code example parses a string into a Unicode character.</span></span>

```csharp
string MyString1 = "A";
char MyChar = Char.Parse(MyString1);
// MyChar now contains a Unicode "A" character.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="boolean"></a><span data-ttu-id="9e4ae-109">Boolesch</span><span class="sxs-lookup"><span data-stu-id="9e4ae-109">Boolean</span></span>

<span data-ttu-id="9e4ae-110">Der [Boolean](xref:System.Boolean)-Datentyp enthält eine [Parse](xref:System.Boolean.Parse(System.String))-Methode, mit der Sie eine Zeichenfolge, die einen `Boolean`-Wert darstellt, in einen tatsächlichen `Boolean`-Typ konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-110">The [Boolean](xref:System.Boolean) data type contains a [Parse](xref:System.Boolean.Parse(System.String)) method that you can use to convert a string that represents a `Boolean` value into an actual `Boolean` type.</span></span> <span data-ttu-id="9e4ae-111">Diese Methode ist von der Groß-/Kleinschreibung unabhängig und kann erfolgreich eine Zeichenfolge mit „True“ oder „False“ analysieren.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-111">This method is not case-sensitive and can successfully parse a string containing "True" or "False."</span></span> <span data-ttu-id="9e4ae-112">Die dem `Boolean`-Typ zugeordnete `Parse`-Methode kann auch Zeichenfolgen analysieren, die von Leerzeichen eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-112">The `Parse` method associated with the `Boolean` type can also parse strings that are surrounded by white spaces.</span></span> <span data-ttu-id="9e4ae-113">Wenn eine beliebige andere Zeichenfolge übergeben wird, wird eine [FormatException](xref:System.FormatException) ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-113">If any other string is passed, a [FormatException](xref:System.FormatException) is thrown.</span></span>

<span data-ttu-id="9e4ae-114">Im folgenden Codebeispiel wird die `Parse`-Methode zum Konvertieren einer Zeichenfolge in einen `Boolean`-Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-114">The following code example uses the `Parse` method to convert a string into a `Boolean` value.</span></span>

```csharp
string MyString2 = "True";
bool MyBool = bool.Parse(MyString2);
// MyBool now contains a True Boolean value.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="enumeration"></a><span data-ttu-id="9e4ae-115">Enumeration</span><span class="sxs-lookup"><span data-stu-id="9e4ae-115">Enumeration</span></span>

<span data-ttu-id="9e4ae-116">Mit der statischen [Parse](xref:System.Enum.Parse(System.Type,System.String))-Methode können Sie einen Enumerationstyp auf den Wert einer Zeichenfolge initialisieren.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-116">You can use the static [Parse](xref:System.Enum.Parse(System.Type,System.String)) method to initialize an enumeration type to the value of a string.</span></span> <span data-ttu-id="9e4ae-117">Diese Methode akzeptiert den zu analysierenden Enumerationstyp, die zu analysierende Zeichenfolge und ein optionales `Boolean`-Flag, das angibt, ob bei der Analyse die Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-117">This method accepts the enumeration type you are parsing, the string to parse, and an optional `Boolean` flag indicating whether or not the parse is case-sensitive.</span></span> <span data-ttu-id="9e4ae-118">Die zu analysierende Zeichenfolge kann mehrere durch Kommas voneinander getrennte Werte enthalten, denen ein oder mehrere Leerzeichen (auch als Leerräume bezeichnet) voran- oder nachgestellt sein können.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-118">The string you are parsing can contain several values separated by commas, which can be preceded or followed by one or more empty spaces (also called white spaces).</span></span> <span data-ttu-id="9e4ae-119">Wenn die Zeichenfolge mehrere Werte enthält, entspricht der Wert des zurückgegebenen Objekts dem Wert aller angegebenen Werte, kombiniert mit einem bitweisen OR-Vorgang.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-119">When the string contains multiple values, the value of the returned object is the value of all specified values combined with a bitwise OR operation.</span></span>

<span data-ttu-id="9e4ae-120">Im folgenden Beispiel wird die `Parse`-Methode zum Konvertieren einer Zeichenfolgendarstellung in einen Enumerationswert verwendet.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-120">The following example uses the `Parse` method to convert a string representation into an enumeration value.</span></span> <span data-ttu-id="9e4ae-121">Die [DayOfWeek](xref:System.DayOfWeek)-Enumeration wird über eine Zeichenfolge mit Donnerstag initialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e4ae-121">The [DayOfWeek](xref:System.DayOfWeek) enumeration is initialized to Thursday from a string.</span></span>

```csharp
string MyString3 = "Thursday";
DayOfWeek MyDays = (DayOfWeek)Enum.Parse(typeof(DayOfWeek), MyString3);
Console.WriteLine(MyDays);
// The result is Thursday.
```

```vb
Dim MyString3 As String = "Thursday"
Dim MyDays As DayOfWeek = CType([Enum].Parse(GetType(DayOfWeek), MyString3), DayOfWeek)
Console.WriteLine("{0:G}", MyDays)
' The result is Thursday.
```

## <a name="see-also"></a><span data-ttu-id="9e4ae-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e4ae-122">See Also</span></span>

[<span data-ttu-id="9e4ae-123">Analysieren von Zeichenfolgen in .NET</span><span class="sxs-lookup"><span data-stu-id="9e4ae-123">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="9e4ae-124">Formatieren von Typen in .NET</span><span class="sxs-lookup"><span data-stu-id="9e4ae-124">Formatting types in .NET</span></span>](formatting-types.md)

[<span data-ttu-id="9e4ae-125">Typkonvertierung in .NET</span><span class="sxs-lookup"><span data-stu-id="9e4ae-125">Type conversion in .NET</span></span>](type-conversion.md)


