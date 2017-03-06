---
title: Verwenden der StringBuilder-Klasse
description: Verwenden der StringBuilder-Klasse
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: f4f5d1c7-d84d-4867-810f-2708cd6de0da
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 076e10e095b50cc96187f2ec13ade2365d83dad3
ms.lasthandoff: 03/02/2017

---

# <a name="using-the-stringbuilder-class"></a>Verwenden der StringBuilder-Klasse

Das [String](xref:System.String)-Objekt ist nicht änderbar. Jedes Mal, wenn Sie eine der Methoden in der [System.String](xref:System.String)-Klasse verwenden, erstellen Sie ein neues Zeichenfolgenobjekt im Arbeitsspeicher, das eine neue Zuordnung von Speicherplatz für dieses neue Objekt erfordert. In Fällen, in denen Sie wiederholte Änderungen an einer Zeichenfolge vornehmen müssen, kann der Aufwand, der mit dem Erstellen eines neuen [String](xref:System.String)-Objekts verbunden ist, erheblich sein. Die [System.Text.StringBuilder](xref:System.Text.StringBuilder)-Klasse kann verwendet werden, wenn Sie eine Zeichenfolge ändern möchten, ohne ein neues Objekt zu erstellen. Beispielsweise lässt sich durch Verwenden der [StringBuilder](xref:System.Text.StringBuilder)-Klasse die Leistung steigern, wenn zahlreiche Zeichenfolgen in einer Schleife verkettet werden.

## <a name="importing-the-systemtext-namespace"></a>Importieren des System.Text-Namespace

Die [StringBuilder](xref:System.Text.StringBuilder)-Klasse befindet sich im [System.Text](xref:System.Text)-Namespace. Wenn Sie in Ihrem Code nicht den vollqualifizierten Typnamen bereitstellen möchten, können Sie den [System.Text](xref:System.Text)-Namespace importieren: 

```csharp
using System;
using System.Text;
```

```vb
Imports System.Text
```

## <a name="instantiating-a-stringbuilder-object"></a>Instanziieren eines StringBuilder-Objekts

Sie können eine neue Instanz der [StringBuilder](xref:System.Text.StringBuilder)-Klasse erstellen, indem Sie Ihre Variable mit einer der Methoden für überladene Konstruktoren initialisieren, wie im folgenden Beispiel verdeutlicht.

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
```

## <a name="setting-the-capacity-and-length"></a>Festlegen von Kapazität und Länge

Obwohl ein [StringBuilder](xref:System.Text.StringBuilder)-Objekt ein dynamisches Objekt ist, das es Ihnen ermöglicht, die Anzahl der Zeichen in der darin gekapselten Zeichenfolge zu erweitern, können Sie einen Wert für die maximale Anzahl von Zeichen festlegen, die das Objekt enthalten darf. Dieser Wert wird als die Kapazität des Objekts bezeichnet und darf nicht mit der Länge der Zeichenfolge verwechselt werden, die im aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekt enthalten ist. Sie könnten z.B. eine neue Instanz der [StringBuilder](xref:System.Text.StringBuilder)-Klasse mit der Zeichenfolge „Hello“ erstellen, die eine Länge von 5 Zeichen hat, und Sie könnten angeben, dass das Objekt eine maximale Kapazität von 25 Zeichen hat. Wenn das [StringBuilder](xref:System.Text.StringBuilder)-Objekt geändert wird, ordnet es für sich selbst keine neue Größe zu, bis die Kapazität erreicht ist. Tritt dieser Fall ein, wird der neue Speicherplatz automatisch zugeordnet, und die Kapazität wird verdoppelt. Sie können die Kapazität der [StringBuilder](xref:System.Text.StringBuilder)-Klasse angeben, indem Sie einen der überladenen Konstruktoren verwenden. Im folgenden Beispiel wird festgelegt, dass das `MyStringBuilder`-Objekt auf maximal 25 Zeichen erweitert werden kann.

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!", 25);
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!", 25) 
```

Darüber hinaus können Sie die [Capacity](xref:System.Text.StringBuilder.Capacity)-Eigenschaft mit Lese-/Schreibzugriff verwenden, um die maximale Länge Ihres Objekts festzulegen. Im folgenden Beispiel wird die [Capacity](xref:System.Text.StringBuilder.Capacity)-Eigenschaft verwendet, um die maximale Objektlänge zu definieren.

```csharp
MyStringBuilder.Capacity = 25;
```

