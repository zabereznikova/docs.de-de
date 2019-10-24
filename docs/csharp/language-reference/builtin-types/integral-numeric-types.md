---
title: Integrale numerische Typen – C#-Referenz
description: Erfahren Sie mehr über den Bereich, die Speichergröße und die Verwendung für jeden integralen numerischen Typen.
ms.date: 10/18/2019
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
ms.openlocfilehash: 3d4f3164d67a000123417619f3be6be455d5ab87
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579192"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="06e10-103">Integrale numerische Typen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="06e10-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="06e10-104">Die **integralen numerischen Typen** sind eine Teilmenge der **einfachen Typen** und können mit [*Literalen*](#integer-literals) initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="06e10-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integer-literals).</span></span> <span data-ttu-id="06e10-105">Alle integrale Typen sind auch Werttypen.</span><span class="sxs-lookup"><span data-stu-id="06e10-105">All integral types are also value types.</span></span> <span data-ttu-id="06e10-106">Alle integralen numerischen Typen unterstützen [arithmetic](../operators/arithmetic-operators.md)-, [bitwise logical](../operators/bitwise-and-shift-operators.md)-, [comparison](../operators/comparison-operators.md)- and [equality](../operators/equality-operators.md)-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="06e10-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="06e10-107">Merkmale der integralen Typen</span><span class="sxs-lookup"><span data-stu-id="06e10-107">Characteristics of the integral types</span></span>

<span data-ttu-id="06e10-108">C# unterstützt die folgenden vordefinierten integralen Typen:</span><span class="sxs-lookup"><span data-stu-id="06e10-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="06e10-109">C#-Typ/Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="06e10-109">C# type/keyword</span></span>|<span data-ttu-id="06e10-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="06e10-110">Range</span></span>|<span data-ttu-id="06e10-111">Größe</span><span class="sxs-lookup"><span data-stu-id="06e10-111">Size</span></span>|<span data-ttu-id="06e10-112">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="06e10-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="06e10-113">–128 bis 127</span><span class="sxs-lookup"><span data-stu-id="06e10-113">-128 to 127</span></span>|<span data-ttu-id="06e10-114">Ganze 8-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="06e10-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="06e10-115">0 bis 255</span><span class="sxs-lookup"><span data-stu-id="06e10-115">0 to 255</span></span>|<span data-ttu-id="06e10-116">8-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="06e10-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="06e10-117">–32.768 bis 32.767</span><span class="sxs-lookup"><span data-stu-id="06e10-117">-32,768 to 32,767</span></span>|<span data-ttu-id="06e10-118">Ganze 16-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="06e10-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="06e10-119">0 bis 65.535</span><span class="sxs-lookup"><span data-stu-id="06e10-119">0 to 65,535</span></span>|<span data-ttu-id="06e10-120">16-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="06e10-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="06e10-121">-2,147,483,648 bis 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="06e10-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="06e10-122">Eine 32-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="06e10-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="06e10-123">0 bis 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="06e10-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="06e10-124">32-Bit Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="06e10-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="06e10-125">-9,223,372,036,854,775,808 bis 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="06e10-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="06e10-126">64-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="06e10-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="06e10-127">0 bis 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="06e10-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="06e10-128">64-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="06e10-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="06e10-129">In der obigen Tabelle ist jedes C#-Typschlüsselwort aus der äußerst linken Spalte ein Alias für den entsprechenden .NET-Typ.</span><span class="sxs-lookup"><span data-stu-id="06e10-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="06e10-130">Sie können synonym verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="06e10-130">They are interchangeable.</span></span> <span data-ttu-id="06e10-131">In den folgenden Deklarationen werden beispielsweise Variablen des gleichen Typs deklariert:</span><span class="sxs-lookup"><span data-stu-id="06e10-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="06e10-132">Der Standardwert jedes integralen Typs ist Null (`0`).</span><span class="sxs-lookup"><span data-stu-id="06e10-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="06e10-133">Die einzelnen integralen Typen verfügen jeweils über die Konstanten `MinValue` und `MaxValue`, die den minimalen und maximalen Wert des Typs angeben.</span><span class="sxs-lookup"><span data-stu-id="06e10-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="06e10-134">Verwenden Sie die <xref:System.Numerics.BigInteger?displayProperty=nameWithType>-Struktur, um eine ganze Zahl mit Vorzeichen ohne obere oder untere Grenzen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="06e10-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="06e10-135">Ganzzahlenliteral</span><span class="sxs-lookup"><span data-stu-id="06e10-135">Integer literals</span></span>

<span data-ttu-id="06e10-136">Ganzzahlenliterale können die folgenden Typen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="06e10-136">Integer literals can be</span></span>

- <span data-ttu-id="06e10-137">*Dezimal* : ohne Präfix</span><span class="sxs-lookup"><span data-stu-id="06e10-137">*decimal*: without any prefix</span></span>
- <span data-ttu-id="06e10-138">*Hexadezimal*: mit dem Präfix `0x` oder `0X`</span><span class="sxs-lookup"><span data-stu-id="06e10-138">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="06e10-139">*Binär*: mit dem Präfix `0b` oder `0B` (verfügbar in C# 7.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="06e10-139">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="06e10-140">Der folgende Code zeigt ein Beispiel für jeden Typ:</span><span class="sxs-lookup"><span data-stu-id="06e10-140">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="06e10-141">Das vorherige Beispiel zeigt auch die Verwendung von `_` als *Zifferntrennzeichen*, das ab C# 7.0 unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="06e10-141">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="06e10-142">Sie können das Zifferntrennzeichen mit allen Arten numerischer Literale verwenden.</span><span class="sxs-lookup"><span data-stu-id="06e10-142">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="06e10-143">Der Typ eines integralen Literals wird wie folgt durch sein Suffix bestimmt:</span><span class="sxs-lookup"><span data-stu-id="06e10-143">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="06e10-144">Wenn das Literal kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann: `int`, `uint`, `long`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="06e10-144">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="06e10-145">Wenn das Literal das Suffix `U` oder `u` aufweist, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann: `uint`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="06e10-145">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="06e10-146">Wenn das Literal das Suffix `L` oder `l` aufweist, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann: `long`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="06e10-146">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="06e10-147">Sie können den Kleinbuchstaben `l` als Suffix verwenden.</span><span class="sxs-lookup"><span data-stu-id="06e10-147">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="06e10-148">Allerdings erzeugt dies eine Compilerwarnung, weil der Buchstabe `l` leicht mit der Zahl `1` verwechselt werden kann.</span><span class="sxs-lookup"><span data-stu-id="06e10-148">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="06e10-149">Verwenden Sie aus Gründen der Klarheit `L`.</span><span class="sxs-lookup"><span data-stu-id="06e10-149">Use `L` for clarity.</span></span>

- <span data-ttu-id="06e10-150">Wenn das Literal das Suffix `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU` oder `lu` aufweist, ist sein Typ `ulong`.</span><span class="sxs-lookup"><span data-stu-id="06e10-150">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="06e10-151">Wenn der von einem Integer-Literal dargestellte Wert <xref:System.UInt64.MaxValue?displayProperty=nameWithType> überschreitet, tritt der Compilerfehler [CS1021](../../misc/cs1021.md) auf.</span><span class="sxs-lookup"><span data-stu-id="06e10-151">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="06e10-152">Der durch ein Ganzzahlliteral dargestellte Wert kann implizit in einen Typ mit einem kleineren Bereich als der festgelegte Typ des Literals konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="06e10-152">The value represented by an integer literal can be implicitly converted to a type with a smaller range than the determined type of the literal.</span></span> <span data-ttu-id="06e10-153">Dies ist möglich, wenn der Wert innerhalb des Bereichs des Zieltyps liegt:</span><span class="sxs-lookup"><span data-stu-id="06e10-153">That's possible when the value is within the range of the destination type:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="06e10-154">Wie das vorherige Beispiel zeigt, tritt der Compilerfehler [CS0031](../../misc/cs0031.md) auf, wenn der Wert des Literals nicht innerhalb des Bereichs des Zieltyps liegt.</span><span class="sxs-lookup"><span data-stu-id="06e10-154">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="06e10-155">Sie können auch eine Umwandlung verwenden, um den Wert, der durch ein Ganzzahlliteral dargestellt wird, in einen anderen Typ als den festgelegten Literaltyp zu konvertieren:</span><span class="sxs-lookup"><span data-stu-id="06e10-155">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="06e10-156">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="06e10-156">Conversions</span></span>

<span data-ttu-id="06e10-157">Zwischen zwei beliebigen integralen Typen gibt es eine implizite Konvertierung (*verbreiternde Konvertierung* genannt), bei der der Zieltyp alle Werte des Quelltyps speichern kann.</span><span class="sxs-lookup"><span data-stu-id="06e10-157">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="06e10-158">Zum Beispiel gibt es eine implizite Konvertierung von `int` nach `long`, da der Bereich der `int`-Werte eine korrekte Teilmenge von `long` ist.</span><span class="sxs-lookup"><span data-stu-id="06e10-158">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="06e10-159">Es gibt implizite Konvertierungen von einem kleineren integral Typ ohne Vorzeichen in einen größeren integralen Typ mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="06e10-159">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="06e10-160">Es gibt auch eine implizite Konvertierung von einem beliebigen integralen Typ in einen beliebigen Gleitkommatyp.</span><span class="sxs-lookup"><span data-stu-id="06e10-160">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="06e10-161">Es gibt keine implizite Konvertierung von einem beliebigen integralen Typ mit Vorzeichen in einen beliebigen integralen Typ ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="06e10-161">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="06e10-162">Sie müssen eine explizite Umwandlung verwenden, um einen integralen Typ in einen anderen integralen Typ zu konvertieren, wenn eine implizite Konvertierung vom Quelltyp in den Zieltyp nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="06e10-162">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="06e10-163">Dies wird als *einschränkende Konvertierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="06e10-163">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="06e10-164">Die explizite Anwendung ist erforderlich, da die Konvertierung zu Datenverlust führen kann.</span><span class="sxs-lookup"><span data-stu-id="06e10-164">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="06e10-165">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="06e10-165">C# language specification</span></span>

<span data-ttu-id="06e10-166">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="06e10-166">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="06e10-167">Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="06e10-167">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="06e10-168">Ganzzahlenliterale</span><span class="sxs-lookup"><span data-stu-id="06e10-168">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="06e10-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06e10-169">See also</span></span>

- [<span data-ttu-id="06e10-170">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="06e10-170">C# reference</span></span>](../index.md)
- [<span data-ttu-id="06e10-171">Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="06e10-171">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="06e10-172">Tabelle für Standardwerte</span><span class="sxs-lookup"><span data-stu-id="06e10-172">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="06e10-173">Tabelle zur Formatierung numerischer Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="06e10-173">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="06e10-174">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="06e10-174">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="06e10-175">Numerische Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="06e10-175">Numerics in .NET</span></span>](../../../standard/numerics.md)
