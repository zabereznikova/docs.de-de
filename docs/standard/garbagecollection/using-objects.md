---
title: Verwenden von Objekten, die IDisposable implementieren
description: Verwenden von Objekten, die IDisposable implementieren
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/19/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: df780a6e-734e-44b8-9747-9f7783f79e20
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 63ad1233b5eab63670fd51f41f86269f643209a7
ms.lasthandoff: 03/02/2017

---

# <a name="using-objects-that-implement-idisposable"></a>Verwenden von Objekten, die IDisposable implementieren

Der Garbage Collector der Common Language Runtime gibt den Speicher frei, der von nicht verwalteten Objekten verwendet wird. Typen, die nicht verwaltete Ressourcen verwenden, implementieren jedoch die [IDisposable](xref:System.IDisposable)-Schnittstelle, damit dieser nicht verwaltete Speicher freigegeben werden kann. Wenn Sie ein Objekt, das [IDisposable](xref:System.IDisposable) implementiert, nicht mehr verwenden, sollten Sie die [IDisposable.Dispose](xref:System.IDisposable.Dispose)-Implementierung des Objekts aufrufen. Dazu haben Sie zwei Möglichkeiten:

* Verwenden der `using`-Anweisung in C# oder der `Using`-Anweisung in Visual Basic.

* Implementieren eines `try/finally`-Blocks. 

## <a name="the-using-statement"></a>Die using-Anweisung

Die `using`-Anweisung in C# und die `Using`-Anweisung in Visual Basic vereinfachen den Code, den Sie schreiben müssen, um ein Objekt zu erstellen und zu bereinigen. Die `using`-Anweisung ruft eine oder mehrere Ressourcen ab, führt die von Ihnen angegebenen Anweisungen aus und verwirft dann das Objekt automatisch. Die `using`-Anweisung ist jedoch nur hilfreich bei Objekten, die im Bereich der Methode verwendet werden, in der sie erstellt werden. 

Im folgenden Beispiel wird die `using`-Anweisung verwendet, um ein [System.IO.StreamReader](xref:System.IO.StreamReader)-Objekt zu erstellen und freizugeben.

```cs
using System;
using System.IO;

public class Example
{
   public static void Main()
   {
      Char[] buffer = new Char[50];
      using (StreamReader s = new StreamReader("File1.txt")) {
         int charsRead = 0;
         while (s.Peek() != -1) {
            charsRead = s.Read(buffer, 0, buffer.Length);
            //
            // Process characters read.
            //   
         }
         s.Close();    
      }

   }
}
```

```vb
Imports System.IO

Module Example
   Public Sub Main()
      Dim buffer(49) As Char
      Using s As New StreamReader("File1.txt")
         Dim charsRead As Integer
         Do While s.Peek() <> -1
            charsRead = s.Read(buffer, 0, buffer.Length)         
            ' 
            ' Process characters read.
            '
         Loop
         s.Close()
      End Using
   End Sub
End Module
```

Beachten Sie Folgendes: Obwohl die [StreamReader](xref:System.IO.StreamReader)-Klasse die [IDisposable](xref:System.IDisposable)-Schnittstelle implementiert, die angibt, dass sie eine nicht verwaltete Ressource verwendet, wird in dem Beispiel nicht explizit die [StreamReader.Dispose](xref:System.IO.StreamReader.Dispose(System.Boolean))-Methode aufgerufen. Wenn der C#- oder Visual Basic-Compiler die `using`-Anweisung findet, gibt er Zwischensprache (Intermediate Language, IL) aus, die dem folgenden Code entspricht, der explizit einen `try/finally`-Block enthält. 

```cs
using System;
using System.IO;

public class Example
{
   public static void Main()
   {
      Char[] buffer = new Char[50];
      {
         StreamReader s = new StreamReader("File1.txt"); 
         try {
            int charsRead = 0;
            while (s.Peek() != -1) {
               charsRead = s.Read(buffer, 0, buffer.Length);
               //
               // Process characters read.
               //   
            }
            s.Close();
         }
         finally {
            if (s != null)
               ((IDisposable)s).Dispose();     
         }       
      }
   }
}
```

```vb
Imports System.IO

Module Example
   Public Sub Main()
      Dim buffer(49) As Char
''      Dim s As New StreamReader("File1.txt")
With s As New StreamReader("File1.txt")
      Try
         Dim charsRead As Integer
         Do While s.Peek() <> -1
            charsRead = s.Read(buffer, 0, buffer.Length)         
            ' 
            ' Process characters read.
            '
         Loop
         s.Close()
      Finally
         If s IsNot Nothing Then DirectCast(s, IDisposable).Dispose()
      End Try
End With
   End Sub
End Module
```

