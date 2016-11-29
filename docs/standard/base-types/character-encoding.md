---
title: Zeichencodierung in .NET
description: Zeichencodierung in .NET
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bce54e41-e9dc-493a-8988-1cbadc340fe8
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: e72540726bdd1b3624064c7388e58d80320c5831

---

# <a name="character-encoding-in-net"></a>Zeichencodierung in .NET

Zeichen sind abstrakte Entitäten, die auf viele verschiedene Arten dargestellt werden können. Eine Zeichencodierung ist ein System, in dem jedes Zeichen in einem unterstützten Zeichensatz mit einem Wert verknüpft wird, der dieses Zeichen darstellt. Beispielsweise handelt es sich beim Morsealphabet um eine Zeichencodierung, die alle Zeichen im römischen Alphabet mit einem Muster aus Punkten und Bindestrichen verknüpft, das für die Übertragung über Telegrafenleitungen geeignet ist. Bei einer Zeichencodierung für Computer wird jedes Zeichen in einem unterstützten Zeichensatz mit einem numerischen Wert verknüpft, der das jeweilige Zeichen darstellt. Eine Zeichencodierung verfügt über zwei verschiedene Komponenten:

* Ein Encoder, der eine Folge von Zeichen in eine Folge von numerischen Werten (Bytes) übersetzt

* Ein Decoder, der eine Bytefolge in eine Folge von Zeichen übersetzt

Die Zeichencodierung gibt die Regeln für die Funktionsweise von Encoder und Decoder an. Zum Beispiel beschreibt die [UTF8Encoding](xref:System.Text.UTF8Encoding)-Klasse die Regeln zum Codieren und Decodieren von UTF-8 (8-Bit-Unicode Transformation Format). In diesem Format werden für die Darstellung eines einzelnen Unicodezeichens ein bis vier Bytes verwendet. Die Codierung und Decodierung können auch eine Validierung beinhalten. Die [UnicodeEncoding](xref:System.Text.UnicodeEncoding)-Klasse prüft z.B. alle Ersatzzeichen, um sicherzustellen, dass sie gültige Ersatzzeichenpaare bilden. (Ein Ersatzzeichenpaar besteht aus einem Zeichen mit einem Codepunkt zwischen U+D800 und U+DBFF gefolgt von einem Zeichen mit einem Codepunkt zwischen U+DC00 und U+DFFF.) Eine Fallbackstrategie legt fest, wie ein Encoder ungültige Zeichen behandelt oder wie ein Decoder ungültige Bytes behandelt. 

> [!WARNING]
> Die .NET-Codierungsklassen bieten eine Möglichkeit, Zeichendaten zu speichern und zu konvertieren. Sie sollten nicht verwendet werden, um Binärdaten im Zeichenfolgenformat zu speichern. Abhängig von der verwendeten Codierung kann das Konvertieren von Binärdaten in das Zeichenfolgenformat mithilfe der Codierungsklassen zu unerwartetem Verhalten und ungenauen oder beschädigten Daten führen. Um Binärdaten in ein Zeichenfolgenformat zu konvertieren, verwenden Sie die [Convert.ToBase64String](xref:System.Convert.ToBase64String(System.Byte[]))-Methode. 
 
.NET verwendet die UTF-16-Codierung (angegeben durch die [UnicodeEncoding](xref:System.Text.UnicodeEncoding)-Klasse), um Zeichen und Zeichenfolgen darzustellen. Anwendungen, die auf die Common Language Runtime abzielen, verwenden Encoder, um von der Common Language Runtime unterstützte Unicode-Zeichendarstellungen anderen Codierungsschemen zuzuordnen. Decoder werden verwendet, um Zeichen aus Nicht-Unicode-Codierungen Unicode zuzuordnen.

Dieses Thema enthält folgende Abschnitte:

