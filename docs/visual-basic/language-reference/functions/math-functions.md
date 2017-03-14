---
title: "Mathematische Funktionen (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Mathematische Funktionen, Visual Basic"
  - "Arithmetische Operationen, Mathematische Funktionen"
  - "Mathematische Routinen"
  - "Atn-Funktion"
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# Mathematische Funktionen (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Die Methoden der \- Klasse stellen die <xref:System.Math?displayProperty=fullName> trigonometrische, logarithmischen und anderen allgemeinen mathematischen Funktionen.  
  
## Hinweise  
 In der folgenden Tabelle werden Methoden der Klasse <xref:System.Math?displayProperty=fullName> auf.  Sie können diese in einem Visual Basic\-Programm verwenden.  
  
|.NET Framework\-Methode|Beschreibung|  
|-----------------------------|------------------|  
|<xref:System.Math.Abs%2A>|Gibt den absoluten Wert einer Zahl zurück.|  
|<xref:System.Math.Acos%2A>|Gibt einen Winkel zurück, dessen Kosinus die angegebene Zahl ist.|  
|<xref:System.Math.Asin%2A>|Gibt einen Winkel zurück, dessen Sinus die angegebene Zahl ist.|  
|<xref:System.Math.Atan%2A>|Gibt einen Winkel zurück, dessen Tangens die angegebene Zahl ist.|  
|<xref:System.Math.Atan2%2A>|Gibt einen Winkel zurück, dessen Tangens der Quotient zweier angegebener Zahlen ist.|  
|<xref:System.Math.BigMul%2A>|Gibt das vollständige Produkt von zwei 32\-Bit\-Zahlen zurück.|  
|<xref:System.Math.Ceiling%2A>|Gibt den kleinsten ganzzahligen Wert zurück, der größer oder gleich angegebene `Decimal` oder `Double` ist.|  
|<xref:System.Math.Cos%2A>|Gibt den Kosinus des angegebenen Winkels zurück.|  
|<xref:System.Math.Cosh%2A>|Gibt den Hyperbelkosinus des angegebenen Winkels zurück.|  
|<xref:System.Math.DivRem%2A>|Gibt den Quotienten von zwei 32\-Bit\- oder 64\-Bit\-Version gesignierten Zahlen zurück und gibt auch den Rest in einem Ausgabeparameter zurück.|  
|<xref:System.Math.Exp%2A>|Gibt e \(die Basis des natürlichen Logarithmus ausgelöst\) der angegebenen Potenz zurück.|  
|<xref:System.Math.Floor%2A>|Gibt die größte ganze Zahl zurück, die kleiner oder gleich angegebene `Decimal` oder die `Double` Zahl ist.|  
|<xref:System.Math.IEEERemainder%2A>|Gibt den Rest zurück, der von der Division einer angegebenen Anzahl von einer anderen angegebene Anzahl entsteht.|  
|<xref:System.Math.Log%2A>|Gibt den natürlichen Logarithmus \(grundlegenden e\) einer bestimmten Anzahl oder den Logarithmus einer angegebenen Anzahl in einer angegebenen Basis zurück.|  
|<xref:System.Math.Log10%2A>|Gibt den Logarithmus einer angegebenen Zahl zur Basis 10 zurück.|  
|<xref:System.Math.Max%2A>|Gibt das größere von zwei Zahlen zurück.|  
|<xref:System.Math.Min%2A>|Gibt die kleinere von zwei Zahlen zurück.|  
|<xref:System.Math.Pow%2A>|Potenziert eine angegebene Zahl mit dem angegebenen Exponenten.|  
|<xref:System.Math.Round%2A>|Gibt einen `Decimal` oder `Double`\-Wert zurück, der zum nächsten ganzzahligen Wert oder eine angegebene Anzahl von Dezimalstellen gerundet.|  
|<xref:System.Math.Sign%2A>|Gibt einen Wert vom Typ `Integer` zurück, der das Vorzeichen einer Zahl angibt.|  
|<xref:System.Math.Sin%2A>|Gibt den Sinus des angegebenen Winkels zurück.|  
|<xref:System.Math.Sinh%2A>|Gibt den Hyperbelsinus des angegebenen Winkels zurück.|  
|<xref:System.Math.Sqrt%2A>|Gibt die Quadratwurzel einer angegebenen Zahl zurück.|  
|<xref:System.Math.Tan%2A>|Gibt den Tangens des angegebenen Winkels zurück.|  
|<xref:System.Math.Tanh%2A>|Gibt den Hyperbeltangens des angegebenen Winkels zurück.|  
|<xref:System.Math.Truncate%2A>|Berechnet den wesentlichen Bestandteil des angegebenen `Decimal` oder von `Double` Zahl.|  
  
 Um diese Funktionen ohne Qualifizierung zu verwenden, importieren Sie den <xref:System.Math?displayProperty=fullName>\-Namespace in das Projekt mit dem folgenden Code zum Anfang der Quelldatei hinzu:  
  