```vb
MyStringBuilder.Capacity = 25
```

Mithilfe der [EnsureCapacity](xref:System.Text.StringBuilder.EnsureCapacity(System.Int32))-Methode kann die Kapazität des aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekts überprüft werden. Ist die Kapazität größer als der übergebene Wert, wird keine Änderung vorgenommen. Ist die Kapazität dagegen kleiner als der übergebene Wert, wird die aktuelle Kapazität entsprechend dem übergebenen Wert geändert.

Die [Length](xref:System.Text.StringBuilder.Length)-Eigenschaft kann auch angezeigt oder festgelegt werden. Wenn Sie für die [Length](xref:System.Text.StringBuilder.Length)-Eigenschaft einen Wert festlegen, der größer ist als der Wert der [Capacity](xref:System.Text.StringBuilder.Capacity)-Eigenschaft, wird die [Capacity](xref:System.Text.StringBuilder.Capacity)-Eigenschaft automatisch auf den Wert der [Length](xref:System.Text.StringBuilder.Length)-Eigenschaft festgelegt. Ist die [Length](xref:System.Text.StringBuilder.Length)-Eigenschaft auf einen Wert festgelegt, der kleiner als die Länge der Zeichenfolge im aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekt ist, wird die Zeichenfolge gekürzt.

## <a name="modifying-the-stringbuilder-string"></a>Ändern der StringBuilder-Zeichenfolge

In der folgenden Tabelle sind die Methoden aufgeführt, mit denen Sie den Inhalt eines [StringBuilder](xref:System.Text.StringBuilder)-Objekts ändern können.

Methodenname | Verwendung
----------- | ---
[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) | Fügt Informationen an das Ende des aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekts an.
[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) | Ersetzt einen in einer Zeichenfolge übergebenen Formatbezeichner durch formatierten Text.
[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) | Fügt eine Zeichenfolge oder ein Objekt in den angegebenen Index des aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekts ein.
[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) | Entfernt eine angegebene Anzahl von Zeichen aus dem aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekt.
[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Ersetzt ein angegebenes Zeichen an einem angegebenen Index.

### <a name="append"></a>Anfügen

Mithilfe der [StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char))-Methode kann Text oder eine Zeichenfolgendarstellung eines Objekts am Ende einer Zeichenfolge hinzugefügt werden, die durch das aktuelle [StringBuilder](xref:System.Text.StringBuilder)-Objekt dargestellt wird. Im folgenden Beispiel wird ein [StringBuilder](xref:System.Text.StringBuilder)-Objekt auf „Hello World“ initialisiert und anschließend Text am Ende des Objekts angefügt. Speicherplatz wird automatisch nach Bedarf zugeordnet.

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Append(" What a beautiful day.");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World! What a beautiful day.
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Append(" What a beautiful day.")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World! What a beautiful day.
```

### <a name="appendformat"></a>AppendFormat

Die [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))-Methode fügt Text am Ende des [StringBuilder](xref:System.Text.StringBuilder)-Objekts hinzu. Die Methode unterstützt die Funktion für die zusammengesetzte Formatierung (weitere Informationen finden Sie unter [Zusammengesetzte Formatierung](composite-format.md)) durch Aufrufen der [IFormattable](xref:System.IFormattable)-Implementierung der Objekte, die formatiert werden sollen. Daher akzeptiert sie die Standardformatzeichenfolgen für numerische Werte, Datums- und Uhrzeitwerte sowie Enumerationswerte, die benutzerdefinierten Formatzeichenfolgen für numerische Werte sowie Datums- und Uhrzeitwerte und die Formatzeichenfolgen, die für benutzerdefinierte Typen definiert sind. (Weitere Informationen zur Formatierung finden Sie unter [Formatieren von Typen](formatting-types.md).) Sie können diese Methode verwenden, um das Format von Variablen anzupassen und diese Werte an ein [StringBuilder](xref:System.Text.StringBuilder)-Objekt anzufügen. Im folgenden Beispiel wird die AppendFormat-Methode verwendet, um einen als Währungsbetrag formatierten ganzzahligen Wert am Ende eines [StringBuilder](xref:System.Text.StringBuilder)-Objekts einzufügen.

```csharp
int MyInt = 25; 
StringBuilder MyStringBuilder = new StringBuilder("Your total is ");
MyStringBuilder.AppendFormat("{0:C} ", MyInt);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Your total is $25.00
```

```vb
Dim MyInt As Integer = 25
Dim MyStringBuilder As New StringBuilder("Your total is ")
MyStringBuilder.AppendFormat("{0:C} ", MyInt)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'     Your total is $25.00 
```

### <a name="insert"></a>Insert

Mit der [StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char))-Methode wird an einer angegebenen Position im aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekt eine Zeichenfolge oder ein Objekt hinzugefügt. Im folgenden Beispiel wird mit dieser Methode ein Wort an der sechsten Position eines [StringBuilder](xref:System.Text.StringBuilder)-Objekts eingefügt.

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Insert(6,"Beautiful ");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello Beautiful World!
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Insert(6, "Beautiful ")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'      Hello Beautiful World!
```

