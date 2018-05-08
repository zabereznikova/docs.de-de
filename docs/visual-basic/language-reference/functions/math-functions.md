---
title: Mathematische Funktionen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- math functions, Visual Basic
- arithmetic operations, math functions
- math routines
- Atn function
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
ms.openlocfilehash: 9c55b48cbc285ab5ed8742a23af43d3a017a35e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="math-functions-visual-basic"></a>Mathematische Funktionen (Visual Basic)
Die Methoden der <xref:System.Math?displayProperty=nameWithType> Klasse bereitstellen trigonometrische, logarithmische und andere gebräuchliche mathematische Funktionen.  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Tabelle listet die Methoden der <xref:System.Math?displayProperty=nameWithType> Klasse. Sie können diese in einem Visual Basic-Programm verwenden.  
  
|.NET Framework-Methode|Beschreibung|  
|---------------------------|-----------------|  
|<xref:System.Math.Abs%2A>|Gibt den absoluten Wert einer Zahl zurück.|  
|<xref:System.Math.Acos%2A>|Gibt einen Winkel zurück, dessen Kosinus die angegebene Zahl ist.|  
|<xref:System.Math.Asin%2A>|Gibt einen Winkel zurück, dessen Sinus die angegebene Zahl ist.|  
|<xref:System.Math.Atan%2A>|Gibt einen Winkel zurück, dessen Tangens die angegebene Zahl ist.|  
|<xref:System.Math.Atan2%2A>|Gibt einen Winkel zurück, dessen Tangens der Quotient zweier angegebener Zahlen ist.|  
|<xref:System.Math.BigMul%2A>|Gibt das volle Produkt zweier 32-Bit-Zahlen zurück.|  
|<xref:System.Math.Ceiling%2A>|Gibt den kleinsten ganzzahligen Wert, der größer als oder gleich einem angegebenen `Decimal` oder `Double`.|  
|<xref:System.Math.Cos%2A>|Gibt den Kosinus des angegebenen Winkels zurück.|  
|<xref:System.Math.Cosh%2A>|Gibt den Hyperbelkosinus des angegebenen Winkels zurück.|  
|<xref:System.Math.DivRem%2A>|Gibt den Quotienten zweier 32-Bit oder 64-Bit-Ganzzahlen mit Vorzeichen und gibt auch den Rest als Ausgabeparameter zurück.|  
|<xref:System.Math.Exp%2A>|Gibt e (die Basis des natürlichen Logarithmus) in der angegebenen Potenz zurück.|  
|<xref:System.Math.Floor%2A>|Gibt die größte ganze Zahl, die kleiner oder gleich dem angegebenen `Decimal` oder `Double` Anzahl.|  
|<xref:System.Math.IEEERemainder%2A>|Gibt zurück, dass der Rest aus der Division einer Zahl durch eine andere Nummer angegeben.|  
|<xref:System.Math.Log%2A>|Gibt den natürlichen (Logarithmus zur Basis e) einer angegebenen Zahl oder den Logarithmus einer angegebenen Zahl in einer angegebenen Basis zurück.|  
|<xref:System.Math.Log10%2A>|Gibt den Logarithmus einer angegebenen Zahl zur Basis 10 zurück.|  
|<xref:System.Math.Max%2A>|Gibt die größere von zwei Zahlen zurück.|  
|<xref:System.Math.Min%2A>|Gibt die kleinere von zwei Zahlen zurück.|  
|<xref:System.Math.Pow%2A>|Potenziert eine angegebene Zahl mit dem angegebenen Exponenten.|  
|<xref:System.Math.Round%2A>|Gibt eine `Decimal` oder `Double` auf den nächsten ganzzahligen Wert oder eine angegebene Anzahl von Dezimalstellen gerundet.|  
|<xref:System.Math.Sign%2A>|Gibt ein `Integer` Wert, der angibt, der der Vorzeichen einer Zahl.|  
|<xref:System.Math.Sin%2A>|Gibt den Sinus des angegebenen Winkels zurück.|  
|<xref:System.Math.Sinh%2A>|Gibt den Hyperbelsinus des angegebenen Winkels zurück.|  
|<xref:System.Math.Sqrt%2A>|Gibt die Quadratwurzel einer angegebenen Zahl zurück.|  
|<xref:System.Math.Tan%2A>|Gibt den Tangens des angegebenen Winkels zurück.|  
|<xref:System.Math.Tanh%2A>|Gibt den Hyperbeltangens des angegebenen Winkels zurück.|  
|<xref:System.Math.Truncate%2A>|Berechnet den ganzzahligen Teil einer angegebenen `Decimal` oder `Double` Anzahl.|  
  
 Importieren Sie für die Verwendung dieser Funktionen ohne Qualifizierung der <xref:System.Math?displayProperty=nameWithType> Namespace in Ihrem Projekt durch den folgenden Code am Anfang der Quelldatei hinzufügen:  
  
