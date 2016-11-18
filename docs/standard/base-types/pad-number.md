---
title: "Gewusst wie: Auffüllen einer Zahl mit führenden Nullen"
description: "Auffüllen einer Zahl mit führenden Nullen"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a517c066-b11e-4815-826b-9262611eac40
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 0a136d88dfbc83d40ff8a204f275537c24f9748b

---

# <a name="how-to-pad-a-number-with-leading-zeros"></a>Gewusst wie: Auffüllen einer Zahl mit führenden Nullen

Führende Nullen können Sie mithilfe der [numerischen Standardformatzeichenfolge](standard-numeric.md) „D“ zusammen mit einem Genauigkeitsbezeichner zu einer Ganzzahl hinzufügen. Ganz- und Gleitkommazahlen können Sie führende Nullen mithilfe einer [benutzerdefinierten numerischen Formatzeichenfolge](custom-numeric.md) hinzufügen. In diesem Thema lernen Sie beide Methoden zum Auffüllen einer Zahl mit führenden Nullen kennen.

## <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a>Ganzzahl bis zu einer bestimmten Länge mit führenden Nullen auffüllen

1. Bestimmen Sie die Mindestanzahl an Ziffern, die der Ganzzahlwert anzeigen soll. Schließen Sie alle führenden Ziffern in diese Zahl ein.

2. Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll.

    * Um die ganze Zahl als Dezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`-Methode auf, und übergeben Sie die Zeichenfolge „D*n*“ als Wert des format-Parameters, wobei *n* die Mindestlänge der Zeichenfolge darstellt.
    
    * Um die ganze Zahl als Hexadezimalwert anzuzeigen, rufen Sie ihre `ToString(String)`-Methode auf, und übergeben Sie die Zeichenfolge „X*n*“ als Wert des format-Parameters, wobei *n* die Mindestlänge der Zeichenfolge darstellt.
    
  Sie können die Formatzeichenfolge auch in einer Methode wie z.B. [Console.WriteLine](xref:System.Console.WriteLine) oder [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) verwenden, die die [kombinierte Formatierung](composite-format.md) unterstützt.  
  
Im folgenden Beispiel sind mehrere Ganzzahlwerte so mit führenden Nullen formatiert, dass die Gesamtlänge der formatierten Zahl mindestens acht Zeichen beträgt.

```csharp
byte byteValue = 254;
short shortValue = 10342;
int intValue = 1023983;
long lngValue = 6985321;               
ulong ulngValue = UInt64.MaxValue;

// Display integer values by calling the ToString method.
Console.WriteLine("{0,22} {1,22}", byteValue.ToString("D8"), byteValue.ToString("X8"));
Console.WriteLine("{0,22} {1,22}", shortValue.ToString("D8"), shortValue.ToString("X8"));
Console.WriteLine("{0,22} {1,22}", intValue.ToString("D8"), intValue.ToString("X8"));
Console.WriteLine("{0,22} {1,22}", lngValue.ToString("D8"), lngValue.ToString("X8"));
Console.WriteLine("{0,22} {1,22}", ulngValue.ToString("D8"), ulngValue.ToString("X8"));
Console.WriteLine();

// Display the same integer values by using composite formatting.
Console.WriteLine("{0,22:D8} {0,22:X8}", byteValue);
Console.WriteLine("{0,22:D8} {0,22:X8}", shortValue);
Console.WriteLine("{0,22:D8} {0,22:X8}", intValue);
Console.WriteLine("{0,22:D8} {0,22:X8}", lngValue);
Console.WriteLine("{0,22:D8} {0,22:X8}", ulngValue);
// The example displays the following output:
//                     00000254               000000FE
//                     00010342               00002866
//                     01023983               000F9FEF
//                     06985321               006A9669
//         18446744073709551615       FFFFFFFFFFFFFFFF
//       
//                     00000254               000000FE
//                     00010342               00002866
//                     01023983               000F9FEF
//                     06985321               006A9669
//         18446744073709551615       FFFFFFFFFFFFFFFF
//         18446744073709551615       FFFFFFFFFFFFFFFF
```

```vb
Dim byteValue As Byte = 254
Dim shortValue As Short = 10342
Dim intValue As Integer = 1023983
Dim lngValue As Long = 6985321               
Dim ulngValue As ULong = UInt64.MaxValue

' Display integer values by calling the ToString method.
Console.WriteLine("{0,22} {1,22}", byteValue.ToString("D8"), byteValue.ToString("X8"))
Console.WriteLine("{0,22} {1,22}", shortValue.ToString("D8"), shortValue.ToString("X8"))
Console.WriteLine("{0,22} {1,22}", intValue.ToString("D8"), intValue.ToString("X8"))
Console.WriteLine("{0,22} {1,22}", lngValue.ToString("D8"), lngValue.ToString("X8"))
Console.WriteLine("{0,22} {1,22}", ulngValue.ToString("D8"), ulngValue.ToString("X8"))
Console.WriteLine()

