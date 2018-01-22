---
title: "Zeichenfolgeninterpolation – C#"
description: Erfahren Sie, wie die Zeichenfolgeninterpolation in C# 6 funktioniert.
keywords: .NET, .NET Core, C#, Zeichenfolge
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8806f6b-3ac7-4ee6-9b3e-c524d5301ae9
ms.openlocfilehash: b6b3ce53a08cfacfacb19266b0be216a40633352
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="string-interpolation-in-c"></a>Zeichenfolgeninterpolation in C# #

Die Zeichenfolgeninterpolation ermöglicht, dass Platzhalter in einer Zeichenfolge durch den Wert einer Zeichenfolgenvariablen ersetzt werden. Vor C# 6 wurde dies mit `System.String.Format` realisiert. Dies funktioniert gut, aber da dabei nummerierte Platzhalter verwendet werden, kann es schwieriger zu lesen und detaillierter sein.

In anderen Programmiersprachen ist die Zeichenfolgeninterpolation bereits seit einer Weile integriert. Zum Beispiel in PHP:

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

In C# 6 haben wir nun diesen Zeichenfolgeninterpolations-Stil. Sie können ein `$` vor einer Zeichenfolge verwenden, um anzugeben, dass sie Variablen/Ausdrücke durch deren Werte ersetzen soll.

## <a name="prerequisites"></a>Erforderliche Komponenten
Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten. Die Installationsanweisungen finden Sie auf der Seite [.NET Core](https://www.microsoft.com/net/core).
Sie können diese Anwendung unter Windows, Ubuntu Linux, macOS oder in einem Docker-Container ausführen. Sie müssen Ihren bevorzugten Code-Editor installieren. In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor. Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.

## <a name="create-the-application"></a>Erstellen der Anwendung

Nachdem Sie alle Tools installiert haben, erstellen Sie eine neue .NET Core-Anwendung. Um den Befehlszeilengenerator zu verwenden, erstellen Sie ein Verzeichnis für Ihr Projekt, z.B. `interpolated`, und führen den folgenden Befehl in Ihrer bevorzugten Shell aus:

```
dotnet new console
```

Dieser Befehl erstellt ein neues .NET Core-Projekt mit einer Projektdatei, *interpolated.csproj*, und einer Quellcodedatei, *Program.cs*. Sie müssen `dotnet restore` ausführen, um die Abhängigkeiten wiederherzustellen, die zum Kompilieren dieses Projekts erforderlich sind.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Verwenden Sie zum Ausführen des Programms `dotnet run`. Es sollte „Hello, World“ auf der Konsole ausgegeben werden.



## <a name="intro-to-string-interpolation"></a>Einführung zur Zeichenfolgeninterpolation

Mit `System.String.Format` geben Sie „Platzhalter“ in einer Zeichenfolge an, die von den Parametern ersetzt werden, die auf die Zeichenfolge folgen. Zum Beispiel:

[!code-csharp[String.Format example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]  

Damit wird „My name is Matt Groves“ ausgegeben.

In C# 6 definieren Sie eine interpolierte Zeichenfolge, indem Sie ihr das `$`-Symbol voranstellen und dann die Variablen direkt in der Zeichenfolge verwenden, anstatt `String.Format` zu verwenden. Zum Beispiel:

[!code-csharp[Interpolation example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]  

Sie müssen nicht einfach Variablen verwenden. Sie können jeden Ausdruck innerhalb der Klammern verwenden. Zum Beispiel:

[!code-csharp[Interpolation expression example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]  

Die Ausgabe wäre:

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

## <a name="how-string-interpolation-works"></a>So funktioniert die Zeichenfolgeninterpolation

Hinter den Kulissen wird diese Zeichenfolgeninterpolations-Syntax vom Compiler in String.Format übersetzt. So können Sie [das Gleiche tun, was Sie bereits mit String.Format getan haben](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx).

Sie können z.B. auffüllen und numerisch formatieren:

[!code-csharp[Interpolation formatting example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]  

Der obige Code würde folgende Ausgabe ergeben:

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

Wenn der Name einer Variablen nicht gefunden wird, wird ein Kompilierzeitfehler generiert.

Zum Beispiel:

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

Wenn Sie dies kompilieren, erhalten Sie Fehlermeldungen:
 
* `Cannot use local variable 'adj' before it is declared` – die `adj`-Variable wurde erst *nach* der interpolierten Zeichenfolge deklariert.
* `The name 'otheranimal' does not exist in the current context` – eine Variable namens `otheranimal` wurde nie deklariert

## <a name="localization-and-internationalization"></a>Lokalisierung und Internationalisierung

Eine interpolierte Zeichenfolge unterstützt `IFormattable` und `FormattableString`, was für die Internationalisierung nützlich sein kann.

Standardmäßig verwendet eine interpolierte Zeichenfolge die aktuelle Kultur. Um eine andere Kultur zu verwenden, können Sie sie in `IFormattable` umwandeln.

Zum Beispiel:

[!code-csharp[Interpolation internationalization example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]  

## <a name="conclusion"></a>Schlussbemerkung 

In diesem Tutorial haben Sie gelernt, wie Sie Zeichenfolgeninterpolations-Funktionen von C# 6 verwenden. Es ist im Grunde eine präzisere Methode, einfache `String.Format`-Anweisungen zu schreiben, mit einigen Einschränkungen für fortgeschrittenere Verwendungen.
