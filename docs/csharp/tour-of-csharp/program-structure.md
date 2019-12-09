---
title: C#-Programmstruktur – Überblick über C#
description: Lernen Sie die grundlegenden Bausteine eines C#-Programms kennen.
ms.date: 08/10/2016
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: 5e095e71549ed3eec6c73e6a134fdb5a64fb63c0
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884383"
---
# <a name="program-structure"></a><span data-ttu-id="ebf19-103">Programmstruktur</span><span class="sxs-lookup"><span data-stu-id="ebf19-103">Program Structure</span></span>

<span data-ttu-id="ebf19-104">Die organisatorischen Schlüsselkonzepte in C# sind: ***Programme***, ***Namespaces***, ***Typen***, ***Member*** und ***Assemblys***.</span><span class="sxs-lookup"><span data-stu-id="ebf19-104">The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span> <span data-ttu-id="ebf19-105">C#-Programme bestehen aus mindestens einer Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="ebf19-105">C# programs consist of one or more source files.</span></span> <span data-ttu-id="ebf19-106">Programme deklarieren Typen, die Member enthalten, und können in Namespaces organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ebf19-106">Programs declare types, which contain members and can be organized into namespaces.</span></span> <span data-ttu-id="ebf19-107">Klassen und Schnittstellen sind Beispiele für Typen.</span><span class="sxs-lookup"><span data-stu-id="ebf19-107">Classes and interfaces are examples of types.</span></span> <span data-ttu-id="ebf19-108">Felder, Methoden, Eigenschaften und Ereignisse sind Beispiele für Member.</span><span class="sxs-lookup"><span data-stu-id="ebf19-108">Fields, methods, properties, and events are examples of members.</span></span> <span data-ttu-id="ebf19-109">Wenn C#-Programme kompiliert werden, werden sie physisch in Assemblys verpackt.</span><span class="sxs-lookup"><span data-stu-id="ebf19-109">When C# programs are compiled, they are physically packaged into assemblies.</span></span> <span data-ttu-id="ebf19-110">Assemblys haben in der Regel die Erweiterung `.exe` oder `.dll`, je nachdem, ob sie ***Anwendungen*** oder ***Bibliotheken*** implementieren.</span><span class="sxs-lookup"><span data-stu-id="ebf19-110">Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***, respectively.</span></span>

<span data-ttu-id="ebf19-111">Das Beispiel deklariert eine Klasse namens `Stack` in einem Namespace namens `Acme.Collections`:</span><span class="sxs-lookup"><span data-stu-id="ebf19-111">The example declares a class named `Stack` in a namespace called `Acme.Collections`:</span></span>

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