' Display the same integer values by using composite formatting.
Console.WriteLine("{0,22:D8} {0,22:X8}", byteValue)
Console.WriteLine("{0,22:D8} {0,22:X8}", shortValue)
Console.WriteLine("{0,22:D8} {0,22:X8}", intValue)
Console.WriteLine("{0,22:D8} {0,22:X8}", lngValue)
Console.WriteLine("{0,22:D8} {0,22:X8}", ulngValue)
' The example displays the following output:
'                     00000254               000000FE
'                     00010342               00002866
'                     01023983               000F9FEF
'                     06985321               006A9669
'         18446744073709551615       FFFFFFFFFFFFFFFF
'       
'                     00000254               000000FE
'                     00010342               00002866
'                     01023983               000F9FEF
'                     06985321               006A9669
'         18446744073709551615       FFFFFFFFFFFFFFFF
```

## <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a>Ganzzahl mit einer bestimmten Anzahl führender Nullen auffüllen

1. Bestimmen Sie, wie viele führende Nullen der Ganzzahlwert anzeigen soll.

2. Bestimmen Sie, ob die Ganzzahl als Dezimalwert oder als Hexadezimalwert angezeigt werden soll. Zum Formatieren der Ganzzahl als Dezimalwert benötigen Sie den Standardformatbezeichner "D", für einen Hexadezimalwert benötigen Sie den Standardformatbezeichner "X".

3. Bestimmen Sie die Länge der noch nicht mit Nullen aufgefüllten numerischen Zeichenfolge, indem Sie die `ToString("D").Length`- oder die `ToString("X").Length`-Methode des Ganzzahlwerts aufrufen. 

4. Fügen Sie die Anzahl der führenden Nullen, die in die formatierte Zeichenfolge eingefügt werden sollen, zur Länge der nicht aufgefüllten numerischen Zeichenfolge hinzu. Dies ergibt die Gesamtlänge der mit Nullen aufgefüllten Zeichenfolge.

5. Rufen Sie die `ToString(String)`-Methode des Ganzzahlwerts auf, und übergeben Sie die Zeichenfolge „D*n*“ für Dezimalzeichenfolgen und „X*n*“ für Hexadezimalzeichenfolgen, wobei *n* die Gesamtlänge der aufgefüllten Zeichenfolge darstellt. Sie können die Formatzeichenfolge „D*n*“ oder „X*n*“ auch in Methoden verwenden, die die kombinierte Formatierung unterstützen.

Im folgenden Beispiel wird ein Ganzzahlwert mit fünf führenden Nullen aufgefüllt.

```csharp
int value = 160934;
int decimalLength = value.ToString("D").Length + 5;
int hexLength = value.ToString("X").Length + 5;
Console.WriteLine(value.ToString("D" + decimalLength.ToString()));
Console.WriteLine(value.ToString("X" + hexLength.ToString()));
// The example displays the following output:
//       00000160934
//       00000274A6
```

```vb
Dim value As Integer = 160934
Dim decimalLength As Integer = value.ToString("D").Length + 5
Dim hexLength As Integer = value.ToString("X").Length + 5
Console.WriteLine(value.ToString("D" + decimalLength.ToString()))
Console.WriteLine(value.ToString("X" + hexLength.ToString()))
' The example displays the following output:
'       00000160934
'       00000274A6 
```

## <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a>Numerischen Wert bis zu einer bestimmten Länge mit führenden Nullen auffüllen

1. Bestimmen Sie, über wie viele Ziffern links des Dezimaltrennzeichens die Zeichenfolgendarstellung der Zahl verfügen soll. Schließen Sie alle führenden Nullen in diese Gesamtzahl der Ziffern ein.

2. Definieren Sie eine benutzerdefinierte numerische Formatzeichenfolge, in der die Mindestanzahl an Nullen mit dem Null-Platzhalter ("0") dargestellt wird.

3. Rufen Sie die `ToString(String)`-Methode der Zahl auf und übergeben sie die benutzerdefinierte Formatzeichenfolge. Sie können die benutzerdefinierte Formatzeichenfolge auch mit Methoden verwenden, die kombinierte Formatierung unterstützen.

Im folgenden Beispiel sind mehrere numerische Werte so mit führenden Nullen formatiert, dass die Gesamtlänge der formatierten Zahl mindestens acht Ziffern links des Dezimaltrennzeichens beträgt.

```csharp
string fmt = "00000000.##";
int intValue = 1053240;
decimal decValue = 103932.52m;
float sngValue = 1549230.10873992f;
double dblValue = 9034521202.93217412;

// Display the numbers using the ToString method.
Console.WriteLine(intValue.ToString(fmt));
Console.WriteLine(decValue.ToString(fmt));           
Console.WriteLine(sngValue.ToString(fmt));
Console.WriteLine(dblValue.ToString(fmt));           
Console.WriteLine();