* [Codierungen in .NET](#encodings-in-net)

* [Auswählen einer Encoding-Klasse](#selecting-an-encoding-class)

* [Verwenden eines Codierungsobjekts](#using-an-encoding-object)

* [Auswählen einer Fallbackstrategie](#choosing-a-fallback-strategy)

* [Implementieren einer benutzerdefinierten Fallbackstrategie](#implementing-a-custom-fallback-strategy)

## <a name="encodings-in-net"></a>Codierungen in .NET

Alle Zeichencodierungsklassen in .NET erben von der abstrakten [System.Text.Encoding](xref:System.Text.Encoding)-Klasse, die die Funktionen definiert, die allen Zeichencodierungen gemeinsam sind. Um auf die einzelnen in .NET implementierten Codierungsobjekte zuzugreifen, gehen Sie wie folgt vor:

* Verwenden Sie die statischen Eigenschaften der [Encoding](xref:System.Text.Encoding)-Klasse, die Objekte zurückgibt, die die in .NET verfügbaren Standardzeichencodierungen darstellen (ASCII, UTF-7, UTF-8, UTF-16 und UTF-32). Die [Encoding.Unicode](xref:System.Text.Encoding.Unicode)-Eigenschaft gibt z.B. ein [UnicodeEncoding](xref:System.Text.UnicodeEncoding)-Objekt zurück. Jedes Objekt verwendet einen Ersatzfallback für die Behandlung von Zeichenfolgen, die nicht codiert werden können, und von Bytes, die nicht decodiert werden können. (Weitere Informationen finden Sie im Abschnitt [Ersatzfallback](#replacement-fallback).)

* Rufen Sie den Klassenkonstruktor der Codierung auf. Objekte für ASCII-, UTF-7-, UTF-8-, UTF-16- und UTF-32-Codierungen können auf diese Weise instanziiert werden. Standardmäßig verwendet jedes Objekt den Ersatzfallback zur Behandlung von Zeichenfolgen, die nicht codiert werden können, und von Bytes, die nicht decodiert werden können. Sie können aber angeben, dass stattdessen eine Ausnahme ausgelöst werden soll. (Weitere Informationen finden Sie in den Abschnitten [Ersatzfallback](#replacement-fallback) und [Ausnahmefallback](#exception-fallback).)

* Rufen Sie den [Encoding.Encoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32))-Konstruktor auf, und übergeben Sie eine ganze Zahl, die die Codierung darstellt. Standardcodierungsobjekte verwenden den Ersatzfallback, und Codepage- und DBCS (Doppelbyte-Zeichensatz)-Codierungsobjekte verwenden den Fallback mit ähnlichen Zeichen zur Behandlung von Zeichenfolgen, die nicht codiert werden können, und von Bytes, die nicht decodiert werden können. (Weitere Informationen finden Sie im Abschnitt [Fallback mit ähnlichen Zeichen](#best-fit-fallback).)

* Rufen Sie die [Encoding.GetEncoding](xref:System.Text.Encoding.GetEncoding(System.Int32))-Methode auf, die jede in .NET verfügbare Standard-, Codepage- oder DBCS-Codierung zurückgibt. Mithilfe von Überladungen können Sie sowohl für den Encoder als auch den Decoder ein Fallbackobjekt angeben.

> [!NOTE]
> Gemäß Unicode-Standard werden jedem Zeichen aller unterstützten Skripts ein Codepunkt (eine Zahl) und ein Name zugewiesen. Das Zeichen "A" wird beispielsweise durch den Codepunkt U+0041 und den Namen "LATIN CAPITAL LETTER A" dargestellt. Die UTF (Unicode-Transformation Format)-Codierungen definieren Möglichkeiten, diesen Codepunkt in eine Abfolge aus einem oder mehreren Bytes zu codieren. Ein Unicode-Datencodierungsschema vereinfacht die Entwicklung weltweit einsetzbarer Anwendungen, da es die Darstellung von Zeichen aus beliebigen Zeichensätzen in einer Codierung ermöglicht. Anwendungsentwickler müssen nicht mehr das Codierungsschema verfolgen, das für die Erstellung von Zeichen für eine bestimmte Sprache oder ein Schreibsystem verwendet wurde, und die Daten können länderübergreifend auf allen Systemen verwendet werden, ohne beschädigt zu werden.
>
>  .NET unterstützt drei Codierungen, die durch den Unicode-Standard definiert sind: UTF-8, UTF-16 und UTF-32. Weitere Informationen finden Sie im Unicode-Standard auf der [Unicode](http://www.unicode.org/)-Homepage.
 
.NET unterstützt die in der folgenden Tabelle aufgelisteten Zeichencodierungssysteme.

Codierung | Klasse | Beschreibung | Vorteile/Nachteile
-------- | ----- | ----------- | ------------------------ 
ASCII | [ASCIIEncoding](xref:System.Text.ASCIIEncoding) | Codiert einen begrenzten Bereich von Zeichen mithilfe der unteren sieben Bits eines Bytes. | Da diese Codierung nur Zeichenwerte von U+0000 bis U+007F unterstützt, ist sie in den meisten Fällen für weltweit einsetzbare Anwendungen nicht geeignet.
UTF-7 | [UTF7Encoding](xref:System.Text.UTF7Encoding) | Stellt Zeichen als Sequenzen von 7-Bit-ASCII-Zeichen dar. Nicht-ASCII-Unicode-Zeichen werden durch eine Escapesequenz von ASCII-Zeichen dargestellt. | UTF-7 unterstützt Protokolle wie E-Mail- und Newsgroupprotokolle. UTF-7 ist jedoch nicht besonders sicher oder robust. In einigen Fällen kann die Änderung eines Bits die Interpretation einer gesamten UTF-7-Zeichenfolge radikal ändern. In anderen Fällen können verschiedene UTF-7-Zeichenfolgen denselben Text codieren. Bei Sequenzen, die Nicht-ASCII-Zeichen enthalten, benötigt UTF-7 mehr Speicherplatz als UTF-8, und auch die Codierung/Decodierung erfolgt langsamer. Daher sollten Sie nach Möglichkeit UTF-8 anstelle von UTF-7 verwenden.
UTF-8 | [UTF8Encoding](xref:System.Text.UTF8Encoding) | Stellt jeden Unicode-Codepunkt als eine Folge von einem bis vier Bytes dar. | UTF-8 unterstützt 8-Bit-Datengrößen und funktioniert mit vielen vorhandenen Betriebssystemen. Im ASCII-Zeichenbereich ist UTF-8 mit der ASCII-Codierung identisch und ermöglicht einen umfangreicheren Zeichensatz. Für CJK-Skripts (Chinesisch, Japanisch, Koreanisch) können bei UTF-8 jedoch drei Bytes für jedes Zeichen erforderlich sein, und es können größere Datengrößen als bei UTF-16 entstehen. Manchmal wird die größere Datengröße für den CJK-Bereich jedoch durch die Menge an ASCII-Daten, z. B. HTML-Tags, gerechtfertigt.
UTF-16 | [UnicodeEncoding](xref:System.Text.UnicodeEncoding) | Stellt jeden Unicode-Codepunkt als Folge von einer oder zwei 16-Bit-Ganzzahlen dar. Die meisten allgemeinen Unicode-Zeichen erfordern nur einen UTF-16-Codepunkt. Ergänzende Unicode-Zeichen (U+10000 und höher) erfordern allerdings zwei UTF-16-Ersatzzeichen-Codepunkte. Sowohl Little-Endian- als auch Big-Endian-Bytereihenfolgen werden unterstützt. | Die UTF-16-Codierung wird von der Common Language Runtime zur Darstellung von Char-Werten und String-Werten und vom Windows-Betriebssystem zur Darstellung von WCHAR-Werten verwendet.
UTF-32 | [UTF32Encoding](xref:System.Text.UTF32Encoding) | Stellt jeden Unicode-Codepunkt als 32-Bit-Ganzzahl dar. Sowohl Little-Endian- als auch Big-Endian-Bytereihenfolgen werden unterstützt. | Die UTF-32-Codierung wird verwendet, wenn Anwendungen das Verhalten mit Ersatzzeichen-Codepunkten der UTF-16-Codierung unter Betriebssystemen vermeiden möchten, bei denen codierter Speicherplatz von zu großer Bedeutung ist. Einzelne Symbole, die in einer Anzeige gerendert werden, können dennoch mit mehr als einem UTF-32-Zeichen codiert werden.

Diese Codierungen ermöglichen Ihnen die Verwendung von Unicode-Zeichen und von Codierungen, die in älteren Anwendungen am häufigsten verwendet werden. Außerdem können Sie eine benutzerdefinierte Codierung erstellen, indem Sie eine von [Encoding](xref:System.Text.Encoding) erbende Klasse definieren und deren Member überschreiben.

> [!NOTE]
> Standardmäßig stellt .NET Core keine anderen Codepagecodierungen als Codepage 28591 und Unicode-Codierungen (z.B. UTF-8 und UTF-16) bereit. Allerdings können Sie Ihrer App die Codepagecodierungen hinzufügen, die in Standard-Windows-Apps verwendet werden, die .NET Framework als Ziel nutzen. Vollständige Informationen finden Sie im Thema [EncodingProvider](xref:System.Text.EncodingProvider). 

## <a name="selecting-an-encoding-class"></a>Auswählen einer Encoding-Klasse

Wenn Sie die Möglichkeit haben, die von der Anwendung verwendete Codierung auszuwählen, sollten Sie eine Unicode-Codierung verwenden, vorzugsweise [UTF8Encoding](xref:System.Text.UTF8Encoding) oder [UnicodeEncoding](xref:System.Text.UnicodeEncoding). (.NET unterstützt auch eine dritte Unicode-Codierung, [UTF32Encoding](xref:System.Text.UTF32Encoding).) 

Wenn Sie eine ASCII-Codierung ([ASCIIEncoding](xref:System.Text.ASCIIEncoding)) verwenden möchten, wählen Sie stattdessen [UTF8Encoding](xref:System.Text.UTF8Encoding). Die beiden Codierungen sind für den ASCII-Zeichensatz identisch. [UTF8Encoding](xref:System.Text.UTF8Encoding) bietet allerdings die folgenden Vorteile: 

* Alle Unicode-Zeichen können dargestellt werden, während [ASCIIEncoding](xref:System.Text.ASCIIEncoding) nur die Unicode-Zeichenwerte zwischen U+0000 und U+007F unterstützt.

* Weitere Vorteile sind die Fehlererkennung und die verbesserte Sicherheit.

* Die Geschwindigkeit wurde optimiert und sollte schneller sein als jede andere Codierung. Selbst bei Inhalten, bei denen es sich um reine ASCII-Daten handelt, erfolgen mit [UTF8Encoding](xref:System.Text.UTF8Encoding) durchgeführte Operationen schneller als mit [ASCIIEncoding](xref:System.Text.ASCIIEncoding) durchgeführte Operationen.

Sie sollten daher in Erwägung ziehen, [ASCIIEncoding](xref:System.Text.ASCIIEncoding) nur für ältere Anwendungen zu verwenden. Allerdings kann [UTF8Encoding](xref:System.Text.UTF8Encoding) auch für ältere Anwendungen aus folgenden Gründen die bessere Wahl sein (ausgehend von den Standardeinstellungen):

* Wenn die Anwendung Inhalte, die keine reinen ASCII-Daten sind, mit [ASCIIEncoding](xref:System.Text.ASCIIEncoding) codiert, wird jedes Nicht-ASCII-Zeichen als Fragezeichen (?) codiert. Wenn die Anwendung diese Daten anschließend decodiert, gehen die Informationen verloren.


* Wenn die Anwendung Inhalte, die keine reinen ASCII-Daten sind, mit [UTF8Encoding](xref:System.Text.UTF8Encoding) codiert und als ASCII-Daten interpretiert, erscheint das Ergebnis unverständlich. Wenn die Anwendung dann jedoch einen UTF-8-Decoder verwendet, um diese Daten zu decodieren, durchlaufen sie einen erfolgreichen Roundtrip.

In einer Webanwendung sollten die Zeichen, die als Antwort auf eine Webanforderung an den Client gesendet werden, die auf dem Client verwendete Codierung widerspiegeln. In den meisten Fällen sollten Sie die [HttpResponse.ContentEncoding](xref:System.Net.HttpResponseHeader.ContentEncoding)-Eigenschaft auf den Wert festlegen, der von der [HttpRequestHeader.ContentEncoding](xref:System.Net.HttpRequestHeader.ContentEncoding)-Eigenschaft zurückgegeben wird, um Text in der vom Benutzer erwarteten Codierung anzuzeigen.

## <a name="using-an-encoding-object"></a>Verwenden eines Codierungsobjekts

Ein Codierer konvertiert eine Zeichenfolge (meistens Unicode-Zeichen) in die numerische Entsprechung (Byte). Beispielsweise können Sie einen ASCII-Encoder verwenden, um Unicode-Zeichen in ASCII zu konvertieren, damit sie in der Konsole angezeigt werden können. Um die Konvertierung auszuführen, rufen Sie die [Encoding.GetBytes](xref:System.Text.Encoding.GetBytes(System.Char[]))-Methode auf. Wenn Sie vor Ausführung der Codierung ermitteln möchten, wie viele Bytes zum Speichern der codierten Zeichen benötigt werden, können Sie die [GetByteCount](xref:System.Text.Encoding.GetByteCount(System.Char[]))-Methode aufrufen.

Im folgenden Beispiel wird ein einzelnes Bytearray verwendet, um Zeichenfolgen in zwei separaten Vorgängen zu codieren. Ein verwalteter Index gibt die Anfangsposition im Bytearray für die nächste Gruppe von ASCII-codierten Bytes an. Die [ASCIIEncoding.GetByteCount(String)](xref:System.Text.ASCIIEncoding.GetByteCount(System.String))-Methode wird aufgerufen, um sicherzustellen, dass das Bytearray groß genug für die codierte Zeichenfolge ist. Die [ASCIIEncoding.GetBytes(String, Int32, Int32, Byte[], Int32)](xref:System.Text.ASCIIEncoding.GetBytes(System.Char[],System.Int32,System.Int32,System.Byte[],System.Int32))-Methode wird dann zum Codieren der Zeichen in der Zeichenfolge aufgerufen.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      string[] strings= { "This is the first sentence. ", 
                          "This is the second sentence. " };
      Encoding asciiEncoding = Encoding.ASCII;

      // Create array of adequate size.
      byte[] bytes = new byte[49];
      // Create index for current position of array.
      int index = 0;

      Console.WriteLine("Strings to encode:");
      foreach (var stringValue in strings) {
         Console.WriteLine("   {0}", stringValue);

         int count = asciiEncoding.GetByteCount(stringValue);
         if (count + index >=  bytes.Length)
            Array.Resize(ref bytes, bytes.Length + 50);

         int written = asciiEncoding.GetBytes(stringValue, 0, 
                                              stringValue.Length, 
                                              bytes, index);    

         index = index + written; 
      } 
      Console.WriteLine("\nEncoded bytes:");
      Console.WriteLine("{0}", ShowByteValues(bytes, index));
      Console.WriteLine();

      // Decode Unicode byte array to a string.
      string newString = asciiEncoding.GetString(bytes, 0, index);
      Console.WriteLine("Decoded: {0}", newString);
   }

   private static string ShowByteValues(byte[] bytes, int last ) 
   {
      string returnString = "   ";
      for (int ctr = 0; ctr <= last - 1; ctr++) {
         if (ctr % 20 == 0)
            returnString += "\n   ";
         returnString += String.Format("{0:X2} ", bytes[ctr]);
      }
      return returnString;
   }
}
// The example displays the following output:
//       Strings to encode:
//          This is the first sentence.
//          This is the second sentence.
//       
//       Encoded bytes:
//       
//          54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
//          6E 74 65 6E 63 65 2E 20 54 68 69 73 20 69 73 20 74 68 65 20
//          73 65 63 6F 6E 64 20 73 65 6E 74 65 6E 63 65 2E 20
//       
//       Decoded: This is the first sentence. This is the second sentence.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim strings() As String = { "This is the first sentence. ", 
                                  "This is the second sentence. " }
      Dim asciiEncoding As Encoding = Encoding.ASCII

      ' Create array of adequate size.
      Dim bytes(50) As Byte
      ' Create index for current position of array.
      Dim index As Integer = 0

      Console.WriteLine("Strings to encode:")
      For Each stringValue In strings
         Console.WriteLine("   {0}", stringValue)

         Dim count As Integer = asciiEncoding.GetByteCount(stringValue)
         If count + index >=  bytes.Length Then
            Array.Resize(bytes, bytes.Length + 50)
         End If
         Dim written As Integer = asciiEncoding.GetBytes(stringValue, 0, 
                                                         stringValue.Length, 
                                                         bytes, index)    

         index = index + written 
      Next 
      Console.WriteLine()
      Console.WriteLine("Encoded bytes:")
      Console.WriteLine("{0}", ShowByteValues(bytes, index))
      Console.WriteLine()

      ' Decode Unicode byte array to a string.
      Dim newString As String = asciiEncoding.GetString(bytes, 0, index)
      Console.WriteLine("Decoded: {0}", newString)
   End Sub

   Private Function ShowByteValues(bytes As Byte(), last As Integer) As String
      Dim returnString As String = "   "
      For ctr As Integer = 0 To last - 1
         If ctr Mod 20 = 0 Then returnString += vbCrLf + "   "
         returnString += String.Format("{0:X2} ", bytes(ctr))
      Next
      Return returnString
   End Function
End Module
' The example displays the following output:
'       Strings to encode:
'          This is the first sentence.
'          This is the second sentence.
'       
'       Encoded bytes:
'       
'          54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
'          6E 74 65 6E 63 65 2E 20 54 68 69 73 20 69 73 20 74 68 65 20
'          73 65 63 6F 6E 64 20 73 65 6E 74 65 6E 63 65 2E 20
'       
'       Decoded: This is the first sentence. This is the second sentence.
```

Ein Decoder konvertiert ein Bytearray, das eine spezifische Zeichencodierung darstellt, in einen Satz von Zeichen, d. h. entweder in ein Zeichenarray oder in eine Zeichenfolge. Um ein Bytearray in ein Zeichenarray zu decodieren, rufen Sie die [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[]))-Methode auf. Um ein Bytearray in eine Zeichenfolge zu decodieren, rufen Sie die [GetString](xref:System.Text.Encoding.GetString(System.Byte[]))-Methode auf. Wenn Sie vor Ausführung der Decodierung ermitteln möchten, wie viele Zeichen zum Speichern der decodierten Bytes benötigt werden, können Sie die [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[]))-Methode aufrufen.

Im folgenden Beispiel werden drei Zeichenfolgen codiert und dann in einzelnes Array von Zeichen decodiert. Ein verwalteter Index gibt die Anfangsposition im Zeichenarray für die nächste Gruppe von decodierten Zeichen an. Die [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[]))-Methode wird aufgerufen, um sicherzustellen, dass das Zeichenarray groß genug für alle decodierten Zeichen ist. Die [ASCIIEncoding.GetChars(Byte[], Int32, Int32, Char[], Int32)](xref:System.Text.ASCIIEncoding.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32))-Methode wird dann zum Decodieren des Bytearrays aufgerufen.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      string[] strings = { "This is the first sentence. ", 
                           "This is the second sentence. ",
                           "This is the third sentence. " };
      Encoding asciiEncoding = Encoding.ASCII;
      // Array to hold encoded bytes.
      byte[] bytes;
      // Array to hold decoded characters.
      char[] chars = new char[50];
      // Create index for current position of character array.
      int index = 0;     

      foreach (var stringValue in strings) {
         Console.WriteLine("String to Encode: {0}", stringValue);
         // Encode the string to a byte array.
         bytes = asciiEncoding.GetBytes(stringValue);
         // Display the encoded bytes.
         Console.Write("Encoded bytes: ");
         for (int ctr = 0; ctr < bytes.Length; ctr++)
            Console.Write(" {0}{1:X2}", 
                          ctr % 20 == 0 ? Environment.NewLine : "", 
                          bytes[ctr]);
         Console.WriteLine();

         // Decode the bytes to a single character array.
         int count = asciiEncoding.GetCharCount(bytes);
         if (count + index >=  chars.Length)
            Array.Resize(ref chars, chars.Length + 50);

         int written = asciiEncoding.GetChars(bytes, 0, 
                                              bytes.Length, 
                                              chars, index);              
         index = index + written;
         Console.WriteLine();       
      }

      // Instantiate a single string containing the characters.
      string decodedString = new string(chars, 0, index - 1);
      Console.WriteLine("Decoded string: ");
      Console.WriteLine(decodedString);
   }
}
// The example displays the following output:
//    String to Encode: This is the first sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
//    6E 74 65 6E 63 65 2E 20
//    
//    String to Encode: This is the second sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 73 65 63 6F 6E 64 20 73
//    65 6E 74 65 6E 63 65 2E 20
//    
//    String to Encode: This is the third sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 74 68 69 72 64 20 73 65
//    6E 74 65 6E 63 65 2E 20
//    
//    Decoded string:
//    This is the first sentence. This is the second sentence. This is the third sentence.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim strings() As String = { "This is the first sentence. ", 
                                  "This is the second sentence. ",
                                  "This is the third sentence. " }
      Dim asciiEncoding As Encoding = Encoding.ASCII
      ' Array to hold encoded bytes.
      Dim bytes() As Byte
      ' Array to hold decoded characters.
      Dim chars(50) As Char
      ' Create index for current position of character array.
      Dim index As Integer     

      For Each stringValue In strings
         Console.WriteLine("String to Encode: {0}", stringValue)
         ' Encode the string to a byte array.
         bytes = asciiEncoding.GetBytes(stringValue)
         ' Display the encoded bytes.
         Console.Write("Encoded bytes: ")
         For ctr As Integer = 0 To bytes.Length - 1
            Console.Write(" {0}{1:X2}", If(ctr Mod 20 = 0, vbCrLf, ""), 
                                        bytes(ctr))
         Next         
         Console.WriteLine()

         ' Decode the bytes to a single character array.
         Dim count As Integer = asciiEncoding.GetCharCount(bytes)
         If count + index >=  chars.Length Then
            Array.Resize(chars, chars.Length + 50)
         End If
         Dim written As Integer = asciiEncoding.GetChars(bytes, 0, 
                                                         bytes.Length, 
                                                         chars, index)              
         index = index + written
         Console.WriteLine()       
      Next

      ' Instantiate a single string containing the characters.
      Dim decodedString As New String(chars, 0, index - 1)
      Console.WriteLine("Decoded string: ")
      Console.WriteLine(decodedString)
   End Sub
End Module
' The example displays the following output:
'    String to Encode: This is the first sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
'    6E 74 65 6E 63 65 2E 20
'    
'    String to Encode: This is the second sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 73 65 63 6F 6E 64 20 73
'    65 6E 74 65 6E 63 65 2E 20
'    
'    String to Encode: This is the third sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 74 68 69 72 64 20 73 65
'    6E 74 65 6E 63 65 2E 20
'    
'    Decoded string:
'    This is the first sentence. This is the second sentence. This is the third sentence.
```

Die Codierungs- und Decodierungsmethoden einer von [Encoding](xref:System.Text.Encoding) abgeleiteten Klasse sind für die Behandlung eines vollständigen Satzes von Daten vorgesehen, d.h., alle zu codierenden oder decodierenden Daten werden in einem einzelnen Methodenaufruf angegeben. In einigen Fällen sind Daten jedoch in einem Stream verfügbar, und die zu codierenden und decodierenden Daten sind möglicherweise nur über separate Lesevorgänge verfügbar. Der Codierungs- oder Decodierungsvorgang muss hierbei jeden gespeicherten Zustand aus dem vorherigen Aufruf speichern. Methoden von Klassen, die von [Encoder](xref:System.Text.Encoder) und [Decoder](xref:System.Text.Decoder) abgeleitet sind, können Codierungs- und Decodierungsvorgänge behandeln, die mehrere Methodenaufrufe umfassen.

Ein [Encoder](xref:System.Text.Encoder)-Objekt für eine bestimmte Codierung ist über die [Encoding.GetEncoder](xref:System.Text.Encoding.GetEncoder)-Eigenschaft dieser Codierung verfügbar. Ein [Decoder](xref:System.Text.Decoder)-Objekt für eine bestimmte Codierung ist über die [Encoding.GetDecoder](xref:System.Text.Encoding.GetDecoder)-Eigenschaft dieser Codierung verfügbar. Bei Decodierungsvorgängen beinhalten die von [Decoder](xref:System.Text.Decoder) abgeleiteten Klassen eine [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32))-Methode, jedoch keine Methode, die [Encoding.GetString](xref:System.Text.Encoding.GetString(System.Byte[])) entspricht.

Das folgende Beispiel veranschaulicht den Unterschied zwischen der Verwendung der [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[]))-Methode und der [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32))-Methode zum Decodieren eines Unicode-Bytearrays. Im Beispiel wird eine Zeichenfolge, die einige Unicode-Zeichen enthält, in eine Datei codiert. Anschließend werden die Zeichen mithilfe der zwei Decodierungsmethoden immer um je zehn Bytes decodiert. Da im zehnten und elften Byte ein Ersatzzeichenpaar auftritt, erfolgt die Decodierung mit separaten Methodenaufrufen. Die Ausgabe zeigt, dass die [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[]))-Methode die Bytes nicht ordnungsgemäß decodieren kann und sie stattdessen durch U+FFFD (REPLACEMENT CHARACTER) ersetzt. Die [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32))-Methode kann das Bytearray hingegen erfolgreich decodieren, um die ursprüngliche Zeichenfolge abzurufen.

```csharp
using System;
using System.IO;
using System.Text;

public class Example
{
   public static void Main()
   {
      // Use default replacement fallback for invalid encoding.
      UnicodeEncoding enc = new UnicodeEncoding(true, false, false);

      // Define a string with various Unicode characters.
      string str1 = "AB YZ 19 \uD800\udc05 \u00e4"; 
      str1 += "Unicode characters. \u00a9 \u010C s \u0062\u0308"; 
      Console.WriteLine("Created original string...\n");

      // Convert string to byte array.                     
      byte[] bytes = enc.GetBytes(str1);

      FileStream fs = File.Create(@".\characters.bin");
      BinaryWriter bw = new BinaryWriter(fs);
      bw.Write(bytes);
      bw.Close();

      // Read bytes from file.
      FileStream fsIn = File.OpenRead(@".\characters.bin");
      BinaryReader br = new BinaryReader(fsIn);

      const int count = 10;            // Number of bytes to read at a time. 
      byte[] bytesRead = new byte[10]; // Buffer (byte array).
      int read;                        // Number of bytes actually read. 
      string str2 = String.Empty;      // Decoded string.

      // Try using Encoding object for all operations.
      do { 
         read = br.Read(bytesRead, 0, count);
         str2 += enc.GetString(bytesRead, 0, read); 
      } while (read == count);
      br.Close();
      Console.WriteLine("Decoded string using UnicodeEncoding.GetString()...");
      CompareForEquality(str1, str2);
      Console.WriteLine();

      // Use Decoder for all operations.
      fsIn = File.OpenRead(@".\characters.bin");
      br = new BinaryReader(fsIn);
      Decoder decoder = enc.GetDecoder();
      char[] chars = new char[50];
      int index = 0;                   // Next character to write in array.
      int written = 0;                 // Number of chars written to array.
      do { 
         read = br.Read(bytesRead, 0, count);
         if (index + decoder.GetCharCount(bytesRead, 0, read) - 1 >= chars.Length) 
            Array.Resize(ref chars, chars.Length + 50);

         written = decoder.GetChars(bytesRead, 0, read, chars, index);
         index += written;                          
      } while (read == count);
      br.Close();            
      // Instantiate a string with the decoded characters.
      string str3 = new String(chars, 0, index); 
      Console.WriteLine("Decoded string using UnicodeEncoding.Decoder.GetString()...");
      CompareForEquality(str1, str3); 
   }

   private static void CompareForEquality(string original, string decoded)
   {
      bool result = original.Equals(decoded);
      Console.WriteLine("original = decoded: {0}", 
                        original.Equals(decoded, StringComparison.Ordinal));
      if (! result) {
         Console.WriteLine("Code points in original string:");
         foreach (var ch in original)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
         Console.WriteLine();

         Console.WriteLine("Code points in decoded string:");
         foreach (var ch in decoded)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
         Console.WriteLine();
      }
   }
}
// The example displays the following output:
//    Created original string...
//    
//    Decoded string using UnicodeEncoding.GetString()...
//    original = decoded: False
//    Code points in original string:
//    0041 0042 0020 0059 005A 0020 0031 0039 0020 D800 DC05 0020 00E4 0055 006E 0069 0063 006F
//    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
//    0020 0073 0020 0062 0308
//    Code points in decoded string:
//    0041 0042 0020 0059 005A 0020 0031 0039 0020 FFFD FFFD 0020 00E4 0055 006E 0069 0063 006F
//    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
//    0020 0073 0020 0062 0308
//    
//    Decoded string using UnicodeEncoding.Decoder.GetString()...
//    original = decoded: True
```

```vb
Imports System.IO
Imports System.Text

Module Example
   Public Sub Main()
      ' Use default replacement fallback for invalid encoding.
      Dim enc As New UnicodeEncoding(True, False, False)

      ' Define a string with various Unicode characters.
      Dim str1 As String = String.Format("AB YZ 19 {0}{1} {2}", 
                                         ChrW(&hD800), ChrW(&hDC05), ChrW(&h00e4))
      str1 += String.Format("Unicode characters. {0} {1} s {2}{3}", 
                            ChrW(&h00a9), ChrW(&h010C), ChrW(&h0062), ChrW(&h0308))
      Console.WriteLine("Created original string...")
      Console.WriteLine()

      ' Convert string to byte array.                     
      Dim bytes() As Byte = enc.GetBytes(str1)

      Dim fs As FileStream = File.Create(".\characters.bin")
      Dim bw As New BinaryWriter(fs)
      bw.Write(bytes)
      bw.Close()

      ' Read bytes from file.
      Dim fsIn As FileStream = File.OpenRead(".\characters.bin")
      Dim br As New BinaryReader(fsIn)

      Const count As Integer = 10      ' Number of bytes to read at a time. 
      Dim bytesRead(9) As Byte         ' Buffer (byte array).
      Dim read As Integer              ' Number of bytes actually read. 
      Dim str2 As String = ""          ' Decoded string.

      ' Try using Encoding object for all operations.
      Do 
         read = br.Read(bytesRead, 0, count)
         str2 += enc.GetString(bytesRead, 0, read) 
      Loop While read = count
      br.Close()
      Console.WriteLine("Decoded string using UnicodeEncoding.GetString()...")
      CompareForEquality(str1, str2)
      Console.WriteLine()

      ' Use Decoder for all operations.
      fsIn = File.OpenRead(".\characters.bin")
      br = New BinaryReader(fsIn)
      Dim decoder As Decoder = enc.GetDecoder()
      Dim chars(50) As Char
      Dim index As Integer = 0         ' Next character to write in array.
      Dim written As Integer = 0       ' Number of chars written to array.
      Do 
         read = br.Read(bytesRead, 0, count)
         If index + decoder.GetCharCount(bytesRead, 0, read) - 1 >= chars.Length Then 
            Array.Resize(chars, chars.Length + 50)
         End If   
         written = decoder.GetChars(bytesRead, 0, read, chars, index)
         index += written                          
      Loop While read = count
      br.Close()            
      ' Instantiate a string with the decoded characters.
      Dim str3 As New String(chars, 0, index) 
      Console.WriteLine("Decoded string using UnicodeEncoding.Decoder.GetString()...")
      CompareForEquality(str1, str3) 
   End Sub

   Private Sub CompareForEquality(original As String, decoded As String)
      Dim result As Boolean = original.Equals(decoded)
      Console.WriteLine("original = decoded: {0}", 
                        original.Equals(decoded, StringComparison.Ordinal))
      If Not result Then
         Console.WriteLine("Code points in original string:")
         For Each ch In original
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()

         Console.WriteLine("Code points in decoded string:")
         For Each ch In decoded
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()
      End If
   End Sub
End Module
' The example displays the following output:
'    Created original string...
'    
'    Decoded string using UnicodeEncoding.GetString()...
'    original = decoded: False
'    Code points in original string:
'    0041 0042 0020 0059 005A 0020 0031 0039 0020 D800 DC05 0020 00E4 0055 006E 0069 0063 006F
'    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
'    0020 0073 0020 0062 0308
'    Code points in decoded string:
'    0041 0042 0020 0059 005A 0020 0031 0039 0020 FFFD FFFD 0020 00E4 0055 006E 0069 0063 006F
'    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
'    0020 0073 0020 0062 0308
'    
'    Decoded string using UnicodeEncoding.Decoder.GetString()...
'    original = decoded: True
```

## <a name="choosing-a-fallback-strategy"></a>Auswählen einer Fallbackstrategie

Wenn eine Methode versucht, ein Zeichen zu codieren oder zu decodieren, aber keine Zuordnung vorhanden ist, muss eine Fallbackstrategie implementiert werden. Diese legt fest, wie die fehlende Zuordnung behandelt werden soll. Es gibt drei Arten von Fallbackstrategien: 

* Fallback mit ähnlichen Zeichen

* Ersatzfallback

* Ausnahmefallback

> [!IMPORTANT]
> Bei Codierungsvorgängen treten Probleme am häufigsten dann auf, wenn ein Unicode-Zeichen keiner bestimmten Codepagecodierung zugeordnet werden kann. Zu den am häufigsten auftretenden Problem bei Decodierungsvorgängen gehört es, wenn ungültige Bytefolgen nicht in gültige Unicode-Zeichen übersetzt werden können. Aus diesen Gründen sollten Sie wissen, welche Fallbackstrategien von bestimmten Codierungsobjekten verwendet werden. Nach Möglichkeit sollten Sie die von einem Codierungsobjekt verwendete Fallbackstrategie beim Instanziieren des Objekts festlegen.
 
### <a name="best-fit-fallback"></a>Fallback mit ähnlichen Zeichen

Wenn ein Zeichen nicht über eine genaue Entsprechung in der Zielcodierung verfügt, kann der Encoder versuchen, eine Zuordnung zu einem ähnlichen Zeichen zu erstellen. (Ein Fallback mit ähnlichen Zeichen ist meist vielmehr ein Codierungs- als ein Decodierungsproblem. Es gibt sehr wenige Codepages, die Zeichen enthalten, die in Unicode nicht erfolgreich zugeordnet werden können.) Der Fallback mit ähnlichen Zeichen ist die Standardeinstellung für Codepage- und DBCS-Codierungen, die von der [Encoding.GetEncoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32))-Überladung und der [Encoding.GetEncoding(String)](xref:System.Text.Encoding.GetEncoding(System.String))-Überladung abgerufen werden.

> [!NOTE]
> Theoretisch unterstützen die in .NET bereitgestellten Unicode-Codierungsklassen ([UTF8Encoding](xref:System.Text.UTF8Encoding), [UnicodeEncoding](xref:System.Text.UnicodeEncoding) und [UTF32Encoding](xref:System.Text.UTF32Encoding)) alle Zeichen in jedem Zeichensatz, sodass sie verwendet werden können, um Probleme beim Fallback mit ähnlichen Zeichen zu vermeiden. 
 

Die Strategien mit ähnlichen Zeichen variieren bei den verschiedenen Codepages und sind nicht detailliert dokumentiert. Beispielsweise werden bei einigen Codepages lateinische Zeichen in voller Breite den gängigeren halbbreiten lateinischen Zeichen zugeordnet. Bei anderen Codepages hingegen erfolgt diese Zuordnung nicht. Selbst bei einer aggressiven Strategie mit ähnlichen Zeichen besteht in einigen Codierungen für manche Zeichen keine denkbare Zuordnung. Ein chinesisches ideografisches Zeichen hat z. B. keine angemessene Zuordnung in der Codepage 1252. Im diesem Fall wird eine Ersatzzeichenfolge verwendet. Standardmäßig handelt es sich bei dieser Zeichenfolge um ein einzelnes QUESTION MARK (Fragezeichen, U+003F).

Im folgenden Beispiel wird die Codepage 1252 (Windows-Codepage für westeuropäische Sprachen) verwendet, um eine Zuordnung mit ähnlichen Zeichen und deren Nachteile zu veranschaulichen. Die [Encoding.GetEncoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32))-Methode wird verwendet, um ein Codierungsobjekt für Codepage 1252 abzurufen. Standardmäßig wird eine Zuordnung mit ähnlichen Zeichen für nicht unterstützte Unicode-Zeichen verwendet. Im Beispiel wird eine Zeichenfolge instanziiert, die drei durch Leerzeichen getrennte Nicht-ASCII-Zeichen enthält: CIRCLED LATIN CAPITAL LETTER S (eingekreister lateinischer Großbuchstabe S, U+24C8), SUPERSCRIPT FIVE (hochgestellte Fünf, U+2075) und INFINITY (Unendlichkeit, U+221E). Die Ausgabe im Beispiel zeigt, dass die drei ursprünglichen Nicht-Leerzeichen bei der Codierung der Zeichenfolge durch QUESTION MARK (Fragezeichen, U+003F), DIGIT FIVE (Ziffer Fünf, U+0035) und DIGIT EIGHT (Ziffer Acht, U+0038) ersetzt. Insbesondere DIGIT EIGHT (Ziffer Acht) ist ein ungeeigneter Ersatz für das nicht unterstützte INFINITY-Zeichen (Unendlichkeit), und QUESTION MARK (Fragezeichen) weist darauf hin, dass für das ursprüngliche Zeichen keine Zuordnung verfügbar war.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      // Get an encoding for code page 1252 (Western Europe character set).
      Encoding cp1252 = Encoding.GetEncoding(1252);

      // Define and display a string.
      string str = "\u24c8 \u2075 \u221e";
      Console.WriteLine("Original string: " + str);
      Console.Write("Code points in string: ");
      foreach (var ch in str)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");   

      // Encode a Unicode string.
      Byte[] bytes = cp1252.GetBytes(str);
      Console.Write("Encoded bytes: ");
      foreach (byte byt in bytes)
         Console.Write("{0:X2} ", byt);
      Console.WriteLine("\n");

      // Decode the string.
      string str2 = cp1252.GetString(bytes);
      Console.WriteLine("String round-tripped: {0}", str.Equals(str2));
      if (! str.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
      }
   }
}
// The example displays the following output:
//       Original string: Ⓢ ⁵ ∞
//       Code points in string: 24C8 0020 2075 0020 221E
//       
//       Encoded bytes: 3F 20 35 20 38
//       
//       String round-tripped: False
//       ? 5 8
//       003F 0020 0035 0020 0038
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      ' Get an encoding for code page 1252 (Western Europe character set).
      Dim cp1252 As Encoding = Encoding.GetEncoding(1252)

      ' Define and display a string.
      Dim str As String = String.Format("{0} {1} {2}", ChrW(&h24c8), ChrW(&H2075), ChrW(&h221E))
      Console.WriteLine("Original string: " + str)
      Console.Write("Code points in string: ")
      For Each ch In str
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next
      Console.WriteLine()   
      Console.WriteLine()

      ' Encode a Unicode string.
      Dim bytes() As Byte = cp1252.GetBytes(str)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the string.
      Dim str2 As String = cp1252.GetString(bytes)
      Console.WriteLine("String round-tripped: {0}", str.Equals(str2))
      If Not str.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Original string: Ⓢ ⁵ ∞