### <a name="remove"></a>Remove

Über die [StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))-Methode können Sie, beginnend bei einem angegebenen nullbasierten Index, eine bestimmte Anzahl von Zeichen aus dem aktuellen [StringBuilder](xref:System.Text.StringBuilder)-Objekt entfernen. Im folgenden Beispiel wird die [Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))-Methode verwendet, um ein [StringBuilder](xref:System.Text.StringBuilder)-Objekt zu kürzen.

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Remove(5,7);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Remove(5, 7)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello
```

### <a name="replace"></a>Ersetzen

Die [StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Ersetzt ein angegebenes Zeichen an einem angegebenen Index.
-Methode kann verwendet werden, um Zeichen im [StringBuilder](xref:System.Text.StringBuilder)-Objekt durch ein anderes angegebenes Zeichen zu ersetzen. Im folgenden Beispiel wird die [Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Ersetzt ein angegebenes Zeichen an einem angegebenen Index.
-Methode verwendet, um in einem [StringBuilder](xref:System.Text.StringBuilder)-Objekt nach allen Vorkommen des Ausrufezeichens (!) zu suchen und diese durch das Fragezeichen (?) zu ersetzen.
 
 ```csharp
 StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Replace('!', '?');
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World?
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Replace("!"c, "?"c)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World?
```

## <a name="converting-a-stringbuilder-object-to-a-string"></a>Konvertieren eines StringBuilder-Objekts in eine Zeichenfolge

Sie müssen das [StringBuilder](xref:System.Text.StringBuilder)-Objekt in ein [String](xref:System.String)-Objekt konvertieren, bevor Sie die vom [StringBuilder](xref:System.Text.StringBuilder)-Objekt dargestellte Zeichenfolge an eine Methode übergeben können, die einen [String](xref:System.String)-Parameter hat, oder bevor Sie sie in der Benutzeroberfläche anzeigen. Diese Konvertierung führen Sie aus, indem Sie die [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString)-Methode aufrufen. Im folgenden Beispiel werden einige [StringBuilder](xref:System.Text.StringBuilder)-Methoden aufgerufen, und anschließend wird die [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString)-Methode aufgerufen, um die Zeichenfolge anzuzeigen.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      StringBuilder sb = new StringBuilder();
      bool flag = true;
      string[] spellings = { "recieve", "receeve", "receive" };
      sb.AppendFormat("Which of the following spellings is {0}:", flag);
      sb.AppendLine();
      for (int ctr = 0; ctr <= spellings.GetUpperBound(0); ctr++) {
         sb.AppendFormat("   {0}. {1}", ctr, spellings[ctr]);
         sb.AppendLine();
      }
      sb.AppendLine();
      Console.WriteLine(sb.ToString());
   }
}
// The example displays the following output:
//       Which of the following spellings is True:
//          0. recieve
//          1. receeve
//          2. receive
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim sb As New StringBuilder()
      Dim flag As Boolean = True
      Dim spellings() As String = { "recieve", "receeve", "receive" }
      sb.AppendFormat("Which of the following spellings is {0}:", flag)
      sb.AppendLine()
      For ctr As Integer = 0 To spellings.GetUpperBound(0)
         sb.AppendFormat("   {0}. {1}", ctr, spellings(ctr))
         sb.AppendLine()
      Next
      sb.AppendLine()
      Console.WriteLine(sb.ToString())
   End Sub
End Module
' The example displays the following output:
'       Which of the following spellings is True:
'          0. recieve
'          1. receeve
'          2. receive
```

## <a name="see-also"></a>Siehe auch

[System.Text.StringBuilder](xref:System.Text.StringBuilder)

[Grundlegende Zeichenfolgenoperationen](basic-string-operations.md)

[Formatierung von Typen](formatting-types.md)

