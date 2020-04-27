---
title: C#-Programmstruktur – Überblick über C#
description: Lernen Sie die grundlegenden Bausteine eines C#-Programms kennen.
ms.date: 02/25/2020
ms.assetid: 984f0314-507f-47a0-af56-9011243f5e65
ms.openlocfilehash: c0a4dcaed7b53a7da7008d6000b3bec2ffe3ee7b
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141014"
---
# <a name="program-structure"></a><span data-ttu-id="a7ee8-103">Programmstruktur</span><span class="sxs-lookup"><span data-stu-id="a7ee8-103">Program Structure</span></span>

<span data-ttu-id="a7ee8-104">Die organisatorischen Schlüsselkonzepte in C# sind: ***Programme***, ***Namespaces***, ***Typen***, ***Member*** und ***Assemblys***.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-104">The key organizational concepts in C# are ***programs***, ***namespaces***, ***types***, ***members***, and ***assemblies***.</span></span> <span data-ttu-id="a7ee8-105">C#-Programme bestehen aus mindestens einer Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-105">C# programs consist of one or more source files.</span></span> <span data-ttu-id="a7ee8-106">Programme deklarieren Typen, die Member enthalten, und können in Namespaces organisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-106">Programs declare types, which contain members and can be organized into namespaces.</span></span> <span data-ttu-id="a7ee8-107">Klassen und Schnittstellen sind Beispiele für Typen.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-107">Classes and interfaces are examples of types.</span></span> <span data-ttu-id="a7ee8-108">Felder, Methoden, Eigenschaften und Ereignisse sind Beispiele für Member.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-108">Fields, methods, properties, and events are examples of members.</span></span> <span data-ttu-id="a7ee8-109">Wenn C#-Programme kompiliert werden, werden sie physisch in Assemblys gepackt.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-109">When C# programs are compiled, they're physically packaged into assemblies.</span></span> <span data-ttu-id="a7ee8-110">Assemblys haben in der Regel die Erweiterung `.exe` oder `.dll`, je nachdem, ob sie ***Anwendungen*** oder ***Bibliotheken*** implementieren.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-110">Assemblies typically have the file extension `.exe` or `.dll`, depending on whether they implement ***applications*** or ***libraries***, respectively.</span></span>

<span data-ttu-id="a7ee8-111">Sie können ein Bibliotheksprojekt namens *acme* mithilfe des `dotnet new`-Befehls erstellen:</span><span class="sxs-lookup"><span data-stu-id="a7ee8-111">You can create a library project named *acme* using the `dotnet new` command:</span></span>

```dotnetcli
dotnet new classlib -o acme
```

<span data-ttu-id="a7ee8-112">In diesem Projekt wird eine Klasse namens `Stack` in einem Namespace namens `Acme.Collections` deklariert:</span><span class="sxs-lookup"><span data-stu-id="a7ee8-112">In that project, declare a class named `Stack` in a namespace called `Acme.Collections`:</span></span>

