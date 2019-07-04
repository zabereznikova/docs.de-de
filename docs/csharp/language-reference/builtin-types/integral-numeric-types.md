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
# <a name="integral-numeric-types--c-reference"></a>Integrale numerische Typen (C#-Referenz)

Die **integralen numerischen Typen** sind eine Teilmenge der **einfachen Typen** und können mit [*Literalen*](#integral-literals) initialisiert werden. Alle integrale Typen sind auch Werttypen.

Alle integral numerischen Typen unterstützen [arithmetic](../operators/arithmetic-operators.md)-, [bitwise logical](../operators/bitwise-and-shift-operators.md)-, [comparison- and equality](../operators/equality-operators.md)-Operatoren.

## <a name="sizes-and-ranges"></a>Größen und Bereiche

Die folgende Tabelle enthält Größe und Bereich der integralen Typen:

|Typ|Bereich|Größe|  
|----------|-----------|----------|  
|`sbyte`|–128 bis 127|Ganze 8-Bit-Zahl mit Vorzeichen|  
|`byte`|0 bis 255|8-Bit-Ganzzahl ohne Vorzeichen|  
|`short`|–32.768 bis 32.767|Ganze 16-Bit-Zahl mit Vorzeichen|  
|`ushort`|0 bis 65.535|16-Bit-Ganzzahl ohne Vorzeichen|  
|`int`|-2,147,483,648 bis 2,147,483,647|Eine 32-Bit-Ganzzahl mit Vorzeichen|  
|`uint`|0 bis 4.294.967.295|32-Bit Ganzzahl ohne Vorzeichen|  
|`long`|-9,223,372,036,854,775,808 bis 9,223,372,036,854,775,807|64-Bit-Ganzzahl mit Vorzeichen|  
|`ulong`|0 bis 18.446.744.073.709.551.615|64-Bit-Ganzzahl ohne Vorzeichen|  

Der Standardwert aller integralen Typen lautet `0`. Jeder der integralen Typen hat Konstanten mit den Namen `MinValue` und `MaxValue` für den minimalen und maximalen Wert für diesen Typ.

Verwenden Sie die <xref:System.Numerics.BigInteger?displayProperty=nameWithType>-Struktur, um eine ganze Zahl mit Vorzeichen ohne obere oder untere Grenzen darzustellen.

## <a name="integral-literals"></a>Integrale Literale

Integrale Literale können als *dezimale Literale*, *hexadezimale Literale* oder *binäre Literale* angegeben werden. Nachfolgend ist eine Beispielausgabe für jedes Literal dargestellt:

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

Für dezimale Literale ist kein Präfix erforderlich. Das Präfix `x` oder `X` bezeichnet ein *hexadezimales Literal*. Das Präfix `b` oder `B` bezeichnet ein *binäres Literal*. Die Deklaration von `binaryLiteral` zeigt die Verwendung von `_` als *Zifferntrennzeichen* an. Das Zifferntrennzeichen kann mit allen numerischen Literalen verwendet werden. Binäre Literale und das Zifferntrennzeichen `_` werden beginnend mit C# 7.0 unterstützt.

## <a name="literal-suffixes"></a>Literalsuffixe 

Das Suffix `l` oder `L` gibt an, dass das integrale Literal vom Typ `long` sein soll. Das Suffix `ul` oder `UL` gibt den Typ `ulong` an. Wenn das Suffix `L` für ein Literal verwendet wird, das größer als 9.223.372.036.854.775.807 (der Maximalwert von `long`) ist, wird der Wert in den Typ `ulong` umgewandelt. Wenn der von einem Integer-Literal dargestellte Wert <xref:System.UInt64.MaxValue?displayProperty=nameWithType> überschreitet, tritt der Compilerfehler [CS1021](../../misc/cs1021.md) auf. 

> [!NOTE]
> Sie können den Kleinbuchstaben „l“ als Suffix verwenden. Allerdings erzeugt dies eine Compilerwarnung, weil der Buchstabe „l“ leicht mit der Zahl „1“ verwechselt wird. Verwenden Sie aus Gründen der Klarheit „L“.

## <a name="type-of-an-integral-literal"></a>Typ eines integralen Literals

Wenn ein integrales Literal kein Suffix besitzt, ist sein Typ der erste dieser Typen, in dem sein Wert dargestellt werden kann:

1. `int`
1. `uint`
1. `long`
1. `ulong`

Sie können ein integrales Literal in einen Typ mit einem kleineren Bereich als dem Standard konvertieren, indem Sie entweder eine Zuweisung oder eine Umwandlung verwenden:

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

Sie können ein integrales Literal in einen Typ mit einem größeren Bereich als dem Standard konvertieren, indem Sie entweder eine Zuweisung, eine Umwandlung oder ein Suffix für das Literal verwenden:

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a>Konvertierungen

Zwischen zwei beliebigen integralen Typen gibt es eine implizite Konvertierung (*verbreiternde Konvertierung* genannt), bei der der Zieltyp alle Werte des Quelltyps speichern kann. Zum Beispiel gibt es eine implizite Konvertierung von `int` nach `long`, da der Bereich der `int`-Werte eine korrekte Teilmenge von `long` ist. Es gibt implizite Konvertierungen von einem kleineren integral Typ ohne Vorzeichen in einen größeren integralen Typ mit Vorzeichen. Es gibt auch eine implizite Konvertierung von einem beliebigen integralen Typ in einen beliebigen Gleitkommatyp.  Es gibt keine implizite Konvertierung von einem beliebigen integralen Typ mit Vorzeichen in einen beliebigen integralen Typ ohne Vorzeichen.

Sie müssen eine explizite Umwandlung verwenden, um einen integralen Typ in einen anderen integralen Typ zu konvertieren, wenn eine implizite Konvertierung vom Quelltyp in den Zieltyp nicht definiert ist. Dies wird als *einschränkende Konvertierung* bezeichnet. Die explizite Anwendung ist erforderlich, da die Konvertierung zu Datenverlust führen kann.

## <a name="see-also"></a>Siehe auch

- [C#-Sprachenspezifikation – Integrale Typen](~/_csharplang/spec/types.md#integral-types)
- [C#-Referenz](../index.md)
- [Tabelle für Gleitkommatypen](../keywords/floating-point-types-table.md)
- [Tabelle für Standardwerte](../keywords/default-values-table.md)
- [Tabelle zur Formatierung numerischer Ergebnisse](../keywords/formatting-numeric-results-table.md)
- [Tabelle integrierter Typen](../keywords/built-in-types-table.md)
- [Numerische Ausdrücke in .NET](../../../standard/numerics.md)