Mit der `using`-Anweisung in C# können Sie auch mehrere Ressourcen in einer einzigen Anweisung abrufen. Intern entspricht dies geschachtelten using-Anweisungen. Im folgenden Beispiel werden zwei [StreamReader](xref:System.IO.StreamReader)-Objekte instanziiert, um den Inhalt von zwei verschiedenen Dateien zu lesen. 

```cs
using System;
using System.IO;

public class Example
{
   public static void Main()
   {
      Char[] buffer1 = new Char[50], buffer2 = new Char[50];

      using (StreamReader version1 = new StreamReader("file1.txt"),
                          version2 = new StreamReader("file2.txt")) {
         int charsRead1, charsRead2 = 0;
         while (version1.Peek() != -1 && version2.Peek() != -1) {
            charsRead1 = version1.Read(buffer1, 0, buffer1.Length);
            charsRead2 = version2.Read(buffer2, 0, buffer2.Length);
            //
            // Process characters read.
            //
         }
         version1.Close();
         version2.Close();
      }
   }
}
```

## <a name="tryfinally-block"></a>Try-/Finally-Block

Anstatt einen `try/finally`-Block in einer `using`-Anweisung zu umschließen, haben Sie die Möglichkeit, den `try/finally`-Block direkt zu implementieren. Dies kann Ihr persönlicher Codierungsstil sein, oder Sie möchten dies eventuell aus einem der folgenden Gründe durchführen: 

* Um einen `catch`-Block einzufügen, um im `try`-Block ausgelöste Ausnahmen zu behandeln. Andernfalls bleiben alle Ausnahmen, die von der `using`-Anweisung ausgelöst werden, unbehandelt, so wie Ausnahmen, die innerhalb des `using`-Blocks ausgelöst werden, wenn kein `try/catch`-Block vorhanden ist. 

* Um ein Objekt zu instanziieren, das [IDisposable](xref:System.IDisposable) implementiert, dessen Bereich für den Block, in dem es deklariert ist, nicht lokal ist. 

Das folgende Beispiel ähnelt dem vorhergehenden, es wird jedoch ein `try/catch/finally`-Block verwendet, um ein [StreamReader](xref:System.IO.StreamReader)-Objekt zu instanziieren, zu verwenden und zu verwerfen und um alle Ausnahmen zu behandeln, die vom [StreamReader](xref:System.IO.StreamReader)-Konstruktor und dessen [ReadToEnd](xref:System.IO.StreamReader.ReadToEnd)-Methode ausgelöst werden. Beachten Sie, dass der Code im `finally`-Block überprüft, ob das Objekt, das [IDisposable](xref:System.IDisposable) implementiert, nicht `null` ist, bevor die [Dispose](xref:System.IDisposable.Dispose)-Methode aufgerufen wird. Wird dies nicht ausgeführt, kann es zu einer [NullReferenceException](xref:System.NullReferenceException)-Ausnahme zur Laufzeit kommen. 

```cs
using System;
using System.Globalization;
using System.IO;

public class Example
{
   public static void Main()
   {
      StreamReader sr = null;
      try {
         sr = new StreamReader("file1.txt");
         String contents = sr.ReadToEnd();
         sr.Close();
         Console.WriteLine("The file has {0} text elements.", 
                           new StringInfo(contents).LengthInTextElements);    
      }      
      catch (FileNotFoundException) {
         Console.WriteLine("The file cannot be found.");
      }   
      catch (IOException) {
         Console.WriteLine("An I/O error has occurred.");
      }
      catch (OutOfMemoryException) {
         Console.WriteLine("There is insufficient memory to read the file.");   
      }
      finally {
         if (sr != null) sr.Dispose();     
      }
   }
}
```

```vb
Imports System.Globalization
Imports System.IO

Module Example
   Public Sub Main()
      Dim sr As StreamReader = Nothing
      Try 
         sr = New StreamReader("file1.txt")
         Dim contents As String = sr.ReadToEnd()
         sr.Close()
         Console.WriteLine("The file has {0} text elements.", 
                           New StringInfo(contents).LengthInTextElements)    
      Catch e As FileNotFoundException
         Console.WriteLine("The file cannot be found.")
      Catch e As IOException
         Console.WriteLine("An I/O error has occurred.")
      Catch e As OutOfMemoryException
         Console.WriteLine("There is insufficient memory to read the file.")   
      Finally 
         If sr IsNot Nothing Then sr.Dispose()     
      End Try
   End Sub
End Module
```

Sie können dieses grundlegende Muster beibehalten, wenn Sie einen `try/finally`-Block implementieren möchten oder müssen, da Ihre Programmiersprache eine `using`-Anweisung nicht unterstützt, jedoch direkte Aufrufe der [Dispose](xref:System.IDisposable.Dispose)-Methode erlaubt. 

## <a name="see-also"></a>Siehe auch

[Bereinigen von nicht verwalteten Ressourcen](unmanaged.md)