'       Code points in string: 24C8 0020 2075 0020 221E
'       
'       Encoded bytes: 3F 20 35 20 38
'       
'       String round-tripped: False
'       ? 5 8
'       003F 0020 0035 0020 0038
```

Die Zuordnung mit ähnlichen Zeichen ist das Standardverhalten für ein [Encoding](xref:System.Text.Encoding)-Objekt, das Unicode-Daten in Codepagedaten codiert. Es gibt ältere Anwendungen, die auf diesem Verhalten basieren. In den meisten neuen Anwendungen sollte dieses Verhalten jedoch aus Sicherheitsgründen vermieden werden. Durch eine Codierung mit ähnlichen Zeichen sollten Anwendungen z. B. keinen Domänennamen ausdrücken.

> [!Note]
> Sie können für eine Codierung auch eine benutzerdefinierte Zuordnung mit einem Fallback mit ähnlichen Zeichen implementieren. Weitere Informationen finden Sie im Abschnitt [Implementieren einer benutzerdefinierten Fallbackstrategie](#implementing-a-custom-fallback-strategy).
 
Wenn der Fallback mit ähnlichen Zeichen die Standardeinstellung für ein Codierungsobjekt ist, können Sie eine andere Fallbackstrategie auswählen, wenn Sie ein [Encoding](xref:System.Text.Encoding)-Objekt durch Aufrufen von [Encoding.GetEncoding(Int32, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)) abrufen oder mit [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) überladen. Der folgende Abschnitt enthält ein Beispiel, in dem jedes Zeichen, das Codepage 1252 nicht zugeordnet werden kann, durch ein Sternchen (\*) ersetzt wird.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding cp1252r = Encoding.GetEncoding(1252, 
                                  new EncoderReplacementFallback("*"),
                                  new DecoderReplacementFallback("*"));

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine();

      byte[] bytes = cp1252r.GetBytes(str1);
      string str2 = cp1252r.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       Round-trip: False
//       * * *
//       002A 0020 002A 0020 002A
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim cp1252r As Encoding = Encoding.GetEncoding(1252, 
                                         New EncoderReplacementFallback("*"),
                                         New DecoderReplacementFallback("*"))

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()

      Dim bytes() As Byte = cp1252r.GetBytes(str1)
      Dim str2 As String = cp1252r.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       Round-trip: False
'       * * *
'       002A 0020 002A 0020 002A
```