<span data-ttu-id="ebf19-112">Der vollqualifizierte Name dieser Klasse ist `Acme.Collections.Stack`.</span><span class="sxs-lookup"><span data-stu-id="ebf19-112">The fully qualified name of this class is `Acme.Collections.Stack`.</span></span> <span data-ttu-id="ebf19-113">Die Klasse enthält mehrere Member: ein Feld mit dem Namen `top`, zwei Methoden mit dem Namen `Push` und `Pop` sowie eine geschachtelte Klasse mit dem Namen `Entry`.</span><span class="sxs-lookup"><span data-stu-id="ebf19-113">The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`.</span></span> <span data-ttu-id="ebf19-114">Die `Entry`-Klasse enthält weitere drei Member: ein Feld mit dem Namen `next`, ein Feld mit dem Namen `data` und einen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ebf19-114">The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor.</span></span> <span data-ttu-id="ebf19-115">Vorausgesetzt, dass der Quellcode des Beispiels in der Datei `acme.cs` gespeichert wird, kompiliert die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="ebf19-115">Assuming that the source code of the example is stored in the file `acme.cs`, the command line</span></span>

```console
csc /t:library acme.cs
```

<span data-ttu-id="ebf19-116">das Beispiel als Bibliothek (Code ohne `Main`-Einstiegspunkt) und erstellt eine Assembly mit dem Namen `acme.dll`.</span><span class="sxs-lookup"><span data-stu-id="ebf19-116">compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebf19-117">Die Beispiele oben verwenden `csc` als C#-Befehlszeilencompiler.</span><span class="sxs-lookup"><span data-stu-id="ebf19-117">The examples above use `csc` as the command line C# compiler.</span></span> <span data-ttu-id="ebf19-118">Dieser Compiler ist eine ausführbare Windows-Datei.</span><span class="sxs-lookup"><span data-stu-id="ebf19-118">This compiler is a Windows executable.</span></span> <span data-ttu-id="ebf19-119">Um C# auf anderen Plattformen zu verwenden, sollten Sie die Tools für .NET Core verwenden.</span><span class="sxs-lookup"><span data-stu-id="ebf19-119">To use C# across other platforms, you should use the tools for .NET Core.</span></span> <span data-ttu-id="ebf19-120">Das .NET Core-Ökosystem verwendet die `dotnet`-CLI zum Verwalten von Befehlszeilenbuilds.</span><span class="sxs-lookup"><span data-stu-id="ebf19-120">The .NET Core ecosystem uses the `dotnet` CLI to manage command line builds.</span></span> <span data-ttu-id="ebf19-121">Dies schließt das Verwalten von Abhängigkeiten und den Aufruf des C#-Compilers ein.</span><span class="sxs-lookup"><span data-stu-id="ebf19-121">This includes managing dependencies, and invoking the C# compiler.</span></span> <span data-ttu-id="ebf19-122">In [diesem Tutorial](../../core/tutorials/cli-create-console-app.md) finden Sie eine vollständige Beschreibung dieser Tools auf den von .NET Core unterstützten Plattformen.</span><span class="sxs-lookup"><span data-stu-id="ebf19-122">See [this tutorial](../../core/tutorials/cli-create-console-app.md) for a full description of those tools on the platforms supported by .NET Core.</span></span>

<span data-ttu-id="ebf19-123">Assemblys enthalten ausführbaren Code in Form von Zwischensprachenanweisungen (Intermediate Language, IL) und symbolischen Informationen in Form von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="ebf19-123">Assemblies contain executable code in the form of Intermediate Language (IL) instructions, and symbolic information in the form of metadata.</span></span> <span data-ttu-id="ebf19-124">Vor der Ausführung wird der IL-Code in einer Assembly automatisch durch den Just-in-Time-Compiler (JIT) der .NET Common Language Runtime in prozessorspezifischen Code konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ebf19-124">Before it is executed, the IL code in an assembly is automatically converted to processor-specific code by the Just-In-Time (JIT) compiler of .NET Common Language Runtime.</span></span>

<span data-ttu-id="ebf19-125">Da eine Assembly eine selbstbeschreibende Funktionseinheit mit Code und Metadaten ist, besteht in C# keine Notwendigkeit für `#include`-Direktiven und Headerdateien.</span><span class="sxs-lookup"><span data-stu-id="ebf19-125">Because an assembly is a self-describing unit of functionality containing both code and metadata, there is no need for `#include` directives and header files in C#.</span></span> <span data-ttu-id="ebf19-126">Die öffentlichen Typen und Member, die in einer bestimmten Assembly enthalten sind, werden einfach durch Verweisen auf die Assembly beim Kompilieren des Programms in einem C#-Programm verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="ebf19-126">The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program.</span></span> <span data-ttu-id="ebf19-127">Dieses Programm verwendet z.B. die `Acme.Collections.Stack`-Klasse aus der `acme.dll`-Assembly:</span><span class="sxs-lookup"><span data-stu-id="ebf19-127">For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:</span></span>

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

<span data-ttu-id="ebf19-128">Wenn das Programm beim Kompilieren von `example.cs` in der Datei `example.cs` gespeichert wird, kann mit der Compileroption „/r“ auf die Assembly „acme.dll“ verwiesen werden:</span><span class="sxs-lookup"><span data-stu-id="ebf19-128">If the program is stored in the file `example.cs`, when `example.cs` is compiled, the acme.dll assembly can be referenced using the compiler’s /r option:</span></span>

```console
csc /r:acme.dll example.cs
```

<span data-ttu-id="ebf19-129">So wird eine ausführbare Assembly mit dem Namen `example.exe` erstellt, die bei Ausführung folgende Ausgabe erzeugt:</span><span class="sxs-lookup"><span data-stu-id="ebf19-129">This creates an executable assembly named `example.exe`, which, when run, produces the output:</span></span>

```console
100
10
1
```

<span data-ttu-id="ebf19-130">In C# kann der Quelltext eines Programms in verschiedenen Quelldateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ebf19-130">C# permits the source text of a program to be stored in several source files.</span></span> <span data-ttu-id="ebf19-131">Bei der Kompilierung eines C#-Programms mit mehreren Dateien werden alle Quelldateien zusammen verarbeitet, und die Quelldateien können frei aufeinander verweisen – vom Konzept her ist es so, als seien alle Quelldateien vor der Verarbeitung in einer einzigen großen Datei verkettet worden.</span><span class="sxs-lookup"><span data-stu-id="ebf19-131">When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed.</span></span> <span data-ttu-id="ebf19-132">Vorwärtsdeklarationen sind in C# nie erforderlich, da die Reihenfolge der Deklaration mit wenigen Ausnahmen unbedeutend ist.</span><span class="sxs-lookup"><span data-stu-id="ebf19-132">Forward declarations are never needed in C# because, with very few exceptions, declaration order is insignificant.</span></span> <span data-ttu-id="ebf19-133">C# beschränkt eine Quelldatei weder auf die Deklaration eines einzigen öffentlichen Typs, noch muss der Name der Quelldatei mit einem in der Quelldatei deklarierten Typ übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ebf19-133">C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ebf19-134">[Zurück](index.md)
>[Weiter](types-and-variables.md)</span><span class="sxs-lookup"><span data-stu-id="ebf19-134">[Previous](index.md)
[Next](types-and-variables.md)</span></span>
