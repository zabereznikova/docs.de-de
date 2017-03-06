---
title: Typkonvertierung
description: Typkonvertierung
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c9a53222-89cb-47e5-983d-4f0f204e31ba
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 0a774a170b7703b900c2044708b07faeb4e51548
ms.lasthandoff: 03/02/2017

---

# <a name="type-conversion"></a>Typkonvertierung

Jeder Wert verfügt über einen zugeordneten Typ, durch den Attribute, z. B. der dem Wert zugewiesene Speicherplatz, der zulässige Wertebereich und die verfügbar gemachten Member, festgelegt werden. Viele Werte können durch mehrere Typen ausgedrückt werden. Beispielsweise kann der Wert `4` als ganze Zahl oder als Gleitkommawert dargestellt werden. Durch Typkonvertierung wird ein Wert neuen Typs erstellt, der mit dem Wert des alten Typs äquivalent ist. Die Identität (oder der exakte Wert) des ursprünglichen Objekts bleibt dabei nicht immer erhalten.

.NET unterstützt automatisch die folgenden Konvertierungen:

* Die Konvertierung von einer abgeleiteten Klasse in eine Basisklasse. Dies bedeutet beispielsweise, dass eine Instanz einer beliebigen Klasse oder Struktur in eine [Object](xref:System.Object)-Instanz konvertiert werden kann. Diese Konvertierung erfordert keinen Umwandlungsoperator.

* Die Konvertierung von einer Basisklasse in die ursprünglich abgeleitete Klasse. In C# erfordert diese Konvertierung einen Umwandlungsoperator. Visual Basic erfordert für diese Konvertierung den Operator `CType`, wenn für `Option Strict` „On“ gesetzt ist. 

* Die Konvertierung von einem Typ, der eine Schnittstelle in einem Schnittstellenobjekt implementiert, das diese Schnittstelle darstellt. Diese Konvertierung erfordert keinen Umwandlungsoperator.

* Die Konvertierung von einem Schnittstellenobjekt zurück in den ursprünglichen Typ, der diese Schnittstelle implementiert. In C# erfordert diese Konvertierung einen Umwandlungsoperator. Visual Basic erfordert für diese Konvertierung den Operator `CType`, wenn für `Option Strict` „On“ gesetzt ist. 

Zusätzlich zu diesen automatischen Konvertierungen bietet .NET verschiedene Funktionen, die die benutzerdefinierte Typkonvertierung unterstützen. Hierzu gehört Folgendes: 