// Display the numbers using composite formatting.
string formatString = " {0,15:" + fmt + "}";
Console.WriteLine(formatString, intValue);      
Console.WriteLine(formatString, decValue);      
Console.WriteLine(formatString, sngValue);      
Console.WriteLine(formatString, dblValue);      
// The example displays the following output:
//       01053240
//       00103932.52
//       01549230
//       9034521202.93
//       
//               01053240
//            00103932.52
//               01549230
//          9034521202.93  
```

```vb
Dim fmt As String = "00000000.##"
Dim intValue As Integer = 1053240
Dim decValue As Decimal = 103932.52d
Dim sngValue As Single = 1549230.10873992
Dim dblValue As Double = 9034521202.93217412

' Display the numbers using the ToString method.
Console.WriteLine(intValue.ToString(fmt))
Console.WriteLine(decValue.ToString(fmt))            
Console.WriteLine(sngValue.ToString(fmt))
Console.WriteLine(dblValue.ToString(fmt))            
Console.WriteLine()

' Display the numbers using composite formatting.
Dim formatString As String = " {0,15:" + fmt + "}"
Console.WriteLine(formatString, intValue)      
Console.WriteLine(formatString, decValue)      
Console.WriteLine(formatString, sngValue)      
Console.WriteLine(formatString, dblValue)      
' The example displays the following output:
'       01053240
'       00103932.52
'       01549230
'       9034521202.93
'       
'               01053240
'            00103932.52
'               01549230
'          9034521202.93
```

## <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a>Numerischen Wert mit einer bestimmten Anzahl führender Nullen auffüllen

1. Bestimmen Sie, über wie viele führende Nullen der numerische Wert verfügen soll.

2. Bestimmen Sie die Anzahl der Ziffern links des Dezimaltrennzeichens in der nicht aufgefüllten numerischen Zeichenfolge. Gehen Sie dazu wie folgt vor:

    a. Bestimmen Sie, ob die Zeichenfolgendarstellung der Zahl ein Symbol für das Dezimaltrennzeichen beinhaltet.
    
    b. Wenn sie ein Dezimaltrennzeichen enthält, bestimmen Sie die Anzahl der Zeichen links des Dezimaltrennzeichens.       
    
    - oder - 
       
    Wenn sie kein Dezimaltrennzeichen enthält, bestimmen Sie die Länge der Zeichenfolge. 
       
3. Erstellen Sie eine benutzerdefinierte Formatzeichenfolge, in der die gewünschte Anzahl führender Nullen in der Zeichenfolge mit dem Null-Platzhalter ("0") und die Ziffern in der Standardzeichenfolge mit dem Null-Platzhalter ("0") oder dem Ziffernplatzhalter ("#") angegeben werden. 

4. Übergeben Sie die benutzerdefinierte Formatzeichenfolge als Parameter an die ToString(String)-Methode der Zahl oder an eine Methode, die kombinierte Formatierung unterstützt.

Im folgenden Beispiel werden zwei [Double](xref:System.Double)-Werte mit fünf vorangestellten Nullen aufgefüllt.

```csharp
double[] dblValues = { 9034521202.93217412, 9034521202 };
foreach (double dblValue in dblValues)
{
   string decSeparator = System.Globalization.NumberFormatInfo.CurrentInfo.NumberDecimalSeparator;
   string fmt, formatString;

   if (dblValue.ToString().Contains(decSeparator))
   {
      int digits = dblValue.ToString().IndexOf(decSeparator);
      fmt = new String('0', 5) + new String('#', digits) + ".##";
   }
   else
   {
      fmt = new String('0', dblValue.ToString().Length);   
   }
   formatString = "{0,20:" + fmt + "}";

   Console.WriteLine(dblValue.ToString(fmt));
   Console.WriteLine(formatString, dblValue);
}
// The example displays the following output:
//       000009034521202.93
//         000009034521202.93
//       9034521202
//                 9034521202 
```

```vb
Dim dblValues() As Double = { 9034521202.93217412, 9034521202 }
For Each dblValue As Double In dblValues
   Dim decSeparator As String = System.Globalization.NumberFormatInfo.CurrentInfo.NumberDecimalSeparator
   Dim fmt, formatString As String

   If dblValue.ToString.Contains(decSeparator) Then
      Dim digits As Integer = dblValue.ToString().IndexOf(decSeparator)
      fmt = New String("0"c, 5) + New String("#"c, digits) + ".##"
   Else
      fmt = New String("0"c, dblValue.ToString.Length)   
   End If
   formatString = "{0,20:" + fmt + "}"

   Console.WriteLine(dblValue.ToString(fmt))
   Console.WriteLine(formatString, dblValue)
Next
' The example displays the following output:
'       000009034521202.93
'         000009034521202.93
'       9034521202
'                 9034521202
```

## <a name="see-also"></a>Siehe auch

[Standard-Zahlenformatzeichenfolgen](standard-numeric.md)

[Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric.md)

[Kombinierte Formatierung](composite-format.md)




<!--HONumber=Nov16_HO3-->