### <a name="replacement-fallback"></a>Ersatzfallback

Wenn ein Zeichen nicht über eine genaue Entsprechung im Zielschema verfügt und kein entsprechendes Zeichen für eine Zuordnung vorhanden ist, kann die Anwendung ein Ersatzzeichen oder eine Ersatzzeichenfolge angeben. Dies ist das Standardverhalten für den Unicode-Decoder, der jede 2-Byte-Sequenz ersetzt, die nicht mit REPLACEMENT_CHARACTER (Ersatzzeichen, U+FFFD) decodiert werden kann. Dies ist auch das Standardverhalten der [ASCIIEncoding](xref:System.Text.ASCIIEncoding)-Klasse, die jedes Zeichen, das nicht codiert oder decodiert werden kann, durch ein Fragezeichen ersetzt. Das folgende Beispiel veranschaulicht das Ersetzen von Zeichen für die Unicode-Zeichenfolge aus dem vorherigen Beispiel. Wie die Ausgabe zeigt, wird jedes Zeichen, das nicht in einen ASCII-Bytewert decodiert werden kann, durch 0x3F ersetzt, dem ASCII-Code für ein Fragezeichen.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding enc = Encoding.ASCII;

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");

      // Encode the original string using the ASCII encoder.
      byte[] bytes = enc.GetBytes(str1);
      Console.Write("Encoded bytes: ");
      foreach (var byt in bytes)
         Console.Write("{0:X2} ", byt);
      Console.WriteLine("\n");

      // Decode the ASCII bytes.
      string str2 = enc.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       
