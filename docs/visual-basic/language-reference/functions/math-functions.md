---
title: Mathematische Funktionen
ms.date: 01/27/2020
helpviewer_keywords:
- math functions, Visual Basic
- arithmetic operations, math functions
- math routines
- Atn function
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
ms.openlocfilehash: ea30ae3b30484c1a13d6d540f121c03afb30ba26
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794596"
---
# <a name="math-functions-visual-basic"></a>Mathematische Funktionen (Visual Basic)

Die Methoden der <xref:System.Math?displayProperty=nameWithType>-Klasse stellen die serialisierungsometrische, logarithmische und andere gängige mathematische Funktionen bereit.

## <a name="remarks"></a>Hinweise

In der folgenden Tabelle sind die Methoden der <xref:System.Math?displayProperty=nameWithType>-Klasse aufgelistet. Diese können in einem Visual Basic-Programm verwendet werden:
  
|.NET-Methode|Beschreibung|
|---------------------------|-----------------|
|<xref:System.Math.Abs%2A>|Gibt den absoluten Wert einer Zahl zurück.|
|<xref:System.Math.Acos%2A>|Gibt einen Winkel zurück, dessen Kosinus die angegebene Zahl ist.|
|<xref:System.Math.Asin%2A>|Gibt einen Winkel zurück, dessen Sinus die angegebene Zahl ist.|
|<xref:System.Math.Atan%2A>|Gibt einen Winkel zurück, dessen Tangens die angegebene Zahl ist.|
|<xref:System.Math.Atan2%2A>|Gibt einen Winkel zurück, dessen Tangens der Quotient zweier angegebener Zahlen ist.|
|<xref:System.Math.BigMul%2A>|Gibt das vollständige Produkt der 2 32-Bit-Zahlen zurück.|
|<xref:System.Math.Ceiling%2A>|Gibt den kleinsten ganzzahligen Wert zurück, der größer oder gleich dem angegebenen `Decimal` oder `Double`ist.|
|<xref:System.Math.Cos%2A>|Gibt den Kosinus des angegebenen Winkels zurück.|
|<xref:System.Math.Cosh%2A>|Gibt den Hyperbelkosinus des angegebenen Winkels zurück.|
|<xref:System.Math.DivRem%2A>|Gibt den Quotienten von 2 32-Bit-oder 64-Bit-Ganzzahlen mit Vorzeichen zurück und gibt auch den Rest in einem Output-Parameter zurück.|
|<xref:System.Math.Exp%2A>|Gibt e (die Basis des natürlichen Logarithmus) in der angegebenen Potenz zurück.|
|<xref:System.Math.Floor%2A>|Gibt die größte ganze Zahl zurück, die kleiner oder gleich der angegebenen `Decimal` oder `Double` Zahl ist.|
|<xref:System.Math.IEEERemainder%2A>|Gibt den Rest zurück, der sich aus der Division einer angegebenen Zahl durch eine andere angegebene Zahl ergibt.|
|<xref:System.Math.Log%2A>|Gibt den natürlichen Logarithmus (Basis e) einer angegebenen Zahl oder den Logarithmus einer angegebenen Zahl in einer angegebenen Basis zurück.|
|<xref:System.Math.Log10%2A>|Gibt den Logarithmus einer angegebenen Zahl zur Basis 10 zurück.|
|<xref:System.Math.Max%2A>|Gibt die größere von zwei Zahlen zurück.|
|<xref:System.Math.Min%2A>|Gibt die kleinere von zwei Zahlen zurück.|
|<xref:System.Math.Pow%2A>|Potenziert eine angegebene Zahl mit dem angegebenen Exponenten.|
|<xref:System.Math.Round%2A>|Gibt einen `Decimal` oder `Double` Wert zurück, der auf den nächstgelegenen ganzzahligen Wert oder auf eine angegebene Anzahl von Dezimalstellen gerundet wird.|
|<xref:System.Math.Sign%2A>|Gibt einen `Integer`-Wert zurück, der das Vorzeichen einer Zahl angibt.|
|<xref:System.Math.Sin%2A>|Gibt den Sinus des angegebenen Winkels zurück.|
|<xref:System.Math.Sinh%2A>|Gibt den Hyperbelsinus des angegebenen Winkels zurück.|
|<xref:System.Math.Sqrt%2A>|Gibt die Quadratwurzel einer angegebenen Zahl zurück.|
|<xref:System.Math.Tan%2A>|Gibt den Tangens des angegebenen Winkels zurück.|
|<xref:System.Math.Tanh%2A>|Gibt den Hyperbeltangens des angegebenen Winkels zurück.|
|<xref:System.Math.Truncate%2A>|Berechnet den integralen Teil eines angegebenen `Decimal` oder `Double` Zahl.|

