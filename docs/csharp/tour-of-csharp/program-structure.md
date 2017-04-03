---
title: "C#-Programmstruktur | Überblick über C#"
description: Lernen Sie die grundlegenden Bausteine eines C#-Programms kennen.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9ef19d7fa2164990edd5e27651d28aa085ec90ad
ms.lasthandoff: 03/13/2017

---

# <a name="program-structure"></a>Programmstruktur

Die organisatorischen Schlüsselkonzepte in C# sind: ***Programme***, ***Namespaces***, ***Typen***, ***Member*** und ***Assemblys***. C#-Programme bestehen aus mindestens einer Quelldatei. Programme deklarieren Typen, die Member enthalten, und können in Namespaces organisiert werden. Klassen und Schnittstellen sind Beispiele für Typen. Felder, Methoden, Eigenschaften und Ereignisse sind Beispiele für Member. Wenn C#-Programme kompiliert werden, werden sie physisch in Assemblys verpackt. Assemblys haben in der Regel die Erweiterung `.exe` oder `.dll`, je nachdem, ob sie ***Anwendungen*** oder ***Bibliotheken*** implementieren.

Das Beispiel deklariert eine Klasse namens `Stack` in einem Namespace namens `Acme.Collections`:

[!code-csharp[Stapel](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

Der vollqualifizierte Name dieser Klasse ist `Acme.Collections.Stack`. Die Klasse enthält mehrere Member: ein Feld mit dem Namen `top`, zwei Methoden mit dem Namen `Push` und `Pop` sowie eine geschachtelte Klasse mit dem Namen `Entry`. Die `Entry`-Klasse enthält weitere drei Member: ein Feld mit dem Namen `next`, ein Feld mit dem Namen `data` und einen Konstruktor. Vorausgesetzt, dass der Quellcode des Beispiels in der Datei `acme.cs` gespeichert wird, kompiliert die Befehlszeile

```
csc /t:library acme.cs
```

das Beispiel als Bibliothek (Code ohne `Main`-Einstiegspunkt) und erstellt eine Assembly mit dem Namen `acme.dll`.

> [!IMPORTANT]
> Die Beispiele oben verwenden `csc` als C#-Befehlszeilencompiler. Dieser Compiler ist eine ausführbare Windows-Datei. Um C# auf anderen Plattformen zu verwenden, sollten Sie die Tools für .NET Core verwenden. Das .NET Core-Ökosystem verwendet die `dotnet`-CLI zum Verwalten von Befehlszeilenbuilds. Dies schließt das Verwalten von Abhängigkeiten und den Aufruf des C#-Compilers ein. In [diesem Tutorial](../../core/tutorials/using-with-xplat-cli.md) finden Sie eine vollständige Beschreibung dieser Tools auf den von .NET Core unterstützten Plattformen.

Assemblys enthalten ausführbaren Code in Form von Zwischensprachenanweisungen (Intermediate Language, IL) und symbolischen Informationen in Form von Metadaten. Vor der Ausführung wird der IL-Code in einer Assembly automatisch durch den Just-in-Time-Compiler (JIT) der .NET Common Language Runtime in prozessorspezifischen Code konvertiert.

Da eine Assembly eine selbstbeschreibende Funktionseinheit mit Code und Metadaten ist, besteht in C# keine Notwendigkeit für `#include`-Direktiven und Headerdateien. Die öffentlichen Typen und Member, die in einer bestimmten Assembly enthalten sind, werden einfach durch Verweisen auf die Assembly beim Kompilieren des Programms in einem C#-Programm verfügbar gemacht. Dieses Programm verwendet z.B. die `Acme.Collections.Stack`-Klasse aus der `acme.dll`-Assembly:

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

Wenn das Programm beim Kompilieren von `example.cs` in der Datei `example.cs` gespeichert wird, kann mit der Compileroption „/r“ auf die Assembly „acme.dll“ verwiesen werden:

```
csc /r:acme.dll example.cs
```

So wird eine ausführbare Assembly mit dem Namen `example.exe` erstellt, die bei Ausführung folgende Ausgabe erzeugt:

```
100
10
1
```

In C# kann der Quelltext eines Programms in verschiedenen Quelldateien gespeichert werden. Bei der Kompilierung eines C#-Programms mit mehreren Dateien werden alle Quelldateien zusammen verarbeitet, und die Quelldateien können frei aufeinander verweisen – vom Konzept her ist es so, als seien alle Quelldateien vor der Verarbeitung in einer einzigen großen Datei verkettet worden. Vorwärtsdeklarationen sind in C# nie erforderlich, da die Reihenfolge der Deklaration mit wenigen Ausnahmen unbedeutend ist. C# beschränkt eine Quelldatei weder auf die Deklaration eines einzigen öffentlichen Typs, noch muss der Name der Quelldatei mit einem in der Quelldatei deklarierten Typ übereinstimmen.

>[!div class="step-by-step"]
[Zurück](index.md)
[Weiter](types-and-variables.md)