//       Encoded bytes: 3F 20 3F 20 3F
//       
//       Round-trip: False
//       ? ? ?
//       003F 0020 003F 0020 003F
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim enc As Encoding = Encoding.Ascii

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()
      Console.WriteLine() 

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = enc.GetBytes(str1)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Dim str2 As String = enc.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       
'       Encoded bytes: 3F 20 3F 20 3F
'       
'       Round-trip: False
'       ? ? ?
'       003F 0020 003F 0020 003F
```

.NET enthält die [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback)-Klasse und die [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback)-Klasse, die eine Ersatzzeichenfolge verwenden, wenn in einem Codierungs- oder Decodierungsvorgang keine genaue Zuordnung für ein Zeichen möglich ist. Standardmäßig ist diese Ersatzzeichenfolge ein Fragezeichen. Sie können jedoch eine Klassenkonstruktorüberladung aufrufen, um eine andere Zeichenfolge auszuwählen. In der Regel handelt es sich bei der Ersatzzeichenfolge um ein einzelnes Zeichen. Dies ist aber nicht erforderlich. Im folgenden Beispiel wird das Verhalten des Encoders für Codepage 1252 geändert, indem ein [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback)-Objekt instanziiert wird, das ein Sternchen (\*) als Ersatzzeichenfolge verwendet.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding cp1252r = Encoding.GetEncoding(1252, 
                                  new EncoderReplacementFallback("*"),
                                  new DecoderReplacementFallback("*"));

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine();

      byte[] bytes = cp1252r.GetBytes(str1);
      string str2 = cp1252r.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       Round-trip: False
//       * * *
//       002A 0020 002A 0020 002A
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim cp1252r As Encoding = Encoding.GetEncoding(1252, 
                                         New EncoderReplacementFallback("*"),
                                         New DecoderReplacementFallback("*"))

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()

      Dim bytes() As Byte = cp1252r.GetBytes(str1)
      Dim str2 As String = cp1252r.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       Round-trip: False
'       * * *
'       002A 0020 002A 0020 002A
```