In der folgenden Tabelle sind die Methoden der <xref:System.Math?displayProperty=nameWithType>-Klasse aufgelistet, die nicht in .NET Framework vorhanden sind, jedoch in .NET Standard oder .net Core hinzugefügt wurden:

|.NET-Methode|Beschreibung|Verfügbar in|
|---------------------------|-----------------|-----------|
|<xref:System.Math.Acosh%2A>|Gibt den Winkel zurück, dessen hyperbolischer Kosinus die angegebene Zahl ist.|Ab .net Core 2,1 und .NET Standard 2,1|
|<xref:System.Math.Asinh%2A>|Gibt den Winkel zurück, dessen hyperbolischer Sinus die angegebene Zahl ist.|Ab .net Core 2,1 und .NET Standard 2,1|
|<xref:System.Math.Atanh%2A>|Gibt den Winkel zurück, dessen hyperbolischer Tangens die angegebene Zahl ist.|Ab .net Core 2,1 und .NET Standard 2,1|
|<xref:System.Math.BitDecrement%2A>|Gibt den nächsten kleinsten Wert zurück, der weniger als `x` vergleicht.|Ab .net Core 3,0|
|<xref:System.Math.BitIncrement%2A>|Gibt den nächsten größten Wert zurück, der größer als `x` vergleicht.|Ab .net Core 3,0|
|<xref:System.Math.Cbrt%2A>|Gibt die Kubikwurzel einer angegebenen Zahl zurück.|Ab .net Core 2,1 und .NET Standard 2,1|
|<xref:System.Math.Clamp%2A>|Gibt `value` gebunden an den Inklusivbereich von `min` und `max` zurück.|Ab .net Core 2,0 und .NET Standard 2,1|
|<xref:System.Math.CopySign%2A>|Gibt einen Wert mit dem Betrag `x` und dem Vorzeichen `y` zurück.|Ab .net Core 3,0|
|<xref:System.Math.FusedMultiplyAdd%2A>|Gibt (x \* y) + z als einen ternären Vorgang gerundet zurück.|Ab .net Core 3,0|
|<xref:System.Math.ILogB%2A>|Gibt den Logarithmus einer angegebenen ganzen Zahl zur Basis 2 zurück.|Ab .net Core 3,0|
|<xref:System.Math.Log2%2A>|Gibt den Logarithmus einer angegebenen Zahl zur Basis 2 zurück.|Ab .net Core 3,0|
|<xref:System.Math.MaxMagnitude%2A>|Gibt den größeren Betrag von zwei Gleitkommazahlen mit doppelter Genauigkeit zurück.|Ab .net Core 3,0|
|<xref:System.Math.MinMagnitude%2A>|Gibt den kleineren Betrag von zwei Gleitkommazahlen mit doppelter Genauigkeit zurück.|Ab .net Core 3,0|
|<xref:System.Math.ScaleB%2A>|Gibt eine effiziente Berechnung von x \* 2 ^ n zurück.|Ab .net Core 3,0|

Wenn Sie diese Funktionen ohne Qualifikation verwenden möchten, importieren Sie den <xref:System.Math?displayProperty=nameWithType>-Namespace in Ihr Projekt, indem Sie den folgenden Code am Anfang der Quelldatei einfügen:

```vb
Imports System.Math
```

## <a name="example---abs"></a>Beispiel: ABS

In diesem Beispiel wird die <xref:System.Math.Abs%2A>-Methode der <xref:System.Math>-Klasse verwendet, um den absoluten Wert einer Zahl zu berechnen.

```vb
Dim x As Double = Math.Abs(50.3)
Dim y As Double = Math.Abs(-50.3)
Console.WriteLine(x)
Console.WriteLine(y)
' This example produces the following output:
' 50.3
' 50.3
```  

## <a name="example---atan"></a>Beispiel-Atan

In diesem Beispiel wird die <xref:System.Math.Atan%2A>-Methode der <xref:System.Math>-Klasse verwendet, um den Wert von Pi zu berechnen.

