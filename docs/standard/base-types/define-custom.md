---
title: 'Gewusst wie: Definieren und Verwenden von benutzerdefinierten Zahlenformatanbietern'
description: Definieren und Verwenden von benutzerdefinierten Zahlenformatanbietern
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 9b184114-6612-4c1a-a2db-2e24e65b0f77
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: bb62bdd03d4af4f764ac3bc8734c67902fffa798

---

# <a name="how-to-define-and-use-custom-numeric-format-providers"></a>Gewusst wie: Definieren und Verwenden von benutzerdefinierten Zahlenformatanbietern

.NET ermöglicht eine umfangreiche Steuerung der Zeichenfolgendarstellung numerischer Werte. Die folgenden Funktionen für die Anpassung des Formats numerischer Werte werden unterstützt:

* Standardmäßige Zahlenformatzeichenfolgen, die einen vordefinierten Satz an Formaten für die Konvertierung von Zahlen in ihre Zeichenfolgendarstellung bereitstellen. Sie können diese mit jeder Zahlenformatierungsmethode verwenden, die über einen Formatparameter verfügt, wie z.B. [Decimal.ToString(String](xref:System.Decimal.ToString(System.String)). Weitere Informationen finden Sie unter [Standardmäßige Zahlenformatzeichenfolgen](standard-numeric.md).

* Benutzerdefinierte Zahlenformatzeichenfolgen, die einen Satz von Symbolen bereitstellen, die kombiniert werden können, um benutzerdefinierte Zahlenformatbezeichner zu definieren. Diese können mit jeder Zahlenformatierungsmethode verwendet werden, die über einen Formatparameter verfügt, wie z.B. [Decimal.ToString(String](xref:System.Decimal.ToString(System.String)). Weitere Informationen finden Sie unter [Benutzerdefinierte Zahlenformatzeichenfolgen](custom-numeric.md).

* Benutzerdefinierte [CultureInfo](xref:System.Globalization.CultureInfo)- oder [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekte, die die beim Anzeigen der Zeichenfolgendarstellungen numerischer Werte verwendeten Symbole und Formatmuster definieren. Sie können diese mit jeder Zahlenformatierungsmethode verwenden, die über einen *provider*-Parameter verfügt, z.B. [ToString](xref:System.Int32.ToString(System.IFormatProvider)). Üblicherweise wird der *provider*-Parameter verwendet, um eine kulturspezifische Formatierung anzugeben.

In einigen Fällen (z.B. wenn eine Anwendung eine formatierte Kontonummer, eine ID oder eine Postleitzahl anzeigen muss) sind diese drei Techniken nicht geeignet. .NET ermöglicht Ihnen auch die Definition eines Formatierungsobjekts, bei dem es sich weder um ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt noch um ein [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt handelt, um zu bestimmen, wie ein numerischer Wert formatiert wird. Dieses Thema stellt eine Schrittanleitung für die Implementierung eines solchen Objekts bereit und bietet ein Beispiel, das Telefonnummern formatiert.

## <a name="to-define-a-custom-format-provider"></a>Definieren eines benutzerdefinierten Formatanbieters

1. Definieren Sie eine Klasse, die die Schnittstellen [IFormatProvider](xref:System.IFormatProvider) und [ICustomFormatter](xref:System.ICustomFormatter) implementiert. 

2. Implementieren Sie die [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Methode. [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) ist eine Rückrufmethode, die von der Formatierungsmethode (z.B. der [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))-Methode) aufgerufen wird, um das Objekt abzurufen, das tatsächlich für die benutzerdefinierte Formatierung zuständig ist. Eine typische Implementierung von [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) führt Folgendes aus:

    a. Bestimmt, ob das als Methodenparameter übergebene [Type](xref:System.Type)-Objekt eine [ICustomFormatter](xref:System.ICustomFormatter)-Schnittstelle darstellt.
    
    b. Wenn der Parameter die [ICustomFormatter](xref:System.ICustomFormatter)-Schnittstelle tatsächlich darstellt, gibt [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) ein Objekt zurück, das die für die benutzerdefinierte Formatierung zuständige [ICustomFormatter](xref:System.ICustomFormatter)-Schnittstelle implementiert. Üblicherweise gibt das benutzerdefinierte Formatierungsobjekt sich selbst zurück. 
    
    c. Wenn der Parameter die [ICustomFormatter](xref:System.ICustomFormatter)-Schnittstelle nicht darstellt, wird `null` von [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) zurückgegeben.
    
3. Implementieren Sie die [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider))-Methode. Diese Methode wird von der [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))-Methode aufgerufen und ist für die Rückgabe der Zeichenfolgendarstellung einer Zahl zuständig. Die Implementierung der Methode umfasst üblicherweise Folgendes:

    a. Stellen Sie optional sicher, dass die Methode dazu in der Lage sein soll, Formatierungsdienste bereitzustellen, indem Sie den *provider*-Parameter untersuchen. Bei Formatierungsobjekten, die sowohl [IFormatProvider](xref:System.IFormatProvider) als auch [ICustomFormatter](xref:System.ICustomFormatter) implementieren, umfasst dies das Testen des *provider*-Parameters auf Gleichheit mit dem aktuellen Formatierungsobjekt.
    
    b. Bestimmen Sie, ob das Formatierungsobjekt benutzerdefinierte Formatbezeichner unterstützen soll. (Beispielsweise könnte ein Formatbezeichner „N“ angeben, dass eine US-amerikanische Telefonnummer im NANP-Format (Nordamerikanischer Nummerierungsplan) ausgegeben werden soll, und ein Bezeichner „I“ könnte eine Ausgabe im Format der ITU-T-Empfehlung E.123 angeben.) Wenn Formatbezeichner verwendet werden, muss die Methode den angegebenen Formatbezeichner verarbeiten. Der Bezeichner wird im Formatparameter an die Methode übergeben. Wen kein Bezeichner vorhanden ist, lautet der Wert des *format*-Parameters [String.Empty](xref:System.String#System_String_Empty).
    
    c. Rufen Sie den numerischen Wert ab, der als *arg*-Parameter an die Methode übergeben wurde. Führen Sie alle Änderungen durch, die notwendig sind, um den Wert in seine Zeichenfolgendarstellung zu konvertieren.
    
    d. Geben Sie die Zeichenfolgendarstellung des *arg*-Parameters zurück.
    
## <a name="to-use-a-custom-numeric-formatting-object"></a>Verwenden eines benutzerdefinierten Zahlenformatierungsobjekts

1. Erstellen Sie eine neue Instanz der benutzerdefinierten Formatierungsklasse.

2. Rufen Sie die [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))-Formatierungsmethode auf, und übergeben Sie das benutzerdefinierte Formatierungsobjekt, den Formatierungsbezeichner (oder [String.Empty](xref:System.String.Empty), falls kein Bezeichner verwendet wird) und den numerischen Wert, der formatiert werden soll. 

## <a name="example"></a>Beispiel

Das folgende Beispiel definiert einen benutzerdefinierten Zahlenformatanbieter namens `TelephoneFormatter`, der eine Zahl, die eine US-amerikanische Telefonnummer darstellt, in das entsprechende NANP- oder E.123-Format konvertiert. Die Methode verarbeitet zwei Formatbezeichner: „N“ (zur Ausgabe des NANP-Formats) und „I“ (zur Ausgabe des internationalen E.123-Formats).

```csharp
using System;
using System.Globalization;

public class TelephoneFormatter : IFormatProvider, ICustomFormatter
{
   public object GetFormat(Type formatType)
   {
      if (formatType == typeof(ICustomFormatter))
         return this;
      else
         return null;
   }               

   public string Format(string format, object arg, IFormatProvider formatProvider)
   {
      // Check whether this is an appropriate callback             
      if (! this.Equals(formatProvider))
         return null; 

      // Set default format specifier             
      if (string.IsNullOrEmpty(format)) 
         format = "N";

      string numericString = arg.ToString();

      if (format == "N")
      {
         if (numericString.Length <= 4)
            return numericString;
         else if (numericString.Length == 7)
            return numericString.Substring(0, 3) + "-" + numericString.Substring(3, 4); 
         else if (numericString.Length == 10)
               return "(" + numericString.Substring(0, 3) + ") " +
                      numericString.Substring(3, 3) + "-" + numericString.Substring(6);   
         else
            throw new FormatException( 
                      string.Format("'{0}' cannot be used to format {1}.", 
                                    format, arg.ToString()));
      }
      else if (format == "I")
      {
         if (numericString.Length < 10)
            throw new FormatException(string.Format("{0} does not have 10 digits.", arg.ToString()));
         else
            numericString = "+1 " + numericString.Substring(0, 3) + " " + numericString.Substring(3, 3) + " " + numericString.Substring(6);
      }
      else
      {
         throw new FormatException(string.Format("The {0} format specifier is invalid.", format));
      } 
      return numericString;  
   }
}

public class TestTelephoneFormatter
{
   public static void Main()
   {
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 0));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 911));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 8490216));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 4257884748));

      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 0));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 911));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 8490216));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 4257884748));

      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:I}", 4257884748));
   }
}
```

```vb
Public Class TelephoneFormatter : Implements IFormatProvider, ICustomFormatter
   Public Function GetFormat(formatType As Type) As Object _
                   Implements IFormatProvider.GetFormat
      If formatType Is GetType(ICustomFormatter) Then
         Return Me
      Else
         Return Nothing
      End If               
   End Function               

   Public Function Format(fmt As String, arg As Object, _
                          formatProvider As IFormatProvider) As String _
                   Implements ICustomFormatter.Format
      ' Check whether this is an appropriate callback             
      If Not Me.Equals(formatProvider) Then Return Nothing 

      ' Set default format specifier             
      If String.IsNullOrEmpty(fmt) Then fmt = "N"

      Dim numericString As String = arg.ToString

      If fmt = "N" Then
         Select Case numericString.Length
            Case <= 4 
               Return numericString
            Case 7
               Return Left(numericString, 3) & "-" & Mid(numericString, 4) 
            Case 10
               Return "(" & Left(numericString, 3) & ") " & _
                      Mid(numericString, 4, 3) & "-" & Mid(numericString, 7)   
            Case Else
               Throw New FormatException( _
                         String.Format("'{0}' cannot be used to format {1}.", _
                                       fmt, arg.ToString()))
         End Select
      ElseIf fmt = "I" Then
         If numericString.Length < 10 Then
            Throw New FormatException(String.Format("{0} does not have 10 digits.", arg.ToString()))
         Else
            numericString = "+1 " & Left(numericString, 3) & " " & Mid(numericString, 4, 3) & " " & Mid(numericString, 7)
         End If      
      Else
         Throw New FormatException(String.Format("The {0} format specifier is invalid.", fmt))
      End If 
      Return numericString  
   End Function
End Class

Public Module TestTelephoneFormatter
   Public Sub Main
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 0))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 911))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 8490216))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 4257884748))

      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 0))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 911))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 8490216))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 4257884748))

      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:I}", 4257884748))
   End Sub
End Module
```

Der benutzerdefinierte Zahlenformatanbieter kann nur mit der [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))-Methode verwendet werden.. Alle anderen Überladungen der Zahlenformatierungsmethoden (z.B. `ToString`), die einen Parameter des Typs [IFormatProvider](xref:System.IFormatProvider) aufweisen, übergeben der [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type))-Implementierung alle ein [Type](xref:System.Type)-Objekt, das den [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Typ darstellt. Im Gegenzug erwarten sie, dass die Methode ein [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt zurückgibt. Wenn dies nicht der Fall ist, wird der benutzerdefinierte Zahlenformatanbieter ignoriert und stattdessen das [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt für die aktuelle Kultur verwendet. Im Beispiel verarbeitet die `TelephoneFormatter.GetFormat`-Methode die Möglichkeit, dass sie fälschlicherweise an eine Zahlenformatierungsmethode übergeben wurde, indem sie den Methodenparameter untersucht und *null* zurückgibt, wenn dieser einen anderen Typ als [ICustomFormatter](xref:System.ICustomFormatter) darstellt.

Wenn ein benutzerdefinierter Zahlenformatanbieter einen Satz von Formatbezeichnern unterstützt, stellen Sie sicher, dass Sie ein Standardverhalten einrichten, falls in dem Formatelement, das im [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))-Methodenaufruf verwendet wird, kein Formatbezeichner bereitgestellt wird. Im Beispiel ist „N“ der Standardformatbezeichner. Dadurch kann eine Zahl in eine formatierte Telefonnummer konvertiert werden, indem ein expliziter Formatbezeichner bereitgestellt wird. Das folgende Beispiel veranschaulicht einen solchen Methodenaufruf.

```csharp
Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 4257884748));
```

```vb
Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 4257884748))
```

Es ermöglicht die Konvertierung aber auch, falls kein Formatbezeichner vorhanden ist. Das folgende Beispiel veranschaulicht einen solchen Methodenaufruf.

```csharp
Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 4257884748));
```

```vb
Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 4257884748))
```

Wenn kein Standardformatbezeichner definiert ist, muss Ihre Implementierung der [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider))-Methode einen Code wie den folgenden beinhalten, damit .NET eine Formatierung bereitstellen kann, die von Ihrem Code nicht unterstützt wird.

```csharp
if (arg is IFormattable) 
   s = ((IFormattable)arg).ToString(format, formatProvider);
else if (arg != null)    
   s = arg.ToString();
```

```vb
If TypeOf(arg) Is IFormattable Then 
   s = DirectCast(arg, IFormattable).ToString(fmt, formatProvider)
ElseIf arg IsNot Nothing Then    
   s = arg.ToString()
End If
```

In diesem Beispiel soll die Methode, die [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) implementiert, als Rückrufmethode für die [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))-Methode dienen. Daher untersucht diese Methode den *formatProvider*-Parameter, um zu ermitteln, ob dieser einen Verweis auf das aktuelle `TelephoneFormatter`-Objekt enthält. Die Methode kann jedoch auch direkt aus dem Code aufgerufen werden. In diesem Fall können Sie den *formatProvider*-Parameter verwenden, um ein [CultureInfo](xref:System.Globalization.CultureInfo)- oder ein [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt bereitzustellen, das kulturspezifische Formatierungsinformationen bereitstellt.

## <a name="see-also"></a>Siehe auch

[Durchführen von Formatierungsvorgängen](performing-formatting-operations.md)



<!--HONumber=Nov16_HO3-->