> [!NOTE]
> Sie können für eine Codierung auch eine Ersatzklasse implementieren. Weitere Informationen finden Sie im Abschnitt [Implementieren einer benutzerdefinierten Fallbackstrategie](#implementing-a-custom-fallback-strategy).
 
Zusätzlich zu QUESTION MARK (Fragezeichen, U+003F) wird in der Regel REPLACEMENT CHARACTER (Unicode-Ersatzzeichen, U+FFFD) als Ersatzzeichenfolge verwendet, insbesondere bei der Decodierung von Bytesequenzen, die nicht erfolgreich in Unicode-Zeichen übersetzt werden können. Allerdings können Sie eine beliebige Ersatzzeichenfolge auswählen, die mehrere Zeichen enthalten kann.

### <a name="exception-fallback"></a>Ausnahmefallback

Anstatt einen Fallback mit ähnlichen Zeichen oder eine Ersatzzeichenfolge bereitzustellen, kann ein Encoder eine [EncoderFallbackException](xref:System.Text.EncoderFallbackException) auslösen, wenn die Codierung eines Satzes von Zeichen nicht möglich ist, und ein Decoder kann eine [DecoderFallbackException](xref:System.Text.DecoderFallbackException) auslösen, wenn ein Bytearray nicht decodiert werden kann. Um eine Ausnahme in Codierungs- und Decodierungsvorgängen auszulösen, übergeben Sie ein [EncoderFallbackException](xref:System.Text.EncoderFallbackException)-Objekt – bzw. ein [DecoderFallbackException](xref:System.Text.DecoderFallbackException)-Objekt – an die [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback))-Methode. Im folgenden Beispiel wird ein Ausnahmefallback mit der ASCIIEncoding-Klasse veranschaulicht.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding enc = Encoding.GetEncoding("us-ascii", 
                                          new EncoderExceptionFallback(), 
                                          new DecoderExceptionFallback());

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");

      // Encode the original string using the ASCII encoder.
      byte[] bytes = {};
      try {
         bytes = enc.GetBytes(str1);
         Console.Write("Encoded bytes: ");
         foreach (var byt in bytes)
            Console.Write("{0:X2} ", byt);

         Console.WriteLine();
      }
      catch (EncoderFallbackException e) {
         Console.Write("Exception: ");
         if (e.IsUnknownSurrogate())
            Console.WriteLine("Unable to encode surrogate pair 0x{0:X4} 0x{1:X3} at index {2}.", 
                              Convert.ToUInt16(e.CharUnknownHigh), 
                              Convert.ToUInt16(e.CharUnknownLow), 
                              e.Index);
         else
            Console.WriteLine("Unable to encode 0x{0:X4} at index {1}.", 
                              Convert.ToUInt16(e.CharUnknown), 
                              e.Index);
         return;
      }
      Console.WriteLine();

      // Decode the ASCII bytes.
      try {
         string str2 = enc.GetString(bytes);
         Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
         if (! str1.Equals(str2)) {
            Console.WriteLine(str2);
            foreach (var ch in str2)
               Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

            Console.WriteLine();
         } 
      }
      catch (DecoderFallbackException e) {
         Console.Write("Unable to decode byte(s) ");
         foreach (byte unknown in e.BytesUnknown)
            Console.Write("0x{0:X2} ");

         Console.WriteLine("at index {0}", e.Index);
      }
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       
//       Exception: Unable to encode 0x24C8 at index 0.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim enc As Encoding = Encoding.GetEncoding("us-ascii", 
                                                 New EncoderExceptionFallback(), 
                                                 New DecoderExceptionFallback())

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()
      Console.WriteLine() 

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = {}
      Try
         bytes = enc.GetBytes(str1)
         Console.Write("Encoded bytes: ")
         For Each byt In bytes
            Console.Write("{0:X2} ", byt)
         Next
         Console.WriteLine()
      Catch e As EncoderFallbackException
         Console.Write("Exception: ")
         If e.IsUnknownSurrogate() Then
            Console.WriteLine("Unable to encode surrogate pair 0x{0:X4} 0x{1:X3} at index {2}.", 
                              Convert.ToUInt16(e.CharUnknownHigh), 
                              Convert.ToUInt16(e.CharUnknownLow), 
                              e.Index)
         Else
            Console.WriteLine("Unable to encode 0x{0:X4} at index {1}.", 
                              Convert.ToUInt16(e.CharUnknown), 
                              e.Index)
         End If                              
         Exit Sub
      End Try
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Try
         Dim str2 As String = enc.GetString(bytes)
         Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
         If Not str1.Equals(str2) Then
            Console.WriteLine(str2)
            For Each ch In str2
               Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
            Next    
            Console.WriteLine()
         End If 
      Catch e As DecoderFallbackException
         Console.Write("Unable to decode byte(s) ")
         For Each unknown As Byte In e.BytesUnknown
            Console.Write("0x{0:X2} ")
         Next
         Console.WriteLine("at index {0}", e.Index)
      End Try
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       
'       Exception: Unable to encode 0x24C8 at index 0.
```

> [!NOTE]
> Sie können für einen Codierungsvorgang auch einen benutzerdefinierten Ausnahmehandler implementieren. Weitere Informationen finden Sie im Abschnitt [Implementieren einer benutzerdefinierten Fallbackstrategie](#implementing-a-custom-fallback-strategy).
 
Das [EncoderFallbackException](xref:System.Text.EncoderFallbackException)- und [DecoderFallbackException](xref:System.Text.DecoderFallbackException)-Objekt stellen die folgenden Informationen über die Bedingung bereit, durch die die Ausnahme ausgelöst wurde: 

* Das [EncoderFallbackException](xref:System.Text.EncoderFallbackException)-Objekt enthält eine [IsUnknownSurrogate](xref:System.Text.EncoderFallbackException.IsUnknownSurrogate)-Methode, die angibt, ob die Zeichen, die nicht codiert werden können, ein unbekanntes Ersatzzeichenpaar darstellen (in diesem Fall gibt die Methode `true` zurück), oder ob sie ein unbekanntes einzelnes Zeichen darstellen (in diesem Fall gibt die Methode `false` zurück). Die Zeichen im Ersatzzeichenpaar sind in den Eigenschaften [EncoderFallbackException.CharUnknownHigh](xref:System.Text.EncoderFallbackException.CharUnknownHigh) und [EncoderFallbackException.CharUnknownLow](xref:System.Text.EncoderFallbackException.CharUnknownLow) verfügbar. Das unbekannte einzelne Zeichen ist in der Eigenschaft [EncoderFallbackException.CharUnknown](xref:System.Text.EncoderFallbackException.CharUnknown) verfügbar. Die [EncoderFallbackException.Index](xref:System.Text.EncoderFallbackException.Index)-Eigenschaft gibt die Position in der Zeichenfolge an, an der das erste Zeichen gefunden wurde, das nicht codiert werden kann.

* Das [DecoderFallbackException](xref:System.Text.DecoderFallbackException)-Objekt enthält eine [BytesUnknown](xref:System.Text.DecoderFallbackException.BytesUnknown)-Eigenschaft, die ein Bytearray zurückgibt, das nicht decodiert werden kann. Die [DecoderFallbackException.Index](xref:System.Text.DecoderFallbackException.Index)-Eigenschaft gibt die Anfangsposition der unbekannten Bytes an.

Obwohl das [EncoderFallbackException](xref:System.Text.EncoderFallbackException)- und [DecoderFallbackException](xref:System.Text.DecoderFallbackException)-Objekt angemessene Diagnoseinformationen zu der Ausnahme bereitstellen, ermöglichen sie keinen Zugriff auf den Codierungs- oder Decodierungspuffer. Daher ist es nicht möglich, innerhalb der Codierungs- oder Decodierungsmethode ungültige Daten zu ersetzen oder zu korrigieren.

## <a name="implementing-a-custom-fallback-strategy"></a>Implementieren einer benutzerdefinierten Fallbackstrategie

Neben der Zuordnung mit ähnlichen Zeichen, die intern von Codepages implementiert wird, beinhaltet .NET die folgenden Klassen für die Implementierung einer Fallbackstrategie:

* Verwenden Sie [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) und [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer), um Zeichen in Codierungsvorgängen zu ersetzen.

* Verwenden Sie [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback) und [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer), um Zeichen in Decodierungsvorgängen zu ersetzen.

* Verwenden Sie [EncoderExceptionFallback](xref:System.Text.EncoderExceptionFallback) und [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) zum Auslösen einer [EncoderFallbackException](xref:System.Text.EncoderFallbackException), wenn ein Zeichen nicht codiert werden kann.

* Verwenden Sie [DecoderExceptionFallback](xref:System.Text.DecoderExceptionFallback) und [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) zum Auslösen einer [DecoderFallbackException](xref:System.Text.DecoderFallbackException), wenn ein Zeichen nicht decodiert werden kann.

Darüber hinaus können Sie eine benutzerdefinierte Lösung implementieren, die den Fallback mit ähnlichen Zeichen, den Ersatzfallback oder den Ausnahmefallback verwendet. Führen Sie hierzu folgende Schritte aus: 

1. Leiten Sie für Codierungsvorgänge eine Klasse von [EncoderFallback](xref:System.Text.EncoderFallback) und für Decodierungsvorgänge eine Klasse von [DecoderFallback](xref:System.Text.DecoderFallback) ab.

2. Leiten Sie für Codierungsvorgänge eine Klasse von [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) und für Decodierungsvorgänge eine Klasse von [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) ab.

3. Wenn die vordefinierte [EncoderFallbackException](xref:System.Text.EncoderFallbackException)- und [DecoderFallbackException](xref:System.Text.DecoderFallbackException)-Klasse nicht Ihren Bedürfnissen entspricht, leiten Sie für den Ausnahmefallback eine Klasse von einem Ausnahmeobjekt ab, z.B. [Exception](xref:System.Exception) oder [ArgumentException](xref:System.ArgumentException).

### <a name="deriving-from-encoderfallback-or-decoderfallback"></a>Ableiten von EncoderFallback oder DecoderFallback

Um eine benutzerdefinierte Fallbacklösung zu implementieren, müssen Sie für Codierungsvorgänge eine Klasse erstellen, die von [EncoderFallback](xref:System.Text.EncoderFallback) erbt. Für Decodierungsvorgänge erstellen Sie eine Klasse, die von [DecoderFallback](xref:System.Text.DecoderFallback) erbt. Instanzen dieser Klassen werden an die [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback))-Methode übergeben und dienen als Vermittler zwischen der Codierungsklasse und der Fallbackimplementierung.

Beim Erstellen einer benutzerdefinierten Fallbacklösung für einen Encoder oder einen Decoder müssen Sie die folgenden Member implementieren:

* Die [EncoderFallback.MaxCharCount](xref:System.Text.EncoderFallback.MaxCharCount)-Eigenschaft oder die [DecoderFallback.MaxCharCount](xref:System.Text.DecoderFallback.MaxCharCount)-Eigenschaft, die die höchstmögliche Anzahl von Zeichen zurückgibt, die der Fallback mit ähnlichen Zeichen, der Ersatz- oder der Ausnahmefallback zurückgeben kann, um ein einzelnes Zeichen zu ersetzen. Für einen benutzerdefinierten Ausnahmefallback ist der Wert Null. 

* Die [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer)- oder [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer)-Methode, die Ihre benutzerdefinierte [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer)- oder [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer)-Implementierung zurückgibt. Die Methode wird vom Encoder aufgerufen, wenn das erste Zeichen erkannt wird, das nicht erfolgreich codiert werden kann, oder vom Decoder, wenn das erste Byte erkannt wird, das nicht erfolgreich decodiert werden kann.

### <a name="deriving-from-encoderfallbackbuffer-or-decoderfallbackbuffer"></a>Ableiten von EncoderFallbackBuffer oder DecoderFallbackBuffer

Um eine benutzerdefinierte Fallbacklösung zu implementieren, müssen Sie für Codierungsvorgänge außerdem eine Klasse erstellen, die von [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) erbt. Für Decodierungsvorgänge erstellen Sie eine Klasse, die von [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) erbt. Instanzen dieser Klassen werden von der `CreateFallbackBuffer`-Methode der [EncoderFallback](xref:System.Text.EncoderFallback)- und [DecoderFallback](xref:System.Text.DecoderFallback)-Klasse zurückgegeben. Die [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer)-Methode wird vom Encoder aufgerufen, wenn das erste Zeichen erkannt wird, das nicht codiert werden kann. Die [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer)-Methode wird vom Decoder aufgerufen, wenn ein oder mehrere Bytes erkannt werden, die nicht decodiert werden können. Die [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer)- und [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer)-Klasse stellen die Fallbackimplementierung bereit. Jede Instanz stellt einen Puffer dar, der die Fallbackzeichen enthält, die das Zeichen ersetzen, das nicht codiert werden kann, bzw. die die Bytesequenz ersetzen, die nicht decodiert werden kann.

Beim Erstellen einer benutzerdefinierten Fallbacklösung für einen Encoder oder einen Decoder müssen Sie die folgenden Member implementieren:

* Die [EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.%23ctor)- oder [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32))-Methode. [EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.Fallback(System.Char,System.Char,System.Int32)) wird vom Encoder aufgerufen, um dem Fallbackpuffer Informationen über das Zeichen bereitzustellen, das nicht codiert werden kann. Da das zu codierende Zeichen möglicherweise ein Ersatzzeichenpaar ist, wird diese Methode überladen. Einer Überladung werden das zu codierende Zeichen und der zugehörige Index in der Zeichenfolge übergeben. Der zweiten Überladung werden das hohe und das niedrige Ersatzzeichen zusammen mit dem Index in der Zeichenfolge übergeben. Die [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32))-Methode wird vom Decoder aufgerufen, um dem Fallbackpuffer Informationen über die Bytes bereitzustellen, die nicht codiert werden können. Dieser Methode wird zusammen mit dem Index des ersten Bytes ein Bytearray übergeben, das nicht decodiert werden kann. Die Fallbackmethode sollte `true` zurückgeben, wenn der Fallbackpuffer ein ähnliches Zeichen oder ein bzw. mehrere Ersatzzeichen bereitstellen kann. Andernfalls sollte sie `false` zurückgeben. Bei einem Ausnahmefallback sollte die Fallbackmethode eine Ausnahme auslösen.

* Die [EncoderFallbackBuffer.GetNextChar](xref:System.Text.EncoderFallbackBuffer.GetNextChar)- oder [DecoderFallbackBuffer.GetNextChar](xref:System.Text.DecoderFallbackBuffer.GetNextChar)-Methode, die wiederholt vom Encoder oder Decoder aufgerufen wird, um das nächste Zeichen aus dem Fallbackpuffer abzurufen. Wenn alle Fallbackzeichen zurückgegeben wurden, sollte die Methode U+0000 zurückgeben. 

* Die [EncoderFallbackBuffer.Remaining](xref:System.Text.EncoderFallbackBuffer.Remaining)- oder [DecoderFallbackBuffer.Remaining](xref:System.Text.DecoderFallbackBuffer.Remaining)-Eigenschaft, die die Anzahl der im Fallbackpuffer verbleibenden Zeichen zurückgibt.

* Die [EncoderFallbackBuffer.MovePrevious](xref:System.Text.EncoderFallbackBuffer.MovePrevious) oder [DecoderFallbackBuffer.MovePrevious](xref:System.Text.DecoderFallbackBuffer.MovePrevious)-Methode, die die aktuelle Position im Fallbackpuffer zum vorhergehenden Zeichen verschiebt.

* Die [EncoderFallbackBuffer.Reset](xref:System.Text.EncoderFallbackBuffer.Reset)- oder [DecoderFallbackBuffer.Reset](xref:System.Text.DecoderFallbackBuffer.Reset)-Methode, die den Fallbackpuffer erneut initialisiert.

Wenn es sich bei der Fallbackimplementierung um einen Fallback mit ähnlichen Zeichen oder einen Ersatzfallback handelt, enthalten die von [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) und [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) abgeleiteten Klassen außerdem zwei private Instanzfelder: die genaue Anzahl von Zeichen im Puffer und den Index des nächsten Zeichens im Puffer, das zurückgegeben werden soll.

### <a name="an-encoderfallback-example"></a>Ein EncoderFallback-Beispiel

In einem früheren Beispiel wurde ein Ersatzfallback verwendet, um Unicode-Zeichen, die keinen ASCII-Zeichen entsprachen, durch ein Sternchen (\*) zu ersetzen. Im folgenden Beispiel wird stattdessen eine benutzerdefinierte Implementierung mit ähnlichen Zeichen verwendet, um eine bessere Zuordnung von Nicht-ASCII-Zeichen zu ermöglichen.

Der folgende Code definiert eine von [EncoderFallback](xref:System.Text.EncoderFallback) abgeleitete Klasse mit dem Namen `CustomMapper`, um die Zuordnung mit ähnlichen Zeichen für Nicht-ASCII-Zeichen zu behandeln. Die `CreateFallbackBuffer`-Methode gibt ein `CustomMapperFallbackBuffer`-Objekt zurück, das die [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer)-Implementierung bereitstellt. Die `CustomMapper`-Klasse verwendet ein [Dictionary&lt;TKey, TValue&gt;](xref:System.Collections.Generic.Dictionary%602)-Objekt, um die Zuordnungen von nicht unterstützten Unicode-Zeichen (Schlüsselwert) und den entsprechenden 8-Bit-Zeichen (die in zwei aufeinander folgenden Bytes in einer 64-Bit-Ganzzahl gespeichert sind) zu speichern. Um dem Fallbackpuffer diese Zuordnung zur Verfügung zu stellen, wird die `CustomMapper`-Instanz als Parameter an den `CustomMapperFallbackBuffer`-Klassenkonstruktor übergeben. Da die längste Zuordnung die Zeichenfolge "INF" für das Unicode-Zeichen U+221E ist, gibt die `MaxCharCount`-Eigenschaft 3 zurück. 

```csharp
public class CustomMapper : EncoderFallback
{
   public string DefaultString;
   internal Dictionary<ushort, ulong> mapping;

