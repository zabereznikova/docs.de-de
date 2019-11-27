---
title: Mathematische Funktionen
ms.date: 07/20/2015
helpviewer_keywords:
- math functions, Visual Basic
- arithmetic operations, math functions
- math routines
- Atn function
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
ms.openlocfilehash: b1cd6a846a7dc1dddcf6bdb5eb99ebc1c57a012c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348065"
---
# <a name="math-functions-visual-basic"></a>Mathematische Funktionen (Visual Basic)
Die Methoden der <xref:System.Math?displayProperty=nameWithType>-Klasse stellen die serialisierungsometrische, logarithmische und andere gängige mathematische Funktionen bereit.  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle sind die Methoden der <xref:System.Math?displayProperty=nameWithType>-Klasse aufgelistet. Sie können diese in einem Visual Basic-Programm verwenden.  
  
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
  
 Wenn Sie diese Funktionen ohne Qualifikation verwenden möchten, importieren Sie den <xref:System.Math?displayProperty=nameWithType>-Namespace in Ihr Projekt, indem Sie den folgenden Code am Anfang der Quelldatei einfügen:  
  
```vb
Imports System.Math  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Math.Abs%2A>-Methode der <xref:System.Math>-Klasse verwendet, um den absoluten Wert einer Zahl zu berechnen.  
  
```vb
' Returns 50.3.  
Dim MyNumber1 As Double = Math.Abs(50.3)  
' Returns 50.3.  
Dim MyNumber2 As Double = Math.Abs(-50.3)  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Math.Atan%2A>-Methode der <xref:System.Math>-Klasse verwendet, um den Wert von Pi zu berechnen.  
  
```vb
Public Function GetPi() As Double  
    ' Calculate the value of pi.  
    Return 4.0 * Math.Atan(1.0)  
End Function  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Math.Cos%2A>-Methode der <xref:System.Math>-Klasse verwendet, um den Kosinus eines Winkels zurückzugeben.  
  
```vb
Public Function Sec(ByVal angle As Double) As Double  
    ' Calculate the secant of angle, in radians.  
    Return 1.0 / Math.Cos(angle)  
End Function  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Math.Exp%2A>-Methode der <xref:System.Math>-Klasse verwendet, um e an einen Strom zurückzugeben.  
  
```vb
Public Function Sinh(ByVal angle As Double) As Double  
    ' Calculate hyperbolic sine of an angle, in radians.  
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0  
End Function  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Math.Log%2A>-Methode der <xref:System.Math>-Klasse verwendet, um den natürlichen Logarithmus einer Zahl zurückzugeben.  
  
```vb
Public Function Asinh(ByVal value As Double) As Double  
    ' Calculate inverse hyperbolic sine, in radians.  
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))  
End Function  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Math.Round%2A>-Methode der <xref:System.Math>-Klasse verwendet, um eine Zahl auf die nächste ganze Zahl zu runden.  
  
```vb
' Returns 3.  
Dim MyVar2 As Double = Math.Round(2.8)  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Math.Sign%2A>-Methode der <xref:System.Math>-Klasse verwendet, um das Vorzeichen einer Zahl zu bestimmen.  
  
```vb
' Returns 1.  
Dim MySign1 As Integer = Math.Sign(12)  
' Returns -1.  
Dim MySign2 As Integer = Math.Sign(-2.4)  
' Returns 0.  
Dim MySign3 As Integer = Math.Sign(0)  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Math.Sin%2A>-Methode der <xref:System.Math>-Klasse verwendet, um den Sinus eines Winkels zurückzugeben.  
  
```vb
Public Function Csc(ByVal angle As Double) As Double  
    ' Calculate cosecant of an angle, in radians.  
    Return 1.0 / Math.Sin(angle)  
End Function  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Math.Sqrt%2A>-Methode der <xref:System.Math>-Klasse verwendet, um die Quadratwurzel einer Zahl zu berechnen.  
  
```vb
' Returns 2.  
Dim MySqr1 As Double = Math.Sqrt(4)  
' Returns 4.79583152331272.  
Dim MySqr2 As Double = Math.Sqrt(23)  
' Returns 0.  
Dim MySqr3 As Double = Math.Sqrt(0)  
' Returns NaN (not a number).  
Dim MySqr4 As Double = Math.Sqrt(-4)  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die <xref:System.Math.Tan%2A>-Methode der <xref:System.Math>-Klasse verwendet, um den Tangens eines Winkels zurückzugeben.  
  
```vb
Public Function Ctan(ByVal angle As Double) As Double  
    ' Calculate cotangent of an angle, in radians.  
    Return 1.0 / Math.Tan(angle)  
End Function  
```  
  
## <a name="requirements"></a>Voraussetzungen  
 **Klasse:** <xref:System.Math>  
  
 **Namespace:** <xref:System>  
  
 **Assembly:** mscorlib (in "mscorlib. dll")  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>
- <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>
- <xref:System.Double.NaN>
- [Abgeleitete mathematische Funktionen](../../../visual-basic/language-reference/keywords/derived-math-functions.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
