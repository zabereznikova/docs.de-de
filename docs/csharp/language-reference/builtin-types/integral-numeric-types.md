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
ms.openlocfilehash: dfb1298abaff0cfe8eae7536f94511a30012a4a9
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236074"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="485ac-103">Integrale numerische Typen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="485ac-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="485ac-104">Die **integralen numerischen Typen** sind eine Teilmenge der **einfachen Typen** und können mit [*Literalen*](#integral-literals) initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="485ac-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integral-literals).</span></span> <span data-ttu-id="485ac-105">Alle integralen Typen sind auch Werttypen.</span><span class="sxs-lookup"><span data-stu-id="485ac-105">All integral types are also value types.</span></span> <span data-ttu-id="485ac-106">Alle integral numerischen Typen unterstützen [arithmetic](../operators/arithmetic-operators.md)-, [bitwise logical](../operators/bitwise-and-shift-operators.md)-, [comparison- und equality](../operators/equality-operators.md)-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="485ac-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="485ac-107">Merkmale der integralen Typen</span><span class="sxs-lookup"><span data-stu-id="485ac-107">Characteristics of the integral types</span></span>

<span data-ttu-id="485ac-108">C# unterstützt die folgenden vordefinierten integralen Typen:</span><span class="sxs-lookup"><span data-stu-id="485ac-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="485ac-109">C#-Typ/Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="485ac-109">C# type/keyword</span></span>|<span data-ttu-id="485ac-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="485ac-110">Range</span></span>|<span data-ttu-id="485ac-111">Größe</span><span class="sxs-lookup"><span data-stu-id="485ac-111">Size</span></span>|<span data-ttu-id="485ac-112">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="485ac-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="485ac-113">–128 bis 127</span><span class="sxs-lookup"><span data-stu-id="485ac-113">-128 to 127</span></span>|<span data-ttu-id="485ac-114">Ganze 8-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="485ac-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="485ac-115">0 bis 255</span><span class="sxs-lookup"><span data-stu-id="485ac-115">0 to 255</span></span>|<span data-ttu-id="485ac-116">Ganze 8-Bit-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="485ac-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="485ac-117">–32.768 bis 32.767</span><span class="sxs-lookup"><span data-stu-id="485ac-117">-32,768 to 32,767</span></span>|<span data-ttu-id="485ac-118">Ganze 16-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="485ac-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="485ac-119">0 bis 65.535</span><span class="sxs-lookup"><span data-stu-id="485ac-119">0 to 65,535</span></span>|<span data-ttu-id="485ac-120">16-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="485ac-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="485ac-121">-2,147,483,648 bis 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="485ac-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="485ac-122">Eine 32-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="485ac-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="485ac-123">0 bis 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="485ac-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="485ac-124">32-Bit Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="485ac-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="485ac-125">-9,223,372,036,854,775,808 bis 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="485ac-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="485ac-126">64-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="485ac-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="485ac-127">0 bis 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="485ac-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="485ac-128">64-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="485ac-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="485ac-129">In der obigen Tabelle ist jedes C#-Typschlüsselwort aus der äußerst linken Spalte ein Alias für den entsprechenden .NET-Typ.</span><span class="sxs-lookup"><span data-stu-id="485ac-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="485ac-130">Sie können synonym verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="485ac-130">They are interchangeable.</span></span> <span data-ttu-id="485ac-131">In den folgenden Deklarationen werden beispielsweise Variablen des gleichen Typs deklariert:</span><span class="sxs-lookup"><span data-stu-id="485ac-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="485ac-132">Der Standardwert jedes integralen Typs ist Null (`0`).</span><span class="sxs-lookup"><span data-stu-id="485ac-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="485ac-133">Die einzelnen integralen Typen verfügen jeweils über die Konstanten `MinValue` und `MaxValue`, die den minimalen und maximalen Wert des Typs angeben.</span><span class="sxs-lookup"><span data-stu-id="485ac-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="485ac-134">Verwenden Sie die <xref:System.Numerics.BigInteger?displayProperty=nameWithType>-Struktur, um eine ganze Zahl mit Vorzeichen ohne obere oder untere Grenzen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="485ac-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integral-literals"></a><span data-ttu-id="485ac-135">Integrale Literale</span><span class="sxs-lookup"><span data-stu-id="485ac-135">Integral literals</span></span>

<span data-ttu-id="485ac-136">Integrale Literale können als *dezimale Literale*, *hexadezimale Literale* oder *binäre Literale* angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="485ac-136">Integral literals can be specified as *decimal literals*, *hexadecimal literals*, or *binary literals*.</span></span> <span data-ttu-id="485ac-137">Nachfolgend ist eine Beispielausgabe für jedes Literal dargestellt:</span><span class="sxs-lookup"><span data-stu-id="485ac-137">An example of each is shown below:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="485ac-138">Für dezimale Literale ist kein Präfix erforderlich.</span><span class="sxs-lookup"><span data-stu-id="485ac-138">Decimal literals don't require any prefix.</span></span> <span data-ttu-id="485ac-139">Das Präfix `x` oder `X` bezeichnet ein *hexadezimales Literal*.</span><span class="sxs-lookup"><span data-stu-id="485ac-139">The `x` or `X` prefix signifies a *hexadecimal literal*.</span></span> <span data-ttu-id="485ac-140">Das Präfix `b` oder `B` bezeichnet ein *binäres Literal*.</span><span class="sxs-lookup"><span data-stu-id="485ac-140">The `b` or `B` prefix signifies a *binary literal*.</span></span> <span data-ttu-id="485ac-141">Die Deklaration von `binaryLiteral` zeigt die Verwendung von `_` als *Zifferntrennzeichen* an.</span><span class="sxs-lookup"><span data-stu-id="485ac-141">The declaration of `binaryLiteral` demonstrates the use of `_` as a *digit separator*.</span></span> <span data-ttu-id="485ac-142">Das Zifferntrennzeichen kann mit allen numerischen Literalen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="485ac-142">The digit separator can be used with all numeric literals.</span></span> <span data-ttu-id="485ac-143">Binäre Literale und das Zifferntrennzeichen `_` werden beginnend mit C# 7.0 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="485ac-143">Binary literals and the digit separator `_` are supported starting with C# 7.0.</span></span>

### <a name="literal-suffixes"></a><span data-ttu-id="485ac-144">Literalsuffixe</span><span class="sxs-lookup"><span data-stu-id="485ac-144">Literal suffixes</span></span>

<span data-ttu-id="485ac-145">Das Suffix `l` oder `L` gibt an, dass das integrale Literal vom Typ `long` sein soll.</span><span class="sxs-lookup"><span data-stu-id="485ac-145">The `l` or `L` suffix specifies that the integral literal should be of the `long` type.</span></span> <span data-ttu-id="485ac-146">Das Suffix `ul` oder `UL` gibt den Typ `ulong` an.</span><span class="sxs-lookup"><span data-stu-id="485ac-146">The `ul` or `UL` suffix specifies the `ulong` type.</span></span> <span data-ttu-id="485ac-147">Wenn das Suffix `L` für ein Literal verwendet wird, das größer als 9.223.372.036.854.775.807 (der Maximalwert von `long`) ist, wird der Wert in den Typ `ulong` umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="485ac-147">If the `L` suffix is used on a literal that is greater than 9,223,372,036,854,775,807 (the maximum value of `long`), the value is converted to the `ulong` type.</span></span> <span data-ttu-id="485ac-148">Wenn der von einem integralen Literal dargestellte Wert <xref:System.UInt64.MaxValue?displayProperty=nameWithType> überschreitet, tritt der Compilerfehler [CS1021](../../misc/cs1021.md) auf.</span><span class="sxs-lookup"><span data-stu-id="485ac-148">If the value represented by an integral literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span> 

> [!NOTE]
> <span data-ttu-id="485ac-149">Sie können den Kleinbuchstaben „l“ als Suffix verwenden.</span><span class="sxs-lookup"><span data-stu-id="485ac-149">You can use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="485ac-150">Allerdings erzeugt dies eine Compilerwarnung, weil der Buchstabe „l“ leicht mit der Zahl „1“ verwechselt wird.</span><span class="sxs-lookup"><span data-stu-id="485ac-150">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="485ac-151">Verwenden Sie aus Gründen der Klarheit „L“.</span><span class="sxs-lookup"><span data-stu-id="485ac-151">Use "L" for clarity.</span></span>

### <a name="type-of-an-integral-literal"></a><span data-ttu-id="485ac-152">Typ eines integralen Literals</span><span class="sxs-lookup"><span data-stu-id="485ac-152">Type of an integral literal</span></span>

<span data-ttu-id="485ac-153">Wenn ein integrales Literal kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="485ac-153">If an integral literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
1. `uint`
1. `long`
1. `ulong`

<span data-ttu-id="485ac-154">Sie können ein integrales Literal in einen Typ mit einem kleineren Bereich als dem Standard konvertieren, indem Sie entweder eine Zuweisung oder eine Umwandlung verwenden:</span><span class="sxs-lookup"><span data-stu-id="485ac-154">You can convert an integral literal to a type with a smaller range than the default using either an assignment or a cast:</span></span>

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

<span data-ttu-id="485ac-155">Sie können ein integrales Literal in einen Typ mit einem größeren Bereich als dem Standard konvertieren, indem Sie entweder eine Zuweisung, eine Umwandlung oder ein Suffix für das Literal verwenden:</span><span class="sxs-lookup"><span data-stu-id="485ac-155">You can convert an integral literal to a type with a larger range than the default using either assignment, a cast, or a suffix on the literal:</span></span>

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="485ac-156">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="485ac-156">Conversions</span></span>

<span data-ttu-id="485ac-157">Zwischen zwei beliebigen integralen Typen gibt es eine implizite Konvertierung (*erweiternde Konvertierung genannt*), bei der der Zieltyp alle Werte des Quelltyps speichern kann.</span><span class="sxs-lookup"><span data-stu-id="485ac-157">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="485ac-158">Zum Beispiel gibt es eine implizite Konvertierung von `int` nach `long`, da der Bereich der `int`-Werte eine korrekte Teilmenge von `long` ist.</span><span class="sxs-lookup"><span data-stu-id="485ac-158">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="485ac-159">Es gibt implizite Konvertierungen von einem kleineren integralen Typ ohne Vorzeichen in einen größeren integralen Typ mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="485ac-159">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="485ac-160">Es gibt auch eine implizite Konvertierung von einem beliebigen integralen Typ in einen beliebigen Gleitkommatyp.</span><span class="sxs-lookup"><span data-stu-id="485ac-160">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="485ac-161">Es gibt keine implizite Konvertierung von einem beliebigen integralen Typ mit Vorzeichen in einen beliebigen integralen Typ ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="485ac-161">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="485ac-162">Sie müssen eine explizite Umwandlung verwenden, um einen integralen Typ in einen anderen integralen Typ zu konvertieren, wenn eine implizite Konvertierung vom Quelltyp in den Zieltyp nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="485ac-162">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="485ac-163">Dies wird als *einschränkende Konvertierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="485ac-163">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="485ac-164">Die explizite Anwendung ist erforderlich, da die Konvertierung zu Datenverlust führen kann.</span><span class="sxs-lookup"><span data-stu-id="485ac-164">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="see-also"></a><span data-ttu-id="485ac-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="485ac-165">See also</span></span>

- [<span data-ttu-id="485ac-166">C#-Sprachenspezifikation – Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="485ac-166">C# language specification - Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="485ac-167">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="485ac-167">C# reference</span></span>](../index.md)
- [<span data-ttu-id="485ac-168">Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="485ac-168">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="485ac-169">Tabelle für Standardwerte</span><span class="sxs-lookup"><span data-stu-id="485ac-169">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="485ac-170">Tabelle zur Formatierung numerischer Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="485ac-170">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="485ac-171">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="485ac-171">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="485ac-172">Numerische Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="485ac-172">Numerics in .NET</span></span>](../../../standard/numerics.md)