   public CustomMapper() : this("*")
   {   
   }

   public CustomMapper(string defaultString)
   {
      this.DefaultString = defaultString;

      // Create table of mappings
      mapping = new Dictionary<ushort, ulong>();
      mapping.Add(0x24C8, 0x53);
      mapping.Add(0x2075, 0x35);
      mapping.Add(0x221E, 0x49004E0046);
   }

   public override EncoderFallbackBuffer CreateFallbackBuffer()
   {
      return new CustomMapperFallbackBuffer(this);
   }

   public override int MaxCharCount
   {
      get { return 3; }
   } 
}
```

```vb
Public Class CustomMapper : Inherits EncoderFallback
   Public DefaultString As String
   Friend mapping As Dictionary(Of UShort, ULong)

   Public Sub New()
      Me.New("?")
   End Sub

   Public Sub New(ByVal defaultString As String)
      Me.DefaultString = defaultString

      ' Create table of mappings
      mapping = New Dictionary(Of UShort, ULong)
      mapping.Add(&H24C8, &H53)
      mapping.Add(&H2075, &H35)
      mapping.Add(&H221E, &H49004E0046)
   End Sub

   Public Overrides Function CreateFallbackBuffer() As System.Text.EncoderFallbackBuffer
      Return New CustomMapperFallbackBuffer(Me)
   End Function

   Public Overrides ReadOnly Property MaxCharCount As Integer
      Get
         Return 3
      End Get
   End Property
