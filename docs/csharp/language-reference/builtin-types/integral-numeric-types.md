---
title: Integrale numerische Typen – C#-Referenz
description: Erfahren Sie mehr über den Bereich, die Speichergröße und die Verwendung für jeden integralen numerischen Typen.
ms.date: 10/22/2019
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
ms.openlocfilehash: 394a809a9a2f45f4aee652d0eca892f62f0f2e54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093200"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="eee27-103">Integrale numerische Typen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="eee27-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="eee27-104">Die *integralen numerischen Typen* stellen ganze Zahlen dar.</span><span class="sxs-lookup"><span data-stu-id="eee27-104">The *integral numeric types* represent integer numbers.</span></span> <span data-ttu-id="eee27-105">Alle integralen numerischen Typen sind [Werttypen](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="eee27-105">All integral numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="eee27-106">Sie sind auch [einfache Typen](value-types.md#built-in-value-types) und können mit [Literalen](#integer-literals) initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="eee27-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#integer-literals).</span></span> <span data-ttu-id="eee27-107">Alle integralen numerischen Typen unterstützen [arithmetic](../operators/arithmetic-operators.md)-, [bitwise logical](../operators/bitwise-and-shift-operators.md)-, [comparison](../operators/comparison-operators.md)- and [equality](../operators/equality-operators.md)-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="eee27-107">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="eee27-108">Merkmale der integralen Typen</span><span class="sxs-lookup"><span data-stu-id="eee27-108">Characteristics of the integral types</span></span>

<span data-ttu-id="eee27-109">C# unterstützt die folgenden vordefinierten integralen Typen:</span><span class="sxs-lookup"><span data-stu-id="eee27-109">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="eee27-110">C#-Typ/Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="eee27-110">C# type/keyword</span></span>|<span data-ttu-id="eee27-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="eee27-111">Range</span></span>|<span data-ttu-id="eee27-112">Größe</span><span class="sxs-lookup"><span data-stu-id="eee27-112">Size</span></span>|<span data-ttu-id="eee27-113">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="eee27-113">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="eee27-114">–128 bis 127</span><span class="sxs-lookup"><span data-stu-id="eee27-114">-128 to 127</span></span>|<span data-ttu-id="eee27-115">Ganze 8-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="eee27-115">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="eee27-116">0 bis 255</span><span class="sxs-lookup"><span data-stu-id="eee27-116">0 to 255</span></span>|<span data-ttu-id="eee27-117">8-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="eee27-117">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="eee27-118">–32.768 bis 32.767</span><span class="sxs-lookup"><span data-stu-id="eee27-118">-32,768 to 32,767</span></span>|<span data-ttu-id="eee27-119">Ganze 16-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="eee27-119">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="eee27-120">0 bis 65.535</span><span class="sxs-lookup"><span data-stu-id="eee27-120">0 to 65,535</span></span>|<span data-ttu-id="eee27-121">16-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="eee27-121">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="eee27-122">-2,147,483,648 bis 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="eee27-122">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="eee27-123">Eine 32-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="eee27-123">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="eee27-124">0 bis 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="eee27-124">0 to 4,294,967,295</span></span>|<span data-ttu-id="eee27-125">32-Bit Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="eee27-125">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="eee27-126">-9,223,372,036,854,775,808 bis 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="eee27-126">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="eee27-127">64-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="eee27-127">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="eee27-128">0 bis 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="eee27-128">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="eee27-129">64-Bit-Ganzzahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="eee27-129">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="eee27-130">In der obigen Tabelle ist jedes C#-Typschlüsselwort aus der äußerst linken Spalte ein Alias für den entsprechenden .NET-Typ.</span><span class="sxs-lookup"><span data-stu-id="eee27-130">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="eee27-131">Sie können synonym verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eee27-131">They are interchangeable.</span></span> <span data-ttu-id="eee27-132">In den folgenden Deklarationen werden beispielsweise Variablen des gleichen Typs deklariert:</span><span class="sxs-lookup"><span data-stu-id="eee27-132">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="eee27-133">Der Standardwert jedes integralen Typs ist Null (`0`).</span><span class="sxs-lookup"><span data-stu-id="eee27-133">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="eee27-134">Die einzelnen integralen Typen verfügen jeweils über die Konstanten `MinValue` und `MaxValue`, die den minimalen und maximalen Wert des Typs angeben.</span><span class="sxs-lookup"><span data-stu-id="eee27-134">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="eee27-135">Verwenden Sie die <xref:System.Numerics.BigInteger?displayProperty=nameWithType>-Struktur, um eine ganze Zahl mit Vorzeichen ohne obere oder untere Grenzen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="eee27-135">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="eee27-136">Ganzzahlenliteral</span><span class="sxs-lookup"><span data-stu-id="eee27-136">Integer literals</span></span>

<span data-ttu-id="eee27-137">Ganzzahlenliterale können die folgenden Typen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="eee27-137">Integer literals can be</span></span>

- <span data-ttu-id="eee27-138">*Dezimal* : ohne Präfix</span><span class="sxs-lookup"><span data-stu-id="eee27-138">*decimal*: without any prefix</span></span>
- <span data-ttu-id="eee27-139">*Hexadezimal*: mit dem Präfix `0x` oder `0X`</span><span class="sxs-lookup"><span data-stu-id="eee27-139">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="eee27-140">*Binär*: mit dem Präfix `0b` oder `0B` (verfügbar in C# 7.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="eee27-140">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="eee27-141">Der folgende Code zeigt ein Beispiel für jeden Typ:</span><span class="sxs-lookup"><span data-stu-id="eee27-141">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="eee27-142">Das vorherige Beispiel zeigt auch die Verwendung von `_` als *Zifferntrennzeichen*, das ab C# 7.0 unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="eee27-142">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="eee27-143">Sie können das Zifferntrennzeichen mit allen Arten numerischer Literale verwenden.</span><span class="sxs-lookup"><span data-stu-id="eee27-143">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="eee27-144">Der Typ eines integralen Literals wird wie folgt durch sein Suffix bestimmt:</span><span class="sxs-lookup"><span data-stu-id="eee27-144">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="eee27-145">Wenn das Literal kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann: `int`, `uint`, `long`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="eee27-145">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="eee27-146">Wenn das Literal das Suffix `U` oder `u` aufweist, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann: `uint`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="eee27-146">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="eee27-147">Wenn das Literal das Suffix `L` oder `l` aufweist, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann: `long`, `ulong`.</span><span class="sxs-lookup"><span data-stu-id="eee27-147">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="eee27-148">Sie können den Kleinbuchstaben `l` als Suffix verwenden.</span><span class="sxs-lookup"><span data-stu-id="eee27-148">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="eee27-149">Allerdings erzeugt dies eine Compilerwarnung, weil der Buchstabe `l` leicht mit der Zahl `1` verwechselt werden kann.</span><span class="sxs-lookup"><span data-stu-id="eee27-149">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="eee27-150">Verwenden Sie aus Gründen der Klarheit `L`.</span><span class="sxs-lookup"><span data-stu-id="eee27-150">Use `L` for clarity.</span></span>

- <span data-ttu-id="eee27-151">Wenn das Literal das Suffix `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU` oder `lu` aufweist, ist sein Typ `ulong`.</span><span class="sxs-lookup"><span data-stu-id="eee27-151">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="eee27-152">Wenn der von einem Integer-Literal dargestellte Wert <xref:System.UInt64.MaxValue?displayProperty=nameWithType> überschreitet, tritt der Compilerfehler [CS1021](../../misc/cs1021.md) auf.</span><span class="sxs-lookup"><span data-stu-id="eee27-152">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="eee27-153">Wenn der festgelegte Typ eines Integerliterals `int` lautet, und der vom Literal dargestellte Wert innerhalb des Bereichs des Zieltyps liegt, kann der Wert implizit in `sbyte`, `byte`, `short`, `ushort`, `uint` oder `ulong` konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="eee27-153">If the determined type of an integer literal is `int` and the value represented by the literal is within the range of the destination type, the value can be implicitly converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="eee27-154">Wie das vorherige Beispiel zeigt, tritt der Compilerfehler [CS0031](../../misc/cs0031.md) auf, wenn der Wert des Literals nicht innerhalb des Bereichs des Zieltyps liegt.</span><span class="sxs-lookup"><span data-stu-id="eee27-154">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="eee27-155">Sie können auch eine Umwandlung verwenden, um den Wert, der durch ein Ganzzahlliteral dargestellt wird, in einen anderen Typ als den festgelegten Literaltyp zu konvertieren:</span><span class="sxs-lookup"><span data-stu-id="eee27-155">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="eee27-156">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="eee27-156">Conversions</span></span>

<span data-ttu-id="eee27-157">Sie können beliebige ganzzahlige numerische Typen in beliebige andere ganzzahlige numerische Typen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="eee27-157">You can convert any integral numeric type to any other integral numeric type.</span></span> <span data-ttu-id="eee27-158">Wenn der Zieltyp alle Werte des Quelltyps speichern kann, handelt es sich um eine implizite Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="eee27-158">If the destination type can store all values of the source type, the conversion is implicit.</span></span> <span data-ttu-id="eee27-159">Andernfalls müssen Sie den [cast-Operator `()`](../operators/type-testing-and-cast.md#cast-operator-) verwenden, um eine explizite Konvertierung aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="eee27-159">Otherwise, you need to use the [cast operator `()`](../operators/type-testing-and-cast.md#cast-operator-) to invoke an explicit conversion.</span></span> <span data-ttu-id="eee27-160">Weitere Informationen finden Sie unter [Built-in numeric conversions](numeric-conversions.md) (Integrierte numerische Konvertierungen).</span><span class="sxs-lookup"><span data-stu-id="eee27-160">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="eee27-161">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="eee27-161">C# language specification</span></span>

<span data-ttu-id="eee27-162">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="eee27-162">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="eee27-163">Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="eee27-163">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="eee27-164">Ganzzahlenliterale</span><span class="sxs-lookup"><span data-stu-id="eee27-164">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="eee27-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eee27-165">See also</span></span>

- [<span data-ttu-id="eee27-166">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="eee27-166">C# reference</span></span>](../index.md)
- [<span data-ttu-id="eee27-167">Werttypen</span><span class="sxs-lookup"><span data-stu-id="eee27-167">Value types</span></span>](value-types.md)
- [<span data-ttu-id="eee27-168">Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="eee27-168">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="eee27-169">Standardmäßige Zahlenformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="eee27-169">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="eee27-170">Numerische Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="eee27-170">Numerics in .NET</span></span>](../../../standard/numerics.md)