```  
Imports System.Math  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Math.Abs%2A> Methode der <xref:System.Math> Klasse, um den absoluten Wert einer Zahl zu berechnen.  
  
```  
' Returns 50.3.  
Dim MyNumber1 As Double = Math.Abs(50.3)  
' Returns 50.3.  
Dim MyNumber2 As Double = Math.Abs(-50.3)  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Math.Atan%2A> Methode der <xref:System.Math> Klasse, um den Wert von Pi zu berechnen.  
  
```  
Public Function GetPi() As Double  
    ' Calculate the value of pi.  
    Return 4.0 * Math.Atan(1.0)  
End Function  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Math.Cos%2A> Methode der <xref:System.Math> Klasse, um den Kosinuswert eines Winkels zurückzugeben.  
  
```  
Public Function Sec(ByVal angle As Double) As Double  
    ' Calculate the secant of angle, in radians.  
    Return 1.0 / Math.Cos(angle)  
End Function  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Math.Exp%2A> Methode der <xref:System.Math> Klasse mit einem Exponenten Potenziert die Basis e zurückgegeben.  
  
```  
Public Function Sinh(ByVal angle As Double) As Double  
    ' Calculate hyperbolic sine of an angle, in radians.  
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0  
End Function  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Math.Log%2A> Methode der <xref:System.Math> Klasse, um den natürlichen Logarithmus einer Zahl zurückzugeben.  
  
```  
Public Function Asinh(ByVal value As Double) As Double  
    ' Calculate inverse hyperbolic sine, in radians.  
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))  
End Function  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Math.Round%2A> Methode der <xref:System.Math> Klasse, um eine Zahl auf die nächste ganze Zahl gerundet.  
  
```  
' Returns 3.  
Dim MyVar2 As Double = Math.Round(2.8)  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Math.Sign%2A> Methode von der <xref:System.Math> -Klasse die Vorzeichen einer Zahl zu bestimmen.  
  
```  
' Returns 1.  
Dim MySign1 As Integer = Math.Sign(12)  
' Returns -1.  
Dim MySign2 As Integer = Math.Sign(-2.4)  
' Returns 0.  
Dim MySign3 As Integer = Math.Sign(0)  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Math.Sin%2A> Methode der <xref:System.Math> Klasse, um den Sinuswert eines Winkels zurückzugeben.  
  
```  
Public Function Csc(ByVal angle As Double) As Double  
    ' Calculate cosecant of an angle, in radians.  
    Return 1.0 / Math.Sin(angle)  
End Function  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Math.Sqrt%2A> Methode der <xref:System.Math> Klasse, um die Quadratwurzel einer Zahl zu berechnen.  
  
```  
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
 Dieses Beispiel verwendet die <xref:System.Math.Tan%2A> Methode der <xref:System.Math> Klasse, um den Tangens eines Winkels zurückzugeben.  
  
```  
Public Function Ctan(ByVal angle As Double) As Double  
    ' Calculate cotangent of an angle, in radians.  
    Return 1.0 / Math.Tan(angle)  
End Function  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Klasse:** <xref:System.Math>  
  
 **Namespace:** <xref:System>  
  
 **Assembly:** "mscorlib" (in "mscorlib.dll")  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>  
 <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>  
 <xref:System.Double.NaN>  
 [Abgeleitete mathematische Funktionen](../../../visual-basic/language-reference/keywords/derived-math-functions.md)  
 [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