```  
Imports System.Math  
```  
  
## Beispiel  
 In diesem Beispiel wird der absolute Wert einer Zahl mit der <xref:System.Math.Abs%2A>\-Methode der <xref:System.Math>\-Klasse berechnet.  
  
```  
' Returns 50.3.  
Dim MyNumber1 As Double = Math.Abs(50.3)  
' Returns 50.3.  
Dim MyNumber2 As Double = Math.Abs(-50.3)  
```  
  
## Beispiel  
 In diesem Beispiel wird der Wert von Pi mit der <xref:System.Math.Atan%2A>\-Methode der <xref:System.Math>\-Klasse berechnet.  
  
```  
Public Function GetPi() As Double  
    ' Calculate the value of pi.  
    Return 4.0 * Math.Atan(1.0)  
End Function  
```  
  
## Beispiel  
 In diesem Beispiel wird der Kosinus eines Winkels mit der <xref:System.Math.Cos%2A>\-Methode der <xref:System.Math>\-Klasse zurückgegeben.  
  
```  
Public Function Sec(ByVal angle As Double) As Double  
    ' Calculate the secant of angle, in radians.  
    Return 1.0 / Math.Cos(angle)  
End Function  
```  
  
## Beispiel  
 In diesem Beispiel wird eine Potenz zur Basis e mit der <xref:System.Math.Exp%2A>\-Methode der <xref:System.Math>\-Klasse zurückgegeben.  
  
```  
Public Function Sinh(ByVal angle As Double) As Double  
    ' Calculate hyperbolic sine of an angle, in radians.  
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0  
End Function  
```  
  
## Beispiel  
 In diesem Beispiel wird der natürliche Logarithmus einer Zahl mit der <xref:System.Math.Log%2A>\-Methode der <xref:System.Math>\-Klasse zurückgegeben.  
  
```  
Public Function Asinh(ByVal value As Double) As Double  
    ' Calculate inverse hyperbolic sine, in radians.  
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))  
End Function  
```  
  
## Beispiel  
 In diesem Beispiel wird mit der <xref:System.Math.Round%2A>\-Methode der <xref:System.Math>\-Klasse eine Zahl auf die nächste ganze Zahl gerundet.  
  
```  
' Returns 3.  
Dim MyVar2 As Double = Math.Round(2.8)  
```  
  
## Beispiel  
 In diesem Beispiel wird das Vorzeichen einer Zahl mit der <xref:System.Math.Sign%2A>\-Methode der <xref:System.Math>\-Klasse ermittelt.  
  
```  
' Returns 1.  
Dim MySign1 As Integer = Math.Sign(12)  
' Returns -1.  
Dim MySign2 As Integer = Math.Sign(-2.4)  
' Returns 0.  
Dim MySign3 As Integer = Math.Sign(0)  
```  
  
## Beispiel  
 In diesem Beispiel wird der Sinus eines Winkels mit der <xref:System.Math.Sin%2A>\-Methode der <xref:System.Math>\-Klasse zurückgegeben.  
  
```  
Public Function Csc(ByVal angle As Double) As Double  
    ' Calculate cosecant of an angle, in radians.  
    Return 1.0 / Math.Sin(angle)  
End Function  
```  
  
## Beispiel  
 In diesem Beispiel wird die Quadratwurzel einer Zahl mit der <xref:System.Math.Sqrt%2A>\-Methode der <xref:System.Math>\-Klasse berechnet.  
  
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
  
## Beispiel  
 In diesem Beispiel wird der Tangens eines Winkels mit der <xref:System.Math.Tan%2A>\-Methode der <xref:System.Math>\-Klasse zurückgegeben.  
  
```  
Public Function Ctan(ByVal angle As Double) As Double  
    ' Calculate cotangent of an angle, in radians.  
    Return 1.0 / Math.Tan(angle)  
End Function  
```  
  
## Anforderungen  
 **Klasse:** <xref:System.Math>  
  
 **Namespace:** <xref:System>  
  
 **Assembly:** mscorlib \(in Mscorlib.dll\)  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>   
 <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>   
 <xref:System.Double.NaN>   
 [Derived Math Functions](../../../visual-basic/language-reference/keywords/derived-math-functions.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)