```vb
Public Function GetPi() As Double
    ' Calculate the value of pi.
    Return 4.0 * Math.Atan(1.0)
End Function
```

> [!NOTE]
> Die <xref:System.Math?displayProperty=nameWithType> Klasse enthält <xref:System.Math.PI?displayProperty=nameWithType> Konstantenfeld. Sie können Sie verwenden, anstatt Sie zu berechnen.

## <a name="example---cos"></a>Beispiel: cos

In diesem Beispiel wird die <xref:System.Math.Cos%2A>-Methode der <xref:System.Math>-Klasse verwendet, um den Kosinus eines Winkels zurückzugeben.

```vb
Public Function Sec(angle As Double) As Double
    ' Calculate the secant of angle, in radians.
    Return 1.0 / Math.Cos(angle)
End Function
```

## <a name="example---exp"></a>Beispiel-Exp

In diesem Beispiel wird die <xref:System.Math.Exp%2A>-Methode der <xref:System.Math>-Klasse verwendet, um e an einen Strom zurückzugeben.

```vb
Public Function Sinh(angle As Double) As Double
    ' Calculate hyperbolic sine of an angle, in radians.
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0
End Function
```

## <a name="example---log"></a>Beispiel: Protokoll

In diesem Beispiel wird die <xref:System.Math.Log%2A>-Methode der <xref:System.Math>-Klasse verwendet, um den natürlichen Logarithmus einer Zahl zurückzugeben.

```vb
Public Function Asinh(value As Double) As Double
    ' Calculate inverse hyperbolic sine, in radians.
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))
End Function
```

## <a name="example---round"></a>Beispiel-Round

In diesem Beispiel wird die <xref:System.Math.Round%2A>-Methode der <xref:System.Math>-Klasse verwendet, um eine Zahl auf die nächste ganze Zahl zu runden.

```vb
Dim myVar2 As Double = Math.Round(2.8)
Console.WriteLine(myVar2)
' The code produces the following output:
' 3
```

## <a name="example---sign"></a>Beispiel: Vorzeichen

In diesem Beispiel wird die <xref:System.Math.Sign%2A>-Methode der <xref:System.Math>-Klasse verwendet, um das Vorzeichen einer Zahl zu bestimmen.

```vb
Dim mySign1 As Integer = Math.Sign(12)
Dim mySign2 As Integer = Math.Sign(-2.4)
Dim mySign3 As Integer = Math.Sign(0)
Console.WriteLine(mySign1)
Console.WriteLine(mySign2)
Console.WriteLine(mySign3)
' The code produces the following output:
' 1
' -1
' 0
```

## <a name="example---sin"></a>Beispiel-Sin

In diesem Beispiel wird die <xref:System.Math.Sin%2A>-Methode der <xref:System.Math>-Klasse verwendet, um den Sinus eines Winkels zurückzugeben.

```vb
Public Function Csc(angle As Double) As Double
    ' Calculate cosecant of an angle, in radians.
    Return 1.0 / Math.Sin(angle)
End Function
```

## <a name="example---sqrt"></a>Beispiel: Sqrt

In diesem Beispiel wird die <xref:System.Math.Sqrt%2A>-Methode der <xref:System.Math>-Klasse verwendet, um die Quadratwurzel einer Zahl zu berechnen.

```vb
Dim mySqrt1 As Double = Math.Sqrt(4)
Dim mySqrt2 As Double = Math.Sqrt(23)
Dim mySqrt3 As Double = Math.Sqrt(0)
Dim mySqrt4 As Double = Math.Sqrt(-4)
Console.WriteLine(mySqrt1)
Console.WriteLine(mySqrt2)
Console.WriteLine(mySqrt3)
Console.WriteLine(mySqrt4)
' The code produces the following output:
' 2
' 4.79583152331272
' 0
' NaN
```

## <a name="example---tan"></a>Beispiel: Tan

In diesem Beispiel wird die <xref:System.Math.Tan%2A>-Methode der <xref:System.Math>-Klasse verwendet, um den Tangens eines Winkels zurückzugeben.

```vb
Public Function Ctan(angle As Double) As Double
    ' Calculate cotangent of an angle, in radians.
    Return 1.0 / Math.Tan(angle)
End Function
```

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>
- <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>
- <xref:System.Double.NaN>
- [Abgeleitete mathematische Funktionen](../keywords/derived-math-functions.md)
- [Arithmetische Operatoren](../operators/arithmetic-operators.md)
