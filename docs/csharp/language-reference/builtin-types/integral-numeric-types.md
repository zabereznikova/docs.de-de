---
title: Integrale numerische Typen – C#-Referenz
description: Erfahren Sie mehr über den Bereich, die Speichergröße und die Verwendung für jeden integralen numerischen Typen.
ms.date: 06/25/2019
f1_keywords:
- byte
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- sbyte
- short
- short_CSharpKeyword
- ushort
- ushort_CSharpKeyword
- int_CSharpKeyword
- int
- uint
- uint_CSharpKeyword
- long_CSharpKeyword
- long
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
- byte keyword [C#]
- sbyte keyword [C#]
- short keyword [C#]
- ushort keyword [C#]
- int keyword [C#]
- uint keyword [C#]
- long keyword [C#]
- ulong keyword [C#]
ms.openlocfilehash: bde0b7cea52951cd72bde6cfd7d8f1c7dbcb8f46
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425595"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="d71fc-103">Integrale numerische Typen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d71fc-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="d71fc-104">Die **integralen numerischen Typen** sind eine Teilmenge der **einfachen Typen** und können mit [*Literalen*](#integral-literals) initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="d71fc-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integral-literals).</span></span> <span data-ttu-id="d71fc-105">Alle integrale Typen sind auch Werttypen.</span><span class="sxs-lookup"><span data-stu-id="d71fc-105">All integral types are also value types.</span></span>

<span data-ttu-id="d71fc-106">Alle integral numerischen Typen unterstützen [arithmetic](../operators/arithmetic-operators.md)-, [bitwise logical](../operators/bitwise-and-shift-operators.md)-, [comparison- and equality](../operators/equality-operators.md)-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="d71fc-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="sizes-and-ranges"></a><span data-ttu-id="d71fc-107">Größen und Bereiche</span><span class="sxs-lookup"><span data-stu-id="d71fc-107">Sizes and ranges</span></span>

<span data-ttu-id="d71fc-108">Die folgende Tabelle enthält Größe und Bereich der integralen Typen:</span><span class="sxs-lookup"><span data-stu-id="d71fc-108">The following table shows the sizes and ranges of the integral types:</span></span>

|<span data-ttu-id="d71fc-109">Typ</span><span class="sxs-lookup"><span data-stu-id="d71fc-109">Type</span></span>|<span data-ttu-id="d71fc-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="d71fc-110">Range</span></span>|<span data-ttu-id="d71fc-111">Größe</span><span class="sxs-lookup"><span data-stu-id="d71fc-111">Size</span></span>|  
|----------|-----------|----------|  
|`sbyte`|<span data-ttu-id="d71fc-112">–128 bis 127</span><span class="sxs-lookup"><span data-stu-id="d71fc-112">-128 to 127</span></span>|<span data-ttu-id="d71fc-113">Ganze 8-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="d71fc-113">Signed 8-bit integer</span></span>|  
|`byte`|<span data-ttu-id="d71fc-114">0 bis 255</span><span class="sxs-lookup"><span data-stu-id="d71fc-114">0 to 255</span></span>|<span data-ttu-id="d71fc-115">8-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="d71fc-115">Unsigned 8-bit integer</span></span>|  
|`short`|<span data-ttu-id="d71fc-116">–32.768 bis 32.767</span><span class="sxs-lookup"><span data-stu-id="d71fc-116">-32,768 to 32,767</span></span>|<span data-ttu-id="d71fc-117">Ganze 16-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="d71fc-117">Signed 16-bit integer</span></span>|  
|`ushort`|<span data-ttu-id="d71fc-118">0 bis 65.535</span><span class="sxs-lookup"><span data-stu-id="d71fc-118">0 to 65,535</span></span>|<span data-ttu-id="d71fc-119">16-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="d71fc-119">Unsigned 16-bit integer</span></span>|  
|`int`|<span data-ttu-id="d71fc-120">-2,147,483,648 bis 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="d71fc-120">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="d71fc-121">Eine 32-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="d71fc-121">Signed 32-bit integer</span></span>|  
|`uint`|<span data-ttu-id="d71fc-122">0 bis 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="d71fc-122">0 to 4,294,967,295</span></span>|<span data-ttu-id="d71fc-123">32-Bit Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="d71fc-123">Unsigned 32-bit integer</span></span>|  
|`long`|<span data-ttu-id="d71fc-124">-9,223,372,036,854,775,808 bis 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="d71fc-124">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="d71fc-125">64-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="d71fc-125">Signed 64-bit integer</span></span>|  
|`ulong`|<span data-ttu-id="d71fc-126">0 bis 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="d71fc-126">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="d71fc-127">64-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="d71fc-127">Unsigned 64-bit integer</span></span>|  

<span data-ttu-id="d71fc-128">Der Standardwert aller integralen Typen lautet `0`.</span><span class="sxs-lookup"><span data-stu-id="d71fc-128">The default value for all integral types is `0`.</span></span> <span data-ttu-id="d71fc-129">Jeder der integralen Typen hat Konstanten mit den Namen `MinValue` und `MaxValue` für den minimalen und maximalen Wert für diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="d71fc-129">Each of the integral types has constants named `MinValue` and `MaxValue` for the minimum and maximum value for that type.</span></span>

<span data-ttu-id="d71fc-130">Verwenden Sie die <xref:System.Numerics.BigInteger?displayProperty=nameWithType>-Struktur, um eine ganze Zahl mit Vorzeichen ohne obere oder untere Grenzen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="d71fc-130">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integral-literals"></a><span data-ttu-id="d71fc-131">Integrale Literale</span><span class="sxs-lookup"><span data-stu-id="d71fc-131">Integral literals</span></span>

<span data-ttu-id="d71fc-132">Integrale Literale können als *dezimale Literale*, *hexadezimale Literale* oder *binäre Literale* angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d71fc-132">Integral literals can be specified as *decimal literals*, *hexadecimal literals*, or *binary literals*.</span></span> <span data-ttu-id="d71fc-133">Nachfolgend ist eine Beispielausgabe für jedes Literal dargestellt:</span><span class="sxs-lookup"><span data-stu-id="d71fc-133">An example of each is shown below:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="d71fc-134">Für dezimale Literale ist kein Präfix erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d71fc-134">Decimal literals don't require any prefix.</span></span> <span data-ttu-id="d71fc-135">Das Präfix `x` oder `X` bezeichnet ein *hexadezimales Literal*.</span><span class="sxs-lookup"><span data-stu-id="d71fc-135">The `x` or `X` prefix signifies a *hexadecimal literal*.</span></span> <span data-ttu-id="d71fc-136">Das Präfix `b` oder `B` bezeichnet ein *binäres Literal*.</span><span class="sxs-lookup"><span data-stu-id="d71fc-136">The `b` or `B` prefix signifies a *binary literal*.</span></span> <span data-ttu-id="d71fc-137">Die Deklaration von `binaryLiteral` zeigt die Verwendung von `_` als *Zifferntrennzeichen* an.</span><span class="sxs-lookup"><span data-stu-id="d71fc-137">The declaration of `binaryLiteral` demonstrates the use of `_` as a *digit separator*.</span></span> <span data-ttu-id="d71fc-138">Das Zifferntrennzeichen kann mit allen numerischen Literalen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d71fc-138">The digit separator can be used with all numeric literals.</span></span> <span data-ttu-id="d71fc-139">Binäre Literale und das Zifferntrennzeichen `_` werden beginnend mit C# 7.0 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d71fc-139">Binary literals and the digit separator `_` are supported starting with C# 7.0.</span></span>

## <a name="literal-suffixes"></a><span data-ttu-id="d71fc-140">Literalsuffixe</span><span class="sxs-lookup"><span data-stu-id="d71fc-140">Literal suffixes</span></span> 

<span data-ttu-id="d71fc-141">Das Suffix `l` oder `L` gibt an, dass das integrale Literal vom Typ `long` sein soll.</span><span class="sxs-lookup"><span data-stu-id="d71fc-141">The `l` or `L` suffix specifies that the integral literal should be of the `long` type.</span></span> <span data-ttu-id="d71fc-142">Das Suffix `ul` oder `UL` gibt den Typ `ulong` an.</span><span class="sxs-lookup"><span data-stu-id="d71fc-142">The `ul` or `UL` suffix specifies the `ulong` type.</span></span> <span data-ttu-id="d71fc-143">Wenn das Suffix `L` für ein Literal verwendet wird, das größer als 9.223.372.036.854.775.807 (der Maximalwert von `long`) ist, wird der Wert in den Typ `ulong` umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="d71fc-143">If the `L` suffix is used on a literal that is greater than 9,223,372,036,854,775,807 (the maximum value of `long`), the value is converted to the `ulong` type.</span></span> <span data-ttu-id="d71fc-144">Wenn der von einem Integer-Literal dargestellte Wert <xref:System.UInt64.MaxValue?displayProperty=nameWithType> überschreitet, tritt der Compilerfehler [CS1021](../../misc/cs1021.md) auf.</span><span class="sxs-lookup"><span data-stu-id="d71fc-144">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span> 

> [!NOTE]
> <span data-ttu-id="d71fc-145">Sie können den Kleinbuchstaben „l“ als Suffix verwenden.</span><span class="sxs-lookup"><span data-stu-id="d71fc-145">You can use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="d71fc-146">Allerdings erzeugt dies eine Compilerwarnung, weil der Buchstabe „l“ leicht mit der Zahl „1“ verwechselt wird.</span><span class="sxs-lookup"><span data-stu-id="d71fc-146">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="d71fc-147">Verwenden Sie aus Gründen der Klarheit „L“.</span><span class="sxs-lookup"><span data-stu-id="d71fc-147">Use "L" for clarity.</span></span>

## <a name="type-of-an-integral-literal"></a><span data-ttu-id="d71fc-148">Typ eines integralen Literals</span><span class="sxs-lookup"><span data-stu-id="d71fc-148">Type of an integral literal</span></span>

<span data-ttu-id="d71fc-149">Wenn ein integrales Literal kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="d71fc-149">If an integral literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
1. `uint`
1. `long`
1. `ulong`

<span data-ttu-id="d71fc-150">Sie können ein integrales Literal in einen Typ mit einem kleineren Bereich als dem Standard konvertieren, indem Sie entweder eine Zuweisung oder eine Umwandlung verwenden:</span><span class="sxs-lookup"><span data-stu-id="d71fc-150">You can convert an integral literal to a type with a smaller range than the default using either an assignment or a cast:</span></span>

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

<span data-ttu-id="d71fc-151">Sie können ein integrales Literal in einen Typ mit einem größeren Bereich als dem Standard konvertieren, indem Sie entweder eine Zuweisung, eine Umwandlung oder ein Suffix für das Literal verwenden:</span><span class="sxs-lookup"><span data-stu-id="d71fc-151">You can convert an integral literal to a type with a larger range than the default using either assignment, a cast, or a suffix on the literal:</span></span>

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="d71fc-152">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d71fc-152">Conversions</span></span>

<span data-ttu-id="d71fc-153">Zwischen zwei beliebigen integralen Typen gibt es eine implizite Konvertierung (*verbreiternde Konvertierung* genannt), bei der der Zieltyp alle Werte des Quelltyps speichern kann.</span><span class="sxs-lookup"><span data-stu-id="d71fc-153">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="d71fc-154">Zum Beispiel gibt es eine implizite Konvertierung von `int` nach `long`, da der Bereich der `int`-Werte eine korrekte Teilmenge von `long` ist.</span><span class="sxs-lookup"><span data-stu-id="d71fc-154">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="d71fc-155">Es gibt implizite Konvertierungen von einem kleineren integral Typ ohne Vorzeichen in einen größeren integralen Typ mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="d71fc-155">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="d71fc-156">Es gibt auch eine implizite Konvertierung von einem beliebigen integralen Typ in einen beliebigen Gleitkommatyp.</span><span class="sxs-lookup"><span data-stu-id="d71fc-156">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="d71fc-157">Es gibt keine implizite Konvertierung von einem beliebigen integralen Typ mit Vorzeichen in einen beliebigen integralen Typ ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="d71fc-157">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="d71fc-158">Sie müssen eine explizite Umwandlung verwenden, um einen integralen Typ in einen anderen integralen Typ zu konvertieren, wenn eine implizite Konvertierung vom Quelltyp in den Zieltyp nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d71fc-158">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="d71fc-159">Dies wird als *einschränkende Konvertierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d71fc-159">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="d71fc-160">Die explizite Anwendung ist erforderlich, da die Konvertierung zu Datenverlust führen kann.</span><span class="sxs-lookup"><span data-stu-id="d71fc-160">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="see-also"></a><span data-ttu-id="d71fc-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d71fc-161">See also</span></span>

- [<span data-ttu-id="d71fc-162">C#-Sprachenspezifikation – Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="d71fc-162">C# language specification - Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="d71fc-163">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d71fc-163">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d71fc-164">Tabelle für Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="d71fc-164">Floating-point types table</span></span>](../keywords/floating-point-types-table.md)
- [<span data-ttu-id="d71fc-165">Tabelle für Standardwerte</span><span class="sxs-lookup"><span data-stu-id="d71fc-165">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="d71fc-166">Tabelle zur Formatierung numerischer Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="d71fc-166">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="d71fc-167">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="d71fc-167">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="d71fc-168">Numerische Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="d71fc-168">Numerics in .NET</span></span>](../../../standard/numerics.md)