[!code-csharp[Stack](../../../samples/snippets/csharp/tour/program-structure/program.cs#L1-L34)]

<span data-ttu-id="a7ee8-113">Der vollqualifizierte Name dieser Klasse ist `Acme.Collections.Stack`.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-113">The fully qualified name of this class is `Acme.Collections.Stack`.</span></span> <span data-ttu-id="a7ee8-114">Die Klasse enthält mehrere Member: ein Feld mit dem Namen `top`, zwei Methoden mit dem Namen `Push` und `Pop` sowie eine geschachtelte Klasse mit dem Namen `Entry`.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-114">The class contains several members: a field named `top`, two methods named `Push` and `Pop`, and a nested class named `Entry`.</span></span> <span data-ttu-id="a7ee8-115">Die `Entry`-Klasse enthält weitere drei Member: ein Feld mit dem Namen `next`, ein Feld mit dem Namen `data` und einen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-115">The `Entry` class further contains three members: a field named `next`, a field named `data`, and a constructor.</span></span> <span data-ttu-id="a7ee8-116">Der folgende Befehl kompiliert</span><span class="sxs-lookup"><span data-stu-id="a7ee8-116">The command:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="a7ee8-117">das Beispiel als Bibliothek (Code ohne `Main`-Einstiegspunkt) und erstellt eine Assembly mit dem Namen `acme.dll`.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-117">compiles the example as a library (code without a `Main` entry point) and produces an assembly named `acme.dll`.</span></span>

<span data-ttu-id="a7ee8-118">Assemblys enthalten ausführbaren Code in Form von Zwischensprachenanweisungen (Intermediate Language, IL) und symbolischen Informationen in Form von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-118">Assemblies contain executable code in the form of Intermediate Language (IL) instructions, and symbolic information in the form of metadata.</span></span> <span data-ttu-id="a7ee8-119">Vor der Ausführen konvertiert der JIT-Compiler (Just-In-Time) der .NET Common Language Runtime den IL-Code in einer Assembly in prozessorspezifischen Code.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-119">Before it's executed, the Just-In-Time (JIT) compiler of .NET Common Language Runtime converts the IL code in an assembly to processor-specific code.</span></span>

<span data-ttu-id="a7ee8-120">Da eine Assembly eine selbstbeschreibende Funktionseinheit mit Code und Metadaten ist, besteht in C# keine Notwendigkeit für `#include`-Direktiven und Headerdateien.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-120">Because an assembly is a self-describing unit of functionality containing both code and metadata, there's no need for `#include` directives and header files in C#.</span></span> <span data-ttu-id="a7ee8-121">Die öffentlichen Typen und Member, die in einer bestimmten Assembly enthalten sind, werden einfach durch Verweisen auf die Assembly beim Kompilieren des Programms in einem C#-Programm verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-121">The public types and members contained in a particular assembly are made available in a C# program simply by referencing that assembly when compiling the program.</span></span> <span data-ttu-id="a7ee8-122">Dieses Programm verwendet z.B. die `Acme.Collections.Stack`-Klasse aus der `acme.dll`-Assembly:</span><span class="sxs-lookup"><span data-stu-id="a7ee8-122">For example, this program uses the `Acme.Collections.Stack` class from the `acme.dll` assembly:</span></span>

[!code-csharp[UsingStack](../../../samples/snippets/csharp/tour/program-structure/Program.cs#L38-L52)]

<span data-ttu-id="a7ee8-123">Die *CSPROJ*-Datei für das Projekt des obigen Programms muss einen Verweisknoten für den C#-Compiler enthalten, um Verweise auf die Klassen in der `acme.dll`-Assembly aufzulösen:</span><span class="sxs-lookup"><span data-stu-id="a7ee8-123">The *csproj* file for the preceding program's project must include a reference node for the C# compiler to resolve references to the classes in the `acme.dll` assembly:</span></span>

```xml
  <ItemGroup>
    <ProjectReference Include="..\acme\acme.csproj" />
  </ItemGroup>
```

<span data-ttu-id="a7ee8-124">Nachdem dieser hinzugefügt wurde, erstellt `dotnet build` eine ausführbare Assembly namens `example.exe`, die die Ausgabe erzeugt, wenn sie ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="a7ee8-124">After that addition, `dotnet build` creates an executable assembly named `example.exe`, which, when run, produces the output:</span></span>

```dotnetcli
100
10
1
```

<span data-ttu-id="a7ee8-125">In C# kann der Quelltext eines Programms in verschiedenen Quelldateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-125">C# permits the source text of a program to be stored in several source files.</span></span> <span data-ttu-id="a7ee8-126">Bei der Kompilierung eines C#-Programms mit mehreren Dateien werden alle Quelldateien zusammen verarbeitet, und die Quelldateien können frei aufeinander verweisen – vom Konzept her ist es so, als seien alle Quelldateien vor der Verarbeitung in einer einzigen großen Datei verkettet worden.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-126">When a multi-file C# program is compiled, all of the source files are processed together, and the source files can freely reference each other—conceptually, it is as if all the source files were concatenated into one large file before being processed.</span></span> <span data-ttu-id="a7ee8-127">Vorwärtsdeklarationen sind in C# nie erforderlich, da die Reihenfolge der Deklaration mit wenigen Ausnahmen unbedeutend ist.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-127">Forward declarations are never needed in C# because, with few exceptions, declaration order is insignificant.</span></span> <span data-ttu-id="a7ee8-128">C# beschränkt eine Quelldatei weder auf die Deklaration eines einzigen öffentlichen Typs, noch muss der Name der Quelldatei mit einem in der Quelldatei deklarierten Typ übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a7ee8-128">C# does not limit a source file to declaring only one public type nor does it require the name of the source file to match a type declared in the source file.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a7ee8-129">[Zurück](index.md)
>[Weiter](types-and-variables.md)</span><span class="sxs-lookup"><span data-stu-id="a7ee8-129">[Previous](index.md)
[Next](types-and-variables.md)</span></span>