End Class
```

Der folgende Code definiert die `CustomMapperFallbackBuffer`-Klasse, die von [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) abgeleitet wird. Das Wörterbuch, das die Zuordnung mit ähnlichen Zeichen enthält und in der `CustomMapper`-Instanz definiert ist, ist über den Klassenkonstruktor verfügbar. Die `Fallback`-Methode gibt `true` zurück, wenn eines der Unicode-Zeichen, das der ASCII-Encoder nicht codieren kann, im Zuordnungswörterbuch definiert ist. Andernfalls wird `false` zurückgegeben. Bei jedem Fallback gibt die private `count`-Variable die Anzahl von Zeichen an, die noch zurückgegeben werden. Die private `index`-Variable gibt die Position im Zeichenfolgenpuffer (`charsToReturn`) des nächsten zurückzugebenden Zeichens an. 

```csharp
public class CustomMapperFallbackBuffer : EncoderFallbackBuffer
{
   int count = -1;                   // Number of characters to return
   int index = -1;                   // Index of character to return
   CustomMapper fb; 
   string charsToReturn; 

   public CustomMapperFallbackBuffer(CustomMapper fallback)
   {
      this.fb = fallback;
   }

   public override bool Fallback(char charUnknownHigh, char charUnknownLow, int index)
   {
      // Do not try to map surrogates to ASCII.
      return false;
   }

   public override bool Fallback(char charUnknown, int index)
   {
      // Return false if there are already characters to map.
      if (count >= 1) return false;

      // Determine number of characters to return.
      charsToReturn = String.Empty;

      ushort key = Convert.ToUInt16(charUnknown);
      if (fb.mapping.ContainsKey(key)) {
         byte[] bytes = BitConverter.GetBytes(fb.mapping[key]);
         int ctr = 0;
         foreach (var byt in bytes) {
            if (byt > 0) {
               ctr++;
               charsToReturn += (char) byt;
            }
         }
         count = ctr;
      }
      else {
         // Return default.
         charsToReturn = fb.DefaultString;
         count = 1;
      }
      this.index = charsToReturn.Length - 1;

      return true;
   }

   public override char GetNextChar()
   {
      // We'll return a character if possible, so subtract from the count of chars to return.
      count--;
      // If count is less than zero, we've returned all characters.
      if (count < 0) 
         return '\u0000';

      this.index--;
      return charsToReturn[this.index + 1];
   }

   public override bool MovePrevious()
   {
      // Original: if count >= -1 and pos >= 0
      if (count >= -1) {
         count++;
         return true;
      }
      else {
         return false;
      }
   }

   public override int Remaining 
   {
      get { return count < 0 ? 0 : count; }
   }

   public override void Reset()
   {
      count = -1;
      index = -1;
   }
}
```

```vb
Public Class CustomMapperFallbackBuffer : Inherits EncoderFallbackBuffer

   Dim count As Integer = -1        ' Number of characters to return
   Dim index As Integer = -1        ' Index of character to return
   Dim fb As CustomMapper
   Dim charsToReturn As String

   Public Sub New(ByVal fallback As CustomMapper)
      MyBase.New()
      Me.fb = fallback
   End Sub

   Public Overloads Overrides Function Fallback(ByVal charUnknownHigh As Char, ByVal charUnknownLow As Char, ByVal index As Integer) As Boolean
      ' Do not try to map surrogates to ASCII.
      Return False
   End Function

   Public Overloads Overrides Function Fallback(ByVal charUnknown As Char, ByVal index As Integer) As Boolean
      ' Return false if there are already characters to map.
      If count >= 1 Then Return False

      ' Determine number of characters to return.
      charsToReturn = String.Empty

      Dim key As UShort = Convert.ToUInt16(charUnknown)
      If fb.mapping.ContainsKey(key) Then
         Dim bytes() As Byte = BitConverter.GetBytes(fb.mapping.Item(key))
         Dim ctr As Integer
         For Each byt In bytes
            If byt > 0 Then
               ctr += 1
               charsToReturn += Chr(byt)
            End If
         Next
         count = ctr
      Else
         ' Return default.
         charsToReturn = fb.DefaultString
         count = 1
      End If
      Me.index = charsToReturn.Length - 1

      Return True
   End Function

   Public Overrides Function GetNextChar() As Char
      ' We'll return a character if possible, so subtract from the count of chars to return.
      count -= 1
      ' If count is less than zero, we've returned all characters.
      If count < 0 Then Return ChrW(0)

      Me.index -= 1
      Return charsToReturn(Me.index + 1)
   End Function

   Public Overrides Function MovePrevious() As Boolean
      ' Original: if count >= -1 and pos >= 0
      If count >= -1 Then
         count += 1
         Return True
      Else
         Return False
      End If
   End Function

   Public Overrides ReadOnly Property Remaining As Integer
      Get
         Return If(count < 0, 0, count)
      End Get
   End Property

   Public Overrides Sub Reset()
      count = -1
      index = -1
   End Sub
End Class
```

Dann instanziiert der folgende Code das `CustomMapper`-Objekt und übergibt eine Instanz davon an die [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback))-Methode. Die Ausgabe zeigt, dass die Fallbackimplementierung mit ähnlichen Zeichen die drei Nicht-ASCII-Zeichen in der ursprünglichen Zeichenfolge erfolgreich behandelt.

```csharp
using System;
using System.Collections.Generic;
using System.Text;

class Program
{
   static void Main()
   {
      Encoding enc = Encoding.GetEncoding("us-ascii", new CustomMapper(), new DecoderExceptionFallback());

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      for (int ctr = 0; ctr <= str1.Length - 1; ctr++) {
         Console.Write("{0} ", Convert.ToUInt16(str1[ctr]).ToString("X4"));
         if (ctr == str1.Length - 1) 
            Console.WriteLine();
      }
      Console.WriteLine();

      // Encode the original string using the ASCII encoder.
      byte[] bytes = enc.GetBytes(str1);
      Console.Write("Encoded bytes: ");
      foreach (var byt in bytes)
         Console.Write("{0:X2} ", byt);

      Console.WriteLine("\n");

      // Decode the ASCII bytes.
      string str2 = enc.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      }
   }
}
```

```vb
Imports System.Text
Imports System.Collections.Generic

Module Module1

   Sub Main()
      Dim enc As Encoding = Encoding.GetEncoding("us-ascii", New CustomMapper(), New DecoderExceptionFallback())

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&H24C8), ChrW(&H2075), ChrW(&H221E))
      Console.WriteLine(str1)
      For ctr As Integer = 0 To str1.Length - 1
         Console.Write("{0} ", Convert.ToUInt16(str1(ctr)).ToString("X4"))
         If ctr = str1.Length - 1 Then Console.WriteLine()
      Next
      Console.WriteLine()

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = enc.GetBytes(str1)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Dim str2 As String = enc.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()
      End If
   End Sub
End Module
```

## <a name="see-also"></a>Siehe auch

[System.Text.Encoder](xref:System.Text.Encoder)

[System.Text.EncoderFallback](xref:System.Text.EncoderFallback)

[System.Text.Decoder](xref:System.Text.Decoder)

[System.Text.DecoderFallback](xref:System.Text.DecoderFallback)

[System.Text.Encoding](xref:System.Text.Encoding)







<!--HONumber=Nov16_HO3-->