* Der `Implicit`-Operator, der die verfügbaren Erweiterungskonvertierungen zwischen Typen definiert. Weitere Informationen finden Sie im Abschnitt [Implizite Konvertierung mit dem Implicit-Operator](#implicit-conversion-with-the-implicit-operator).

* Der `Explicit`-Operator, der die verfügbaren einschränkenden Konvertierungen zwischen Typen definiert. Weitere Informationen finden Sie im Abschnitt [Explizite Konvertierung mit dem Explicit-Operator](#explicit-conversion-with-the-explicit-operator).

* Die [IConvertible](xref:System.IConvertible)-Schnittstelle, die Konvertierungen in die einzelnen .NET-Basisdatentypen definiert. Weitere Informationen finden Sie im Abschnitt [Die IConvertible-Schnittstelle](#the-iconvertible-interface).

* Die [Convert](xref:System.Convert)-Klasse, die einen Satz von Methoden bereitstellt, mit denen die Methoden in der `IConvertible`-Schnittstelle implementiert werden. Weitere Informationen finden Sie im Abschnitt [Die Convert-Klasse](#the-convert-class).

* Die [TypeConverter](xref:System.ComponentModel.TypeConverter)-Klasse, die eine Basisklasse ist, die für die Unterstützung der Konvertierung eines angegebenen Typs in einen beliebigen anderen Typ erweitert werden kann. Weitere Informationen finden Sie im Abschnitt [Die TypeConverter-Klasse](#the-typeconverter-class).

## <a name="implicit-conversion-with-the-implicit-operator"></a>Implizite Konvertierung mit dem Implicit-Operator

Erweiterungskonvertierungen umfassen die Erstellung eines neuen Werts aus dem Wert eines vorhandenen Typs, der einen restriktiveren Bereich oder eine eingeschränktere Memberliste als der Zieltyp aufweist. Erweiterungskonvertierungen können nicht zu Datenverlust, möglicherweise jedoch zu einem Genauigkeitsverlust führen. Da keine Daten verloren gehen können, können Compiler die Konvertierung implizit oder transparent behandeln, ohne eine explizite Konvertierungsmethode oder einen Typumwandlungsoperator verwenden zu müssen.

> [!NOTE]
> Obwohl in Code, der eine implizite Konvertierung ausführt, eine Konvertierungsmethode aufgerufen oder ein Typumwandlungsoperator verwendet werden kann, ist ihre Verwendung für Compiler, die implizite Konvertierungen unterstützen, nicht erforderlich.

Beispielsweise unterstützt der [Decimal](xref:System.Decimal)-Typ implizite Konvertierungen aus Werten vom Typ [Byte](xref:System.Byte), [Char](xref:System.Char), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32) und [UInt64](xref:System.UInt64). Im folgenden Beispiel werden einige dieser impliziten Konvertierungen beim Zuweisen von Werten zu einer `Decimal`-Variablen veranschaulicht.

```csharp
byte byteValue = 16;
short shortValue = -1024;
int intValue = -1034000;
long longValue = 1152921504606846976;
ulong ulongValue = UInt64.MaxValue;

decimal decimalValue;

decimalValue = byteValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  byteValue.GetType().Name, decimalValue); 

decimalValue = shortValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  shortValue.GetType().Name, decimalValue); 

decimalValue = intValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  intValue.GetType().Name, decimalValue); 

decimalValue = longValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  longValue.GetType().Name, decimalValue); 

decimalValue = ulongValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  longValue.GetType().Name, decimalValue); 
// The example displays the following output:
//    After assigning a Byte value, the Decimal value is 16.
//    After assigning a Int16 value, the Decimal value is -1024.
//    After assigning a Int32 value, the Decimal value is -1034000.
//    After assigning a Int64 value, the Decimal value is 1152921504606846976.
//    After assigning a Int64 value, the Decimal value is 18446744073709551615.
```

```vb
Dim byteValue As Byte = 16
Dim shortValue As Short = -1024
Dim intValue As Integer = -1034000
Dim longValue As Long = CLng(1024^6)
Dim ulongValue As ULong = ULong.MaxValue

Dim decimalValue As Decimal

decimalValue = byteValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  byteValue.GetType().Name, decimalValue) 

decimalValue = shortValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  shortValue.GetType().Name, decimalValue) 

decimalValue = intValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  intValue.GetType().Name, decimalValue) 

decimalValue = longValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  longValue.GetType().Name, decimalValue) 

decimalValue = ulongValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  longValue.GetType().Name, decimalValue) 
' The example displays the following output:
'    After assigning a Byte value, the Decimal value is 16.
'    After assigning a Int16 value, the Decimal value is -1024.
'    After assigning a Int32 value, the Decimal value is -1034000.
'    After assigning a Int64 value, the Decimal value is 1152921504606846976.
'    After assigning a Int64 value, the Decimal value is 18446744073709551615.
```

Wenn ein bestimmter Sprachcompiler benutzerdefinierte Operatoren unterstützt, können Sie auch implizite Konvertierungen in die eigenen benutzerdefinierten Typen definieren. Im folgenden Beispiel wird die partielle Implementierung des Byte-Datentyps mit Vorzeichen `ByteWithSign` bereitgestellt, der eine Vorzeichen-Wert-Darstellung verwendet. Sie unterstützt die implizite Konvertierung von [Byte](xref:System.Byte)-Werten und [SByte](xref:System.SByte)-Werten in `ByteWithSign`-Werte.

```csharp
public struct ByteWithSign
{
   private SByte signValue; 
   private Byte value;

   public static implicit operator ByteWithSign(SByte value) 
   {
      ByteWithSign newValue;
      newValue.signValue = (SByte) Math.Sign(value);
      newValue.value = (byte) Math.Abs(value);
      return newValue;
   }  

   public static implicit operator ByteWithSign(Byte value)
   {
      ByteWithSign  newValue;
      newValue.signValue = 1;
      newValue.value = value;
      return newValue;
   }

   public override string ToString()
   { 
      return (signValue * value).ToString();
   }
}
```

```vb
Public Structure ByteWithSign
   Private signValue As SByte 
   Private value As Byte

   Public Overloads Shared Widening Operator CType(value As SByte) As ByteWithSign
      Dim newValue As ByteWithSign
      newValue.signValue = CSByte(Math.Sign(value))
      newValue.value = CByte(Math.Abs(value))
      Return newValue
   End Operator  

   Public Overloads Shared Widening Operator CType(value As Byte) As ByteWithSign
      Dim NewValue As ByteWithSign
      newValue.signValue = 1
      newValue.value = value
      Return newValue
   End Operator

   Public Overrides Function ToString() As String 
      Return (signValue * value).ToString()
   End Function
End Structure
```

Clientcode kann dann eine `ByteWithSign`-Variable deklarieren und ihr [Byte](xref:System.Byte)-Werte sowie [SByte](xref:System.SByte)-Werte zuweisen, ohne eine explizite Konvertierung auszuführen oder Typumwandlungsoperatoren zu verwenden, wie im folgenden Beispiel gezeigt.

```csharp
SByte sbyteValue = -120;
ByteWithSign value = sbyteValue;
Console.WriteLine(value);
value = Byte.MaxValue;
Console.WriteLine(value);
// The example displays the following output:
//       -120
//       255
```

```vb
Dim sbyteValue As SByte = -120
Dim value As ByteWithSign = sbyteValue
Console.WriteLine(value.ToString()) 
value = Byte.MaxValue
Console.WriteLine(value.ToString()) 
' The example displays the following output:
'       -120
'       255
```

## <a name="explicit-conversion-with-the-explicit-operator"></a>Explizite Konvertierung mit dem Explicit-Operator

Einschränkende Konvertierungen umfassen die Erstellung eines neuen Werts aus dem Wert eines vorhandenen Typs, der einen größeren Bereich oder eine größere Memberliste als der Zieltyp aufweist. Da eine einschränkende Konvertierung zu Datenverlust an Daten führen kann, erfordern Compiler oft, dass die Konvertierung durch den Aufruf einer Konvertierungsmethode oder eines Typumwandlungsoperators als explizite Konvertierung erfolgt. Das bedeutet, dass die Konvertierung in Entwicklercode explizit behandelt werden muss. 

> [!NOTE]
> Eine Konvertierungsmethode oder ein Typumwandlungsoperator ist vor allem deswegen für einschränkende Konvertierungen erforderlich, um den Entwickler auf die Möglichkeit von Datenverlusten oder einer [OverflowException](xref:System.OverflowException) aufmerksam zu machen, damit sie in Code behandelt werden kann. Bei einigen Compilern wird diese Anforderung jedoch weniger streng gehandhabt. Wenn beispielsweise in Visual Basic `Option Strict` deaktiviert ist (die Standardeinstellung), versucht der Visual Basic-Compiler, einschränkende Konvertierungen implizit auszuführen.

Beispielsweise weisen die Datentypen [UInt32](xref:System.UInt32), [Int64](xref:System.Int64) und [UInt64](xref:System.UInt64) größere Bereiche als der [Int32](xref:System.Int32)-Datentyp auf, wie in der folgenden Tabelle gezeigt.

Typ | Vergleich mit Bereich von Int32
---- | ------------------------------
[Int64](xref:System.Int64) | [Int64.MaxValue](xref:System.Int64.MaxValue) ist größer als [Int32.MaxValue](xref:System.Int32#System_Int32_MaxValue), und [Int64.MinValue](xref:System.Int64.MinValue) ist kleiner als (hat einen größeren negativen Bereich als) [Int32.MinValue](xref:System.Int32#System_Int32_MinValue).
[UInt32](xref:System.UInt32) | [UInt32.MaxValue](xref:System.UInt32.MaxValue) ist größer als [Int32.MaxValue](xref:System.Int32.MaxValue).
[UInt64](xref:System.UInt64) | [UInt64.MaxValue](xref:System.UInt64.MaxValue) ist größer als [Int32.MaxValue](xref:System.Int32.MaxValue).

Um solche einschränkenden Konvertierungen zu behandeln, ermöglicht .NET Typen das Definieren eines `Explicit`-Operators. Einzelne Sprachcompiler können diesen Operator dann mithilfe einer eigenen Syntax implementieren, oder ein Member der [Convert](xref:System.Convert)-Klasse kann aufgerufen werden, um die Konvertierung auszuführen. (Weitere Informationen zur `Convert`-Klasse finden Sie unter [Die Convert-Klasse](#the-convert-class) weiter unten in diesem Thema.) Das folgende Beispiel veranschaulicht die Verwendung von Sprachfunktionen, um die explizite Konvertierung dieser potenziell außerhalb des Gültigkeitsbereichs liegenden ganzzahligen Werte in [Int32](xref:System.Int32)-Werte zu behandeln. 

```csharp
long number1 = int.MaxValue + 20L;
uint number2 = int.MaxValue - 1000;
ulong number3 = int.MaxValue;

int intNumber;

try {
   intNumber = checked((int) number1);
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                     number1.GetType().Name, intNumber); 
}
catch (OverflowException) {
   if (number1 > int.MaxValue)
      Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                        number1, int.MaxValue);
   else
      Console.WriteLine("Conversion failed: {0} is less than {1}.", 
                        number1, int.MinValue);
}

try {
   intNumber = checked((int) number2);
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                     number2.GetType().Name, intNumber); 
}
catch (OverflowException) {
   Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                     number2, int.MaxValue);
}

try {
   intNumber = checked((int) number3);
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                     number3.GetType().Name, intNumber); 
}
catch (OverflowException) {
   Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                     number1, int.MaxValue);
}

// The example displays the following output:
//    Conversion failed: 2147483667 exceeds 2147483647.
//    After assigning a UInt32 value, the Integer value is 2147482647.
//    After assigning a UInt64 value, the Integer value is 2147483647.
```

```vb
Dim number1 As Long = Integer.MaxValue + 20L
Dim number2 As UInteger = Integer.MaxValue - 1000
Dim number3 As ULong = Integer.MaxValue

Dim intNumber As Integer

Try
   intNumber = CInt(number1)
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                       number1.GetType().Name, intNumber)
Catch e As OverflowException
   If number1 > Integer.MaxValue Then
      Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                                        number1, Integer.MaxValue)
   Else
      Console.WriteLine("Conversion failed: {0} is less than {1}.\n", 
                                        number1, Integer.MinValue)
   End If
End Try

Try
   intNumber = CInt(number2)
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                       number2.GetType().Name, intNumber)
Catch e As OverflowException
   Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                                     number2, Integer.MaxValue)
End Try

Try
   intNumber = CInt(number3)
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                       number3.GetType().Name, intNumber)
Catch e As OverflowException
   Console.WriteLine("Conversion failed: {0} exceeds {1}.",
                                     number1, Integer.MaxValue)
End Try
' The example displays the following output:
'    Conversion failed: 2147483667 exceeds 2147483647.
'    After assigning a UInt32 value, the Integer value is 2147482647.
'    After assigning a UInt64 value, the Integer value is 2147483647.
```

Explizite Konvertierungen können in verschiedenen Sprachen zu unterschiedlichen Ergebnissen führen, und diese Ergebnisse können sich von dem Wert unterscheiden, der von der entsprechenden [Convert](xref:System.Convert)-Methode zurückgegeben wird. Beispielsweise wird bei der Konvertierung des [Double](xref:System.Double)-Werts **12.63251** in einen [Int32](xref:System.Int32)-Wert sowohl durch die [Convert.ToInt32(Double)](xref:System.Convert.ToInt32(System.Double))-Methode von .NET als auch durch die `CInt`-Methode von Visual Basic eine Aufrundung des [Double](xref:System.Double)-Werts durchgeführt, und der Wert **13** wird zurückgegeben. Der `(int)`-Operator von C# kürzt den [Double](xref:System.Double)-Wert jedoch und gibt den Wert **12** zurück. Entsprechend unterstützt der `(int)`-Operator von C# keine Konvertierung von booleschen Werten in ganzzahlige Werte, wohingegen die `CInt`-Methode von Visual Basic den Wert `true` in **-1** konvertiert. Dagegen konvertiert die [Convert.ToInt32(Boolean)](xref:System.Convert.ToInt32(System.Boolean))-Methode den Wert `true` in **1**.

Die meisten Compiler ermöglichen die überprüfte und nicht überprüfte Ausführung expliziter Konvertierungen. Bei überprüften Konvertierungen wird eine [OverflowException](xref:System.OverflowException) ausgelöst, wenn der Wert des konvertierten Typs außerhalb des Bereichs des Zieltyps liegt. Wird unter denselben Umständen eine nicht überprüfte Konvertierung durchgeführt, wird möglicherweise keine Ausnahme ausgelöst. Die genauen Auswirkungen lassen sich jedoch nicht vorhersagen. Dies kann zu einem fehlerhaften Wert führen.

> [!NOTE]
> In C# können überprüfte Konvertierungen mithilfe des Schlüsselworts `checked` zusammen mit einem Umwandlungsoperator oder durch Festlegen der Compileroption `/checked+` ausgeführt werden. Umgekehrt können nicht überprüfte Konvertierungen mithilfe des Schlüsselworts `unchecked` zusammen mit dem Umwandlungsoperator oder durch Festlegen der Compileroption `/checked-` ausgeführt werden. In der Standardeinstellung werden explizite Konvertierungen nicht überprüft. In Visual Basic können überprüfte Konvertierungen durch Angabe der `/removeintchecks-`-Compileroption ausgeführt werden. Umgekehrt können nicht überprüfte Konvertierungen durch Angabe der `/removeintchecks+`-Compileroption ausgeführt werden. In der Standardeinstellung werden explizite Konvertierungen überprüft.

Im folgenden C#-Beispiel wird mit dem `checked`-Schlüsselwort und mit dem `unchecked`-Schlüsselwort das unterschiedliche Verhalten bei der Konvertierung eines Werts außerhalb des [Byte](xref:System.Byte)-Bereichs in einen `Byte`-Wert veranschaulicht. Die überprüfte Konvertierung löst eine Ausnahme aus, während die nicht überprüfte Konvertierung [Byte.MaxValue](xref:System.Byte.MaxValue) der Variablen `Byte` zuweist.

```csharp
int largeValue = Int32.MaxValue;
byte newValue;

try {
   newValue = unchecked((byte) largeValue);
   Console.WriteLine("Converted the {0} value {1} to the {2} value {3}.", 
                     largeValue.GetType().Name, largeValue,
                     newValue.GetType().Name, newValue);
}
catch (OverflowException) {
   Console.WriteLine("{0} is outside the range of the Byte data type.", 
                     largeValue);
}

try {
   newValue = checked((byte) largeValue);
   Console.WriteLine("Converted the {0} value {1} to the {2} value {3}.", 
                     largeValue.GetType().Name, largeValue,
                     newValue.GetType().Name, newValue);
}
catch (OverflowException) {
   Console.WriteLine("{0} is outside the range of the Byte data type.", 
                     largeValue);
}
// The example displays the following output:
//    Converted the Int32 value 2147483647 to the Byte value 255.
//    2147483647 is outside the range of the Byte data type.
```

Wenn ein bestimmter Sprachcompiler benutzerdefinierte überladene Operatoren unterstützt, können Sie auch explizite Konvertierungen in die eigenen benutzerdefinierten Typen definieren. Im folgenden Beispiel wird die partielle Implementierung des Byte-Datentyps mit Vorzeichen `ByteWithSign` bereitgestellt, der eine Vorzeichen-Wert-Darstellung verwendet. Sie unterstützt die explizite Konvertierung von [Int32](xref:System.Int32)-Werten und [UInt32](xref:System.UInt32)-Werten in `ByteWithSign`-Werte.

```csharp
public struct ByteWithSign
{
   private SByte signValue; 
   private Byte value;

   private const byte MaxValue = byte.MaxValue;
   private const int MinValue = -1 * byte.MaxValue;

   public static explicit operator ByteWithSign(int value) 
   {
      // Check for overflow.
      if (value > ByteWithSign.MaxValue || value < ByteWithSign.MinValue)
         throw new OverflowException(String.Format("'{0}' is out of range of the ByteWithSign 
                                                   data type.", 
                                                   value));

      ByteWithSign newValue;
      newValue.signValue = (SByte) Math.Sign(value);
      newValue.value = (byte) Math.Abs(value);
      return newValue;
   }  

   public static explicit operator ByteWithSign(uint value)
   {
      if (value > ByteWithSign.MaxValue) 
         throw new OverflowException(String.Format("'{0}' is out of range of the ByteWithSign 
                                                   data type.", 
                                                   value));

      ByteWithSign newValue;
      newValue.signValue = 1;
      newValue.value = (byte) value;
      return newValue;
   }

   public override string ToString()
   { 
      return (signValue * value).ToString();
   }
}
```

```vb
Public Structure ByteWithSign
   Private signValue As SByte 
   Private value As Byte

   Private Const MaxValue As Byte = Byte.MaxValue
   Private Const MinValue As Integer = -1 * Byte.MaxValue

   Public Overloads Shared Narrowing Operator CType(value As Integer) As ByteWithSign
      ' Check for overflow.
      If value > ByteWithSign.MaxValue Or value < ByteWithSign.MinValue Then
         Throw New OverflowException(String.Format("'{0}' is out of range of the ByteWithSign 
                                                   data type.", value))
      End If

      Dim newValue As ByteWithSign

      newValue.signValue = CSByte(Math.Sign(value))
      newValue.value = CByte(Math.Abs(value))
      Return newValue
   End Operator

   Public Overloads Shared Narrowing Operator CType(value As UInteger) As ByteWithSign
      If value > ByteWithSign.MaxValue Then 
         Throw New OverflowException(String.Format("'{0}' is out of range of the ByteWithSign 
                                                   data type.", value))
      End If

      Dim NewValue As ByteWithSign

      newValue.signValue = 1
      newValue.value = CByte(value)
      Return newValue
   End Operator

   Public Overrides Function ToString() As String 
      Return (signValue * value).ToString()
   End Function
End Structure
```

In Clientcode kann dann eine `ByteWithSign`-Variable deklariert werden, der [Int32](xref:System.Int32)-Werte und [UInt32](xref:System.UInt32)-Werte zugewiesen werden, wenn die Zuweisungen einen Typumwandlungsoperator umfassen, wie im folgenden Beispiel gezeigt.

```csharp
ByteWithSign value;

try {
   int intValue = -120;
   value = (ByteWithSign) intValue;
   Console.WriteLine(value);
}
catch (OverflowException e) {
   Console.WriteLine(e.Message);
}

try {
   uint uintValue = 1024;
   value = (ByteWithSign) uintValue;
   Console.WriteLine(value);
}
catch (OverflowException e) {
    Console.WriteLine(e.Message);
}
// The example displays the following output:
//       -120
//       '1024' is out of range of the ByteWithSign data type.
```

```vb
Dim value As ByteWithSign

Try  
   Dim intValue As Integer = -120
   value = CType(intValue, ByteWithSign)
   Console.WriteLine(value) 
Catch e As OverflowException
   Console.WriteLine(e.Message)
End Try

Try
   Dim uintValue As UInteger = 1024
   value = CType(uintValue, ByteWithSign)
   Console.WriteLine(value) 
Catch e As OverflowException
   Console.WriteLine(e.Message)
End Try
' The example displays the following output:
'       -120
'       '1024' is out of range of the ByteWithSign data type.
```

## <a name="the-iconvertible-interface"></a>Die IConvertible-Schnittstelle

Um die Konvertierung eines beliebigen Typs in einen Common Language Runtime-Basistyp zu unterstützen, stellt .NET die [IConvertible](xref:System.IConvertible)-Schnittstelle bereit. Der Implementierungstyp ist erforderlich, um folgende Elemente bereitzustellen:

* Eine Methode, die den [TypeCode](xref:System.TypeCode) des Implementierungstyps zurückgibt.

* Methoden, um den Implementierungstyp in die einzelnen Common Language Runtime-Basistypen ([Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double) usw.) zu konvertieren.

* Eine allgemeine Konvertierungsmethode, um eine Instanz des Implementierungstyps in einen anderen angegebenen Typ zu konvertieren. Konvertierungen, die nicht unterstützt werden, sollten eine [InvalidCastException](xref:System.InvalidCastException) auslösen.

Die einzelnen Common Language Runtime-Basistypen (d.h. [Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [Char](xref:System.Char), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [String](xref:System.String), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32) und [UInt64](xref:System.UInt64)) sowie der [DBNull](xref:System.DBNull)-Typ und der [Enum](xref:System.Enum)-Typ implementieren die [IConvertible](xref:System.IConvertible)-Schnittstelle. Dies sind jedoch explizite Schnittstellenimplementierungen. Die Konvertierungsmethode kann nur über eine [IConvertible](xref:System.IConvertible)-Schnittstellenvariable aufgerufen werden, wie im folgenden Beispiel gezeigt. In diesem Beispiel wird ein [Int32](xref:System.Int32)-Wert in den entsprechenden [Char](xref:System.Char)-Wert konvertiert.

```csharp
int codePoint = 1067;
IConvertible iConv = codePoint;
char ch = iConv.ToChar(null);
Console.WriteLine("Converted {0} to {1}.", codePoint, ch);
```

```vb
Dim codePoint As Integer = 1067
Dim iConv As IConvertible = codePoint
Dim ch As Char = iConv.ToChar(Nothing)
Console.WriteLine("Converted {0} to {1}.", codePoint, ch)
```

Durch die Anforderung, die Konvertierungsmethode für die Schnittstelle statt für den Implementierungstyp aufzurufen, werden explizite Schnittstellenimplementierungen relativ kostenintensiv. Stattdessen wird für die Konvertierung zwischen Common Language Runtime-Basistypen empfohlen, den entsprechenden Member der [Convert](xref:System.Convert)-Klasse aufzurufen. Weitere Informationen finden Sie im nachfolgenden Abschnitt [Die Convert-Klasse](#the-convert-class). 

> [!NOTE]
> Zusätzlich zur [IConvertible](xref:System.IConvertible)-Schnittstelle und der [Convert](xref:System.Convert)-Klasse, die von .NET bereitgestellt werden, stellen einzelne Sprachen eventuell ebenfalls Möglichkeiten zum Durchführen von Konvertierungen bereit. C# verwendet beispielsweise Typumwandlungsoperatoren und Visual Basic im Compiler implementierte Konvertierungsfunktionen wie `CType`, `CInt` und `DirectCast`.

Für die Unterstützung der Konvertierung zwischen den Basistypen in .NET ist hauptsächlich die [IConvertible](xref:System.IConvertible)-Schnittstelle vorgesehen. Die Schnittstelle kann jedoch auch von einem benutzerdefinierten Typ implementiert werden, um die Konvertierung dieses Typs in andere benutzerdefinierte Typen zu unterstützen. Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte Konvertierungen mit der ChangeType-Methode](#custom-conversions-with-the-changetype-method) weiter unten in diesem Thema.

## <a name="the-convert-class"></a>Die Convert-Klasse

Obwohl die [IConvertible](xref:System.IConvertible)-Schnittstellenimplementierung jedes Basistyps aufgerufen werden kann, um eine Typkonvertierung auszuführen, wird als sprachneutrales Verfahren für die Konvertierung zwischen Basistypen der Aufruf der Methoden der [System.Convert](xref:System.Convert)-Klasse empfohlen. Außerdem kann die [Convert.ChangeType(Object, Type, IFormatProvider)](xref:System.Convert.ChangeType(System.Object,System.Type,System.IFormatProvider))-Methode verwendet werden, um einen angegebenen benutzerdefinierten Typ in einen anderen Typ zu konvertieren. 

### <a name="conversions-between-base-types"></a>Konvertierungen zwischen Basistypen

Die [Convert](xref:System.Convert)-Klasse ermöglicht sprachneutrale Konvertierungen zwischen Basistypen, und sie ist für alle Sprachen verfügbar, die für die Common Language Runtime entwickelt wurden. Sie enthält einen vollständigen Satz von Methoden für erweiternde Konvertierungen und für einschränkende Konvertierungen und löst eine [InvalidCastException](xref:System.InvalidCastException) für Konvertierungen aus, die nicht unterstützt werden (z.B. die Konvertierung eines [DateTime](xref:System.DateTime)-Werts in einen ganzzahligen Wert). Einschränkende Konvertierungen werden in einem geprüften Kontext ausgeführt, und bei einem Konvertierungsfehler wird eine [OverflowException](xref:System.OverflowException) ausgelöst.

> [!IMPORTANT]
> Da die [Convert](xref:System.Convert)-Klasse Methoden für die Konvertierung in jeden Basistyp und von jedem Basistyp enthält, ist es nicht erforderlich, die explizite [IConvertible](xref:System.IConvertible)-Schnittstellenimplementierung jedes Basistyps aufzurufen.

Im folgenden Beispiel wird veranschaulicht, wie mit der [System.Convert](xref:System.Convert)-Klasse verschiedene erweiternde und einschränkende Konvertierungen zwischen .NET-Basistypen ausgeführt werden.

```csharp
// Convert an Int32 value to a Decimal (a widening conversion).
int integralValue = 12534;
decimal decimalValue = Convert.ToDecimal(integralValue);
Console.WriteLine("Converted the {0} value {1} to " +  
                                  "the {2} value {3:N2}.", 
                                  integralValue.GetType().Name, 
                                  integralValue, 
                                  decimalValue.GetType().Name, 
                                  decimalValue);
// Convert a Byte value to an Int32 value (a widening conversion).
byte byteValue = Byte.MaxValue;
int integralValue2 = Convert.ToInt32(byteValue);                                  
Console.WriteLine("Converted the {0} value {1} to " +  
                                  "the {2} value {3:G}.", 
                                  byteValue.GetType().Name, 
                                  byteValue, 
                                  integralValue2.GetType().Name, 
                                  integralValue2);

// Convert a Double value to an Int32 value (a narrowing conversion).
double doubleValue = 16.32513e12;
try {
   long longValue = Convert.ToInt64(doubleValue);
   Console.WriteLine("Converted the {0} value {1:E} to " +  
                                     "the {2} value {3:N0}.", 
                                     doubleValue.GetType().Name, 
                                     doubleValue, 
                                     longValue.GetType().Name, 
                                     longValue);
}
catch (OverflowException) {
   Console.WriteLine("Unable to convert the {0:E} value {1}.", 
                                     doubleValue.GetType().Name, doubleValue);
}

// Convert a signed byte to a byte (a narrowing conversion).     
sbyte sbyteValue = -16;
try {
   byte byteValue2 = Convert.ToByte(sbyteValue);
   Console.WriteLine("Converted the {0} value {1} to " +  
                                     "the {2} value {3:G}.", 
                                     sbyteValue.GetType().Name, 
                                     sbyteValue, 
                                     byteValue2.GetType().Name, 
                                     byteValue2);
}
catch (OverflowException) {
   Console.WriteLine("Unable to convert the {0} value {1}.", 
                                     sbyteValue.GetType().Name, sbyteValue);
}                                         
// The example displays the following output:
//       Converted the Int32 value 12534 to the Decimal value 12,534.00.
//       Converted the Byte value 255 to the Int32 value 255.
//       Converted the Double value 1.632513E+013 to the Int64 value 16,325,130,000,000.
//       Unable to convert the SByte value -16.
```

```vb
' Convert an Int32 value to a Decimal (a widening conversion).
Dim integralValue As Integer = 12534
Dim decimalValue As Decimal = Convert.ToDecimal(integralValue)
Console.WriteLine("Converted the {0} value {1} to the {2} value {3:N2}.", 
                  integralValue.GetType().Name,
                  integralValue,
                  decimalValue.GetType().Name,
                  decimalValue)

' Convert a Byte value to an Int32 value (a widening conversion).
Dim byteValue As Byte = Byte.MaxValue
Dim integralValue2 As Integer = Convert.ToInt32(byteValue)                                  
Console.WriteLine("Converted the {0} value {1} to " + 
                                  "the {2} value {3:G}.",
                                  byteValue.GetType().Name,
                                  byteValue,
                                  integralValue2.GetType().Name,
                                  integralValue2)

' Convert a Double value to an Int32 value (a narrowing conversion).
Dim doubleValue As Double = 16.32513e12
Try
   Dim longValue As Long = Convert.ToInt64(doubleValue)
   Console.WriteLine("Converted the {0} value {1:E} to " + 
                                     "the {2} value {3:N0}.",
                                     doubleValue.GetType().Name,
                                     doubleValue,
                                     longValue.GetType().Name,
                                     longValue)
Catch e As OverflowException
   Console.WriteLine("Unable to convert the {0:E} value {1}.",
                                     doubleValue.GetType().Name, doubleValue)
End Try                                                             

' Convert a signed byte to a byte (a narrowing conversion).     
Dim sbyteValue As SByte = -16
Try
   Dim byteValue2 As Byte = Convert.ToByte(sbyteValue)
   Console.WriteLine("Converted the {0} value {1} to " + 
                                     "the {2} value {3:G}.",
                                     sbyteValue.GetType().Name,
                                     sbyteValue,
                                     byteValue2.GetType().Name,
                                     byteValue2)
Catch e As OverflowException
   Console.WriteLine("Unable to convert the {0} value {1}.",
                                     sbyteValue.GetType().Name, sbyteValue)
End Try 
' The example displays the following output:
'       Converted the Int32 value 12534 to the Decimal value 12,534.00.
'       Converted the Byte value 255 to the Int32 value 255.
'       Converted the Double value 1.632513E+013 to the Int64 value 16,325,130,000,000.
'       Unable to convert the SByte value -16.
```

In einigen Fällen, insbesondere bei der Konvertierung in Gleitkommawerte und von Gleitkommawerten, ist eine Konvertierung möglicherweise mit einem Genauigkeitsverlust verbunden, obwohl keine [OverflowException](xref:System.OverflowException) ausgelöst wird. Im folgenden Beispiel wird dieser Genauigkeitsverlust veranschaulicht. Im ersten Fall weist ein [Decimal](xref:System.Decimal)-Wert eine geringere Genauigkeit (weniger signifikante Stellen) auf, wenn er in einen [Double](xref:System.Double)-Wert konvertiert wird. Im zweiten Fall wird der [Double](xref:System.Double)-Wert **42,72** auf **43** gerundet, um die Konvertierung durchführen zu können.

```csharp
double doubleValue; 

// Convert a Double to a Decimal.
decimal decimalValue = 13956810.96702888123451471211m;
doubleValue = Convert.ToDouble(decimalValue);
Console.WriteLine("{0} converted to {1}.", decimalValue, doubleValue);

doubleValue = 42.72;
try {
   int integerValue = Convert.ToInt32(doubleValue);
   Console.WriteLine("{0} converted to {1}.", 
                                     doubleValue, integerValue);
}
catch (OverflowException) {      
   Console.WriteLine("Unable to convert {0} to an integer.", 
                                     doubleValue);
}   
// The example displays the following output:
//       13956810.96702888123451471211 converted to 13956810.9670289.
//       42.72 converted to 43.
```

```vb
Dim doubleValue As Double 

' Convert a Double to a Decimal.
Dim decimalValue As Decimal = 13956810.96702888123451471211d
doubleValue = Convert.ToDouble(decimalValue)
Console.WriteLine("{0} converted to {1}.", decimalValue, doubleValue)

doubleValue = 42.72
Try
   Dim integerValue As Integer = Convert.ToInt32(doubleValue)
   Console.WriteLine("{0} converted to {1}.",
                                     doubleValue, integerValue)
Catch e As OverflowException
   Console.WriteLine("Unable to convert {0} to an integer.",
                                     doubleValue)
End Try   
' The example displays the following output:
'       13956810.96702888123451471211 converted to 13956810.9670289.
'       42.72 converted to 43.
```

Eine Tabelle, in der die von der [Convert](xref:System.Convert)-Klasse unterstützten erweiternden und einschränkenden Konvertierungen aufgeführt sind, finden Sie unter [Typkonvertierungstabellen](conversion-tables.md).

### <a name="custom-conversions-with-the-changetype-method"></a>Benutzerdefinierte Konvertierungen mit der ChangeType-Methode

Zusätzlich zur Unterstützung von Konvertierungen in die einzelnen Basistypen kann die [Convert](xref:System.Convert)-Klasse zum Konvertieren eines benutzerdefinierten Typs in einen oder mehrere vordefinierte Typen verwendet werden. Diese Konvertierung erfolgt durch die [Convert.ChangeType(Object, Type, IFormatProvider)](xref:System.Convert.ChangeType(System.Object,System.Type,System.IFormatProvider))-Methode, die wiederum einen Aufruf der [IConvertible.ToType](xref:System.IConvertible.ToType(System.Type,System.IFormatProvider))-Methode des Wertparameters umschließt. Dies bedeutet, dass das vom Wertparameter dargestellte Objekt eine Implementierung der [IConvertible](xref:System.IConvertible)-Schnittstelle bereitstellen muss.

> [!NOTE]
> Da die Methoden [Convert.ChangeType(Object, Type)](xref:System.Convert.ChangeType(System.Object,System.Type)) und [Convert.ChangeType(Object, Type, IFormatProvider)](xref:System.Convert.ChangeType(System.Object,System.Type,System.IFormatProvider)) mithilfe eines [Type](xref:System.Type)-Objekts den Zieltyp für die Konvertierung des Werts angeben, können sie verwendet werden, um eine dynamische Konvertierung in ein Objekt auszuführen, dessen Typ zur Kompilierzeit nicht bekannt ist. Beachten Sie jedoch, dass die [IConvertible](xref:System.IConvertible)-Implementierung des Werts diese Konvertierung nach wie vor unterstützen muss. 

Im folgenden Beispiel wird eine mögliche Implementierung der [IConvertible](xref:System.IConvertible)-Schnittstelle veranschaulicht, die die Konvertierung eines `TemperatureCelsius`-Objekts in ein `TemperatureFahrenheit`-Objekt und umgekehrt zulässt. Im Beispiel wird die Basisklasse `Temperature` definiert, die die [IConvertible](xref:System.IConvertible)-Schnittstelle implementiert, und die [Object.ToString](xref:System.Object.ToString)-Methode wird überschrieben. Die abgeleitete `TemperatureCelsius`-Klasse und die abgeleitete `TemperatureFahrenheit`-Klasse überschreiben jeweils die `ToType`-Methode und die `ToString`-Methode der Basisklasse. 

```csharp
using System;

public abstract class Temperature : IConvertible
{
   protected decimal temp;

   public Temperature(decimal temperature)
   {
      this.temp = temperature;
   }

   public decimal Value
   { 
      get { return this.temp; } 
      set { this.temp = Value; }        
   }

   public override string ToString()
   {
      return temp.ToString(null as IFormatProvider) + "º";
   }

   // IConvertible implementations.
   public TypeCode GetTypeCode() { 
      return TypeCode.Object;
   }   

   public bool ToBoolean(IFormatProvider provider) {
      throw new InvalidCastException(String.Format("Temperature-to-Boolean conversion is not supported."));
   }

   public byte ToByte(IFormatProvider provider) {
      if (temp < Byte.MinValue || temp > Byte.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the Byte data type.", temp));
      else
         return (byte) temp;
   }

   public char ToChar(IFormatProvider provider) {
      throw new InvalidCastException("Temperature-to-Char conversion is not supported.");
   }

   public DateTime ToDateTime(IFormatProvider provider) {
      throw new InvalidCastException("Temperature-to-DateTime conversion is not supported.");
   }

   public decimal ToDecimal(IFormatProvider provider) {
      return temp;
   }

   public double ToDouble(IFormatProvider provider) {
      return (double) temp;
   }

   public short ToInt16(IFormatProvider provider) {
      if (temp < Int16.MinValue || temp > Int16.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the Int16 data type.", temp));
      else
         return (short) Math.Round(temp);
   }

   public int ToInt32(IFormatProvider provider) {
      if (temp < Int32.MinValue || temp > Int32.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the Int32 data type.", temp));
      else
         return (int) Math.Round(temp);
   }

   public long ToInt64(IFormatProvider provider) {
      if (temp < Int64.MinValue || temp > Int64.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the Int64 data type.", temp));
      else
         return (long) Math.Round(temp);
   }

   public sbyte ToSByte(IFormatProvider provider) {
      if (temp < SByte.MinValue || temp > SByte.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the SByte data type.", temp));
      else
         return (sbyte) temp;
   }

   public float ToSingle(IFormatProvider provider) {
      return (float) temp;
   }

   public virtual string ToString(IFormatProvider provider) {
      return temp.ToString(provider) + "°";
   }

   // If conversionType is implemented by another IConvertible method, call it.
   public virtual object ToType(Type conversionType, IFormatProvider provider) {
      switch (Type.GetTypeCode(conversionType))
      {
         case TypeCode.Boolean:
            return this.ToBoolean(provider);
         case TypeCode.Byte:
            return this.ToByte(provider);
         case TypeCode.Char:
            return this.ToChar(provider);
         case TypeCode.DateTime:
            return this.ToDateTime(provider);
         case TypeCode.Decimal:
            return this.ToDecimal(provider);
         case TypeCode.Double:
            return this.ToDouble(provider);
         case TypeCode.Empty:
            throw new NullReferenceException("The target type is null.");
         case TypeCode.Int16:
            return this.ToInt16(provider);
         case TypeCode.Int32:
            return this.ToInt32(provider);
         case TypeCode.Int64:
            return this.ToInt64(provider);
         case TypeCode.Object:
            // Leave conversion of non-base types to derived classes.
            throw new InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", 
                                           conversionType.Name));
         case TypeCode.SByte:
            return this.ToSByte(provider);
         case TypeCode.Single:
            return this.ToSingle(provider);
         case TypeCode.String:
            IConvertible iconv = this;
            return iconv.ToString(provider);
         case TypeCode.UInt16:
            return this.ToUInt16(provider);
         case TypeCode.UInt32:
            return this.ToUInt32(provider);
         case TypeCode.UInt64:
            return this.ToUInt64(provider);
         default:
            throw new InvalidCastException("Conversion not supported.");
      }
   }

   public ushort ToUInt16(IFormatProvider provider) {
      if (temp < UInt16.MinValue || temp > UInt16.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the UInt16 data type.", temp));
      else
         return (ushort) Math.Round(temp);
   }

   public uint ToUInt32(IFormatProvider provider) {
      if (temp < UInt32.MinValue || temp > UInt32.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the UInt32 data type.", temp));
      else
         return (uint) Math.Round(temp);
   }

   public ulong ToUInt64(IFormatProvider provider) {
      if (temp < UInt64.MinValue || temp > UInt64.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the UInt64 data type.", temp));
      else
         return (ulong) Math.Round(temp);
   }
}

public class TemperatureCelsius : Temperature, IConvertible
{
   public TemperatureCelsius(decimal value) : base(value)
   {
   }

   // Override ToString methods.
   public override string ToString()
   {
      return this.ToString(null);
   }

   public override string ToString(IFormatProvider provider)
   {
      return temp.ToString(provider) + "°C"; 
   }

   // If conversionType is a implemented by another IConvertible method, call it.
   public override object ToType(Type conversionType, IFormatProvider provider) {
      // For non-objects, call base method.
      if (Type.GetTypeCode(conversionType) != TypeCode.Object) {
         return base.ToType(conversionType, provider);
      }   
      else
      {   
         if (conversionType.Equals(typeof(TemperatureCelsius)))
            return this;
         else if (conversionType.Equals(typeof(TemperatureFahrenheit)))
            return new TemperatureFahrenheit((decimal) this.temp * 9 / 5 + 32);
         else
            throw new InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", 
                                           conversionType.Name));
      }
   }
}

public class TemperatureFahrenheit : Temperature, IConvertible 
{
   public TemperatureFahrenheit(decimal value) : base(value)
   {
   }

   // Override ToString methods.
   public override string ToString()
   {
      return this.ToString(null);
   }

   public override string ToString(IFormatProvider provider)
   {
      return temp.ToString(provider) + "°F"; 
   }

   public override object ToType(Type conversionType, IFormatProvider provider)
   { 
      // For non-objects, call base methood.
      if (Type.GetTypeCode(conversionType) != TypeCode.Object) {
         return base.ToType(conversionType, provider);
      }   
      else
      {   
         // Handle conversion between derived classes.
         if (conversionType.Equals(typeof(TemperatureFahrenheit))) 
            return this;
         else if (conversionType.Equals(typeof(TemperatureCelsius)))
            return new TemperatureCelsius((decimal) (this.temp - 32) * 5 / 9);
         // Unspecified object type: throw an InvalidCastException.
         else
            throw new InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", 
                                           conversionType.Name));
      }                                 
   }
}
```

```vb
Public MustInherit Class Temperature
   Implements IConvertible

   Protected temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.temp = temperature
   End Sub

   Public Property Value As Decimal
      Get 
         Return Me.temp
      End Get
      Set
         Me.temp = Value
      End Set   
   End Property

   Public Overrides Function ToString() As String
      Return temp.ToString() & "º"
   End Function

   ' IConvertible implementations.
   Public Function GetTypeCode() As TypeCode Implements IConvertible.GetTypeCode
      Return TypeCode.Object
   End Function   

   Public Function ToBoolean(provider As IFormatProvider) As Boolean Implements IConvertible.ToBoolean
      Throw New InvalidCastException(String.Format("Temperature-to-Boolean conversion is not supported."))
   End Function

   Public Function ToByte(provider As IFormatProvider) As Byte Implements IConvertible.ToByte
      If temp < Byte.MinValue Or temp > Byte.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the Byte data type.", temp))
      Else
         Return CByte(temp)
      End If    
   End Function

   Public Function ToChar(provider As IFormatProvider) As Char Implements IConvertible.ToChar
      Throw New InvalidCastException("Temperature-to-Char conversion is not supported.")
   End Function

   Public Function ToDateTime(provider As IFormatProvider) As DateTime Implements IConvertible.ToDateTime
      Throw New InvalidCastException("Temperature-to-DateTime conversion is not supported.")
   End Function

   Public Function ToDecimal(provider As IFormatProvider) As Decimal Implements IConvertible.ToDecimal
      Return temp
   End Function

   Public Function ToDouble(provider As IFormatProvider) As Double Implements IConvertible.ToDouble
      Return CDbl(temp)
   End Function

   Public Function ToInt16(provider As IFormatProvider) As Int16 Implements IConvertible.ToInt16
      If temp < Int16.MinValue Or temp > Int16.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the Int16 data type.", temp))
      End If
      Return CShort(Math.Round(temp))
   End Function

   Public Function ToInt32(provider As IFormatProvider) As Int32 Implements IConvertible.ToInt32
      If temp < Int32.MinValue Or temp > Int32.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the Int32 data type.", temp))
      End If
      Return CInt(Math.Round(temp))
   End Function

   Public Function ToInt64(provider As IFormatProvider) As Int64 Implements IConvertible.ToInt64
      If temp < Int64.MinValue Or temp > Int64.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the Int64 data type.", temp))
      End If
      Return CLng(Math.Round(temp))
   End Function

   Public Function ToSByte(provider As IFormatProvider) As SByte Implements IConvertible.ToSByte
      If temp < SByte.MinValue Or temp > SByte.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the SByte data type.", temp))
      Else
         Return CSByte(temp)
      End If    
   End Function

   Public Function ToSingle(provider As IFormatProvider) As Single Implements IConvertible.ToSingle
      Return CSng(temp)
   End Function

   Public Overridable Overloads Function ToString(provider As IFormatProvider) As String Implements IConvertible.ToString
      Return temp.ToString(provider) & " °C"
   End Function

   ' If conversionType is a implemented by another IConvertible method, call it.
   Public Overridable Function ToType(conversionType As Type, provider As IFormatProvider) As Object Implements IConvertible.ToType
      Select Case Type.GetTypeCode(conversionType)
         Case TypeCode.Boolean
            Return Me.ToBoolean(provider)
         Case TypeCode.Byte
            Return Me.ToByte(provider)
         Case TypeCode.Char
            Return Me.ToChar(provider)   
         Case TypeCode.DateTime
            Return Me.ToDateTime(provider)
         Case TypeCode.Decimal
            Return Me.ToDecimal(provider)
         Case TypeCode.Double
            Return Me.ToDouble(provider)
         Case TypeCode.Empty
            Throw New NullReferenceException("The target type is null.")
         Case TypeCode.Int16
            Return Me.ToInt16(provider)
         Case TypeCode.Int32
            Return Me.ToInt32(provider)
         Case TypeCode.Int64
            Return Me.ToInt64(provider)
         Case TypeCode.Object
            ' Leave conversion of non-base types to derived classes.
            Throw New InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", _
                                           conversionType.Name))
         Case TypeCode.SByte
            Return Me.ToSByte(provider)
         Case TypeCode.Single
            Return Me.ToSingle(provider)
         Case TypeCode.String
            Return Me.ToString(provider)
         Case TypeCode.UInt16
            Return Me.ToUInt16(provider)
         Case TypeCode.UInt32
            Return Me.ToUInt32(provider)
         Case TypeCode.UInt64
            Return Me.ToUInt64(provider)
         Case Else
            Throw New InvalidCastException("Conversion not supported.")   
      End Select
   End Function

   Public Function ToUInt16(provider As IFormatProvider) As UInt16 Implements IConvertible.ToUInt16
      If temp < UInt16.MinValue Or temp > UInt16.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the UInt16 data type.", temp))
      End If
      Return CUShort(Math.Round(temp))
   End Function

   Public Function ToUInt32(provider As IFormatProvider) As UInt32 Implements IConvertible.ToUInt32
      If temp < UInt32.MinValue Or temp > UInt32.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the UInt32 data type.", temp))
      End If
      Return CUInt(Math.Round(temp))
   End Function

   Public Function ToUInt64(provider As IFormatProvider) As UInt64 Implements IConvertible.ToUInt64
      If temp < UInt64.MinValue Or temp > UInt64.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the UInt64 data type.", temp))
      End If
      Return CULng(Math.Round(temp))
   End Function
End Class

Public Class TemperatureCelsius : Inherits Temperature : Implements IConvertible
   Public Sub New(value As Decimal)
      MyBase.New(value)
   End Sub

   ' Override ToString methods.
   Public Overrides Function ToString() As String
      Return Me.ToString(Nothing)
   End Function

   Public Overrides Function ToString(provider As IFormatProvider ) As String
      Return temp.ToString(provider) + "°C" 
   End Function

  ' If conversionType is a implemented by another IConvertible method, call it.
   Public Overrides Function ToType(conversionType As Type, provider As IFormatProvider) As Object
      ' For non-objects, call base method.
      If Type.GetTypeCode(conversionType) <> TypeCode.Object Then
         Return MyBase.ToType(conversionType, provider)
      Else   
         If conversionType.Equals(GetType(TemperatureCelsius)) Then
            Return Me
         ElseIf conversionType.Equals(GetType(TemperatureFahrenheit))
            Return New TemperatureFahrenheit(CDec(Me.temp * 9 / 5 + 32))
         ' Unspecified object type: throw an InvalidCastException.
         Else
            Throw New InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", _ 
                                           conversionType.Name))
         End If
      End If                                  
   End Function
End Class

Public Class TemperatureFahrenheit : Inherits Temperature : Implements IConvertible
   Public Sub New(value As Decimal)
      MyBase.New(value)
   End Sub

   ' Override ToString methods.
   Public Overrides Function ToString() As String
      Return Me.ToString(Nothing)
   End Function

   Public Overrides Function ToString(provider As IFormatProvider ) As String
      Return temp.ToString(provider) + "°F" 
   End Function

   Public Overrides Function ToType(conversionType As Type, provider As IFormatProvider) As Object
      ' For non-objects, call base methood.
      If Type.GetTypeCode(conversionType) <> TypeCode.Object Then
         Return MyBase.ToType(conversionType, provider)
      Else   
         ' Handle conversion between derived classes.
         If conversionType.Equals(GetType(TemperatureFahrenheit)) Then 
            Return Me
         ElseIf conversionType.Equals(GetType(TemperatureCelsius))
            Return New TemperatureCelsius(CDec((MyBase.temp - 32) * 5 / 9))
         ' Unspecified object type: throw an InvalidCastException.
         Else
            Throw New InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", _
                                           conversionType.Name))
         End If
      End If                                  
   End Function
End Class
```

Im folgenden Beispiel werden mehrere Aufrufe dieser [IConvertible](xref:System.IConvertible)-Implementierungen zum Konvertieren von `TemperatureCelsius`-Objekten in `TemperatureFahrenheit`-Objekte und umgekehrt veranschaulicht.

```csharp
TemperatureCelsius tempC1 = new TemperatureCelsius(0);
TemperatureFahrenheit tempF1 = (TemperatureFahrenheit) Convert.ChangeType(tempC1, typeof(TemperatureFahrenheit), null);
Console.WriteLine("{0} equals {1}.", tempC1, tempF1);
TemperatureCelsius tempC2 = (TemperatureCelsius) Convert.ChangeType(tempC1, typeof(TemperatureCelsius), null);
Console.WriteLine("{0} equals {1}.", tempC1, tempC2);
TemperatureFahrenheit tempF2 = new TemperatureFahrenheit(212);
TemperatureCelsius tempC3 = (TemperatureCelsius) Convert.ChangeType(tempF2, typeof(TemperatureCelsius), null);
Console.WriteLine("{0} equals {1}.", tempF2, tempC3);
TemperatureFahrenheit tempF3 = (TemperatureFahrenheit) Convert.ChangeType(tempF2, typeof(TemperatureFahrenheit), null);
Console.WriteLine("{0} equals {1}.", tempF2, tempF3);
// The example displays the following output:
//       0°C equals 32°F.
//       0°C equals 0°C.
//       212°F equals 100°C.
//       212°F equals 212°F.
```

```vb
Dim tempC1 As New TemperatureCelsius(0)
Dim tempF1 As TemperatureFahrenheit = CType(Convert.ChangeType(tempC1, GetType(TemperatureFahrenheit), Nothing), TemperatureFahrenheit)
Console.WriteLine("{0} equals {1}.", tempC1, tempF1) 
Dim tempC2 As TemperatureCelsius = CType(Convert.ChangeType(tempC1, GetType(TemperatureCelsius), Nothing), TemperatureCelsius)
Console.WriteLine("{0} equals {1}.", tempC1, tempC2) 
Dim tempF2 As New TemperatureFahrenheit(212)
Dim tempC3 As TEmperatureCelsius = CType(Convert.ChangeType(tempF2, GEtType(TemperatureCelsius), Nothing), TemperatureCelsius)
Console.WriteLine("{0} equals {1}.", tempF2, tempC3) 
Dim tempF3 As TemperatureFahrenheit = CType(Convert.ChangeType(tempF2, GetType(TemperatureFahrenheit), Nothing), TemperatureFahrenheit)
Console.WriteLine("{0} equals {1}.", tempF2, tempF3)
' The example displays the following output:
'       0°C equals 32°F.
'       0°C equals 0°C.
'       212°F equals 100°C.
'       212°F equals 212°F.
```

## <a name="the-typeconverter-class"></a>Die TypeConverter-Klasse

.NET ermöglicht Ihnen das Definieren eines Typkonverters für einen benutzerdefinierten Typ, indem Sie die [System.ComponentModel.TypeConverter](xref:System.ComponentModel.TypeConverter)-Klasse erweitern und dem Typ über das [System.ComponentModel.TypeConverterAttribute](xref:System.ComponentModel.TypeConverterAttribute)-Attribut den Typkonverter zuordnen. In der folgenden Tabelle werden die Unterschiede zwischen dieser Vorgehensweise und dem Implementieren der [IConvertible](xref:System.IConvertible)-Schnittstelle für einen benutzerdefinierten Typ hervorgehoben.

> [!NOTE]
> Entwurfszeitunterstützung steht für einen benutzerdefinierten Typ nur zur Verfügung, wenn dieser über einen für ihn definierten Typkonverter verfügt.

Konvertierung mit TypeConverter | Konvertierung mit IConvertible
------------------------------ | -----------------------------
Wird für einen benutzerdefinierten Typ implementiert, indem eine separate Klasse von [TypeConverter](xref:System.ComponentModel.TypeConverter) abgeleitet wird. Die abgeleitete Klasse wird dem benutzerdefinierten Typ durch Anwenden eines [TypeConverterAttribute](xref:System.ComponentModel.TypeConverterAttribute)-Attributs zugeordnet. | Wird von einem benutzerdefinierten Typ implementiert, um Konvertierung durchzuführen. Benutzer des Typs rufen eine [IConvertible](xref:System.IConvertible)-Konvertierungsmethode für den Typ auf.
Kann sowohl zur Entwurfszeit als auch zur Laufzeit verwendet werden. | Kann nur zur Laufzeit verwendet werden.
Verwendet Reflektion und ist daher langsamer als die Konvertierung mit [IConvertible](xref:System.IConvertible). | Verwendet keine Reflektion.
Ermöglicht bidirektionale Typkonvertierungen von benutzerdefinierten Typen in andere Datentypen und umgekehrt. Beispielsweise ermöglicht ein für [TypeConverter](xref:System.ComponentModel.TypeConverter) definierter `MyType`-Wert die Konvertierung von `MyType` in [String](xref:System.String) und von [String](xref:System.String) in `MyType`. | Ermöglicht die Konvertierung von benutzerdefinierten Typen in andere Datentypen, jedoch nicht in umgekehrter Richtung.

Weitere Informationen über das Verwenden von Typkonvertern zum Durchführen von Konvertierungen finden Sie unter [System.ComponentModel.TypeConverter](xref:System.ComponentModel.TypeConverter).

## <a name="see-also"></a>Siehe auch

[System.Convert](xref:System.Convert)

[IConvertible](xref:System.IConvertible)

[Typkonvertierungstabellen](conversion-tables.md)
