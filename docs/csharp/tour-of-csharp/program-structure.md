---
title: C#-Programmstruktur – Überblick über C#
description: Lernen Sie die grundlegenden Bausteine eines C#-Programms kennen.
ms.date: 02/25/2020
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: c09c11a4dd957b29b2adb7aaa8d68a50f30620b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156830"
---
# <a name="program-structure"></a>Programmstruktur

Die organisatorischen Schlüsselkonzepte in C# sind: ***Programme***, ***Namespaces***, ***Typen***, ***Member*** und ***Assemblys***. C#-Programme bestehen aus mindestens einer Quelldatei. Programme deklarieren Typen, die Member enthalten, und können in Namespaces organisiert werden. Klassen und Schnittstellen sind Beispiele für Typen. Felder, Methoden, Eigenschaften und Ereignisse sind Beispiele für Member. Wenn C#-Programme kompiliert werden, werden sie physisch in Assemblys gepackt. Assemblys haben in der Regel die Erweiterung `.exe` oder `.dll`, je nachdem, ob sie ***Anwendungen*** oder ***Bibliotheken*** implementieren.

Sie können ein Bibliotheksprojekt namens *acme* mithilfe des `dotnet new`-Befehls erstellen:

```console
dotnet new classlib -o acme
```

In diesem Projekt wird eine Klasse namens `Stack` in einem Namespace namens `Acme.Collections` deklariert:

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

Der vollqualifizierte Name dieser Klasse ist `Acme.Collections.Stack`. Die Klasse enthält mehrere Member: ein Feld mit dem Namen `top`, zwei Methoden mit dem Namen `Push` und `Pop` sowie eine geschachtelte Klasse mit dem Namen `Entry`. Die `Entry`-Klasse enthält weitere drei Member: ein Feld mit dem Namen `next`, ein Feld mit dem Namen `data` und einen Konstruktor. Der folgende Befehl kompiliert

```console
dotnet build
```

das Beispiel als Bibliothek (Code ohne `Main`-Einstiegspunkt) und erstellt eine Assembly mit dem Namen `acme.dll`.

Assemblys enthalten ausführbaren Code in Form von Zwischensprachenanweisungen (Intermediate Language, IL) und symbolischen Informationen in Form von Metadaten. Vor der Ausführen konvertiert der JIT-Compiler (Just-In-Time) der .NET Common Language Runtime den IL-Code in einer Assembly in prozessorspezifischen Code.

Da eine Assembly eine selbstbeschreibende Funktionseinheit mit Code und Metadaten ist, besteht in C# keine Notwendigkeit für `#include`-Direktiven und Headerdateien. Die öffentlichen Typen und Member, die in einer bestimmten Assembly enthalten sind, werden einfach durch Verweisen auf die Assembly beim Kompilieren des Programms in einem C#-Programm verfügbar gemacht. Dieses Programm verwendet z.B. die `Acme.Collections.Stack`-Klasse aus der `acme.dll`-Assembly:

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

Die *CSPROJ*-Datei für das Projekt des obigen Programms muss einen Verweisknoten für den C#-Compiler enthalten, um Verweise auf die Klassen in der `acme.dll`-Assembly aufzulösen:

```xml
  <ItemGroup>
    <ProjectReference Include="..\acme\acme.csproj" />
  </ItemGroup>
```

Nachdem dieser hinzugefügt wurde, erstellt `dotnet build` eine ausführbare Assembly namens `example.exe`, die die Ausgabe erzeugt, wenn sie ausgeführt wird:

```console
100
10
1
```

In C# kann der Quelltext eines Programms in verschiedenen Quelldateien gespeichert werden. Bei der Kompilierung eines C#-Programms mit mehreren Dateien werden alle Quelldateien zusammen verarbeitet, und die Quelldateien können frei aufeinander verweisen – vom Konzept her ist es so, als seien alle Quelldateien vor der Verarbeitung in einer einzigen großen Datei verkettet worden. Vorwärtsdeklarationen sind in C# nie erforderlich, da die Reihenfolge der Deklaration mit wenigen Ausnahmen unbedeutend ist. C# beschränkt eine Quelldatei weder auf die Deklaration eines einzigen öffentlichen Typs, noch muss der Name der Quelldatei mit einem in der Quelldatei deklarierten Typ übereinstimmen.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](types-and-variables.md)
