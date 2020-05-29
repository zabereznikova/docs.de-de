---
title: 'Vorgehensweise: Anzeigen des Assemblyinhalts'
description: Mithilfe des IL-Disassemblers können Sie die Attribute und Verweise einer Assembly anzeigen, die auf andere Module und Assemblys verweisen.
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: aed490459252466c6da06e5422b83b1bc20fb885
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380070"
---
# <a name="how-to-view-assembly-contents"></a><span data-ttu-id="278cb-103">Vorgehensweise: Anzeigen des Assemblyinhalts</span><span class="sxs-lookup"><span data-stu-id="278cb-103">How to: View assembly contents</span></span>

<span data-ttu-id="278cb-104">Sie können den [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) verwenden, um Microsoft Intermediate Language-Informationen (MSIL) in einer Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="278cb-104">You can use the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in a file.</span></span> <span data-ttu-id="278cb-105">Wenn die untersuchte Datei eine Assembly ist, kann die Information die Attribute der Assembly enthalten sowie Verweise auf andere Module und Assemblys.</span><span class="sxs-lookup"><span data-stu-id="278cb-105">If the file being examined is an assembly, this information can include the assembly's attributes and references to other modules and assemblies.</span></span> <span data-ttu-id="278cb-106">Diese Informationen sind nützlich, um zu ermitteln, ob eine Datei eine Assembly oder Teil einer Assembly ist und ob die Datei über Verweise auf andere Module oder Assemblys verfügt.</span><span class="sxs-lookup"><span data-stu-id="278cb-106">This information can be helpful in determining whether a file is an assembly or part of an assembly and whether the file has references to other modules or assemblies.</span></span>

<span data-ttu-id="278cb-107">Wenn Sie den Inhalt einer Assembly mithilfe von *Ildasm.exe* anzeigen möchten, geben Sie in einer Eingabeaufforderung **ildasm\<Assemblyname>** ein.</span><span class="sxs-lookup"><span data-stu-id="278cb-107">To display the contents of an assembly using *Ildasm.exe*, enter **ildasm \<assembly name>** at a command prompt.</span></span> <span data-ttu-id="278cb-108">Beispielsweise disassembliert der folgende Befehl die *Hello.exe*-Assembly.</span><span class="sxs-lookup"><span data-stu-id="278cb-108">For example, the following command disassembles the *Hello.exe* assembly.</span></span>

```cmd
ildasm Hello.exe
```

<span data-ttu-id="278cb-109">Klicken Sie doppelt auf das **Manifest**-Symbol im Fenster „MSIL-Disassembler“, um Informationen zum Assemblymanifest anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="278cb-109">To view assembly manifest information, double-click the **Manifest** icon in the MSIL Disassembler window.</span></span>

## <a name="example"></a><span data-ttu-id="278cb-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="278cb-110">Example</span></span>

<span data-ttu-id="278cb-111">Das folgende Beispiel beginnt mit einem einfachen „Hallo Welt“-Programm.</span><span class="sxs-lookup"><span data-stu-id="278cb-111">The following example starts with a basic "Hello World" program.</span></span> <span data-ttu-id="278cb-112">Nachdem Sie das Programm kompiliert haben, verwenden Sie *Ildasm.exe*, um das *Hello.exe*-Assembly zu disassemblieren, und zeigen Sie das Assemblymanifest an.</span><span class="sxs-lookup"><span data-stu-id="278cb-112">After compiling the program, use *Ildasm.exe* to disassemble the *Hello.exe* assembly and view the assembly manifest.</span></span>

```cpp
using namespace System;

class MainApp
{
public:
    static void Main()
    {
        Console::WriteLine("Hello World using C++/CLI!");
    }
};

int main()
{
    MainApp::Main();
}
```

```csharp
using System;

class MainApp
{
    public static void Main()
    {
        Console.WriteLine("Hello World using C#!");
    }
}
```

```vb
Class MainApp
    Public Shared Sub Main()
        Console.WriteLine("Hello World using Visual Basic!")
    End Sub
End Class
```

<span data-ttu-id="278cb-113">Führen Sie den Befehl *ildasm.exe* noch mal in der *Hello.exe*-Assembly aus, und führen Sie eine Doppelklick auf das **Manifest**-Symbol im Fenster „MSIL Disassembler“ durch, wodurch folgende Ausgabe erzeugt wird:</span><span class="sxs-lookup"><span data-stu-id="278cb-113">Running the command *ildasm.exe* on the *Hello.exe* assembly and double-clicking the **Manifest** icon in the MSIL Disassembler window produces the following output:</span></span>

```output
// Metadata version: v4.0.30319
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 4:0:0:0
}
.assembly Hello
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .custom instance void [mscorlib]System.Runtime.CompilerServices.RuntimeCompatibilityAttribute::.ctor() = ( 01 00 01 00 54 02 16 57 72 61 70 4E 6F 6E 45 78   // ....T..WrapNonEx
                                                                                                             63 65 70 74 69 6F 6E 54 68 72 6F 77 73 01 )       // ceptionThrows.
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module Hello.exe
// MVID: {7C2770DB-1594-438D-BAE5-98764C39CCCA}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x00600000
```

<span data-ttu-id="278cb-114">In der folgenden Tabelle wird jede Anweisung im Assemblymanifest der Assembly *Hello.exe* beschrieben, die im Beispiel verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="278cb-114">The following table describes each directive in the assembly manifest of the *Hello.exe* assembly used in the example:</span></span>

|<span data-ttu-id="278cb-115">Anweisung</span><span class="sxs-lookup"><span data-stu-id="278cb-115">Directive</span></span>|<span data-ttu-id="278cb-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="278cb-116">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="278cb-117">**.assembly extern \<assemblyname>**</span><span class="sxs-lookup"><span data-stu-id="278cb-117">**.assembly extern \<assembly name>**</span></span>|<span data-ttu-id="278cb-118">Gibt eine andere Assembly an, die Elemente enthält, auf die vom aktuellen Modul verwiesen wird (in diesem Beispiel `mscorlib`).</span><span class="sxs-lookup"><span data-stu-id="278cb-118">Specifies another assembly that contains items referenced by the current module (in this example, `mscorlib`).</span></span>|
|<span data-ttu-id="278cb-119">**.publickeytoken \<token>**</span><span class="sxs-lookup"><span data-stu-id="278cb-119">**.publickeytoken \<token>**</span></span>|<span data-ttu-id="278cb-120">Gibt den Token des tatsächlichen Schlüssels der verwiesenen Assembly an.</span><span class="sxs-lookup"><span data-stu-id="278cb-120">Specifies the token of the actual key of the referenced assembly.</span></span>|
|<span data-ttu-id="278cb-121">**.ver \<versionsnummer>**</span><span class="sxs-lookup"><span data-stu-id="278cb-121">**.ver \<version number>**</span></span>|<span data-ttu-id="278cb-122">Gibt die Versionsnummer der verwiesenen Assembly an.</span><span class="sxs-lookup"><span data-stu-id="278cb-122">Specifies the version number of the referenced assembly.</span></span>|
|<span data-ttu-id="278cb-123">**.assembly \<assemblyname>**</span><span class="sxs-lookup"><span data-stu-id="278cb-123">**.assembly \<assembly name>**</span></span>|<span data-ttu-id="278cb-124">Gibt den Assemblynamen an.</span><span class="sxs-lookup"><span data-stu-id="278cb-124">Specifies the assembly name.</span></span>|
|<span data-ttu-id="278cb-125">**.hash algorithm \<int32-wert>**</span><span class="sxs-lookup"><span data-stu-id="278cb-125">**.hash algorithm \<int32 value>**</span></span>|<span data-ttu-id="278cb-126">Gibt den verwendeten Hashalgorithmus an.</span><span class="sxs-lookup"><span data-stu-id="278cb-126">Specifies the hash algorithm used.</span></span>|
|<span data-ttu-id="278cb-127">**.ver \<versionsnummer>**</span><span class="sxs-lookup"><span data-stu-id="278cb-127">**.ver \<version number>**</span></span>|<span data-ttu-id="278cb-128">Gibt die Versionsnummer der Assembly an.</span><span class="sxs-lookup"><span data-stu-id="278cb-128">Specifies the version number of the assembly.</span></span>|
|<span data-ttu-id="278cb-129">**.module \<dateiname>**</span><span class="sxs-lookup"><span data-stu-id="278cb-129">**.module \<file name>**</span></span>|<span data-ttu-id="278cb-130">Gibt den Namen der Module an, aus die eine Assembly besteht.</span><span class="sxs-lookup"><span data-stu-id="278cb-130">Specifies the name of the modules that make up the assembly.</span></span> <span data-ttu-id="278cb-131">In diesem Beispiel besteht die Assembly aus nur einer Datei.</span><span class="sxs-lookup"><span data-stu-id="278cb-131">In this example, the assembly consists of only one file.</span></span>|
|<span data-ttu-id="278cb-132">**.subsystem \<wert>**</span><span class="sxs-lookup"><span data-stu-id="278cb-132">**.subsystem \<value>**</span></span>|<span data-ttu-id="278cb-133">Gibt die Anwendungsumgebung an, die für das Programm erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="278cb-133">Specifies the application environment required for the program.</span></span> <span data-ttu-id="278cb-134">In diesem Beispiel gibt der Wert 3 an, dass diese ausführbare Datei von einer Konsole aus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="278cb-134">In this example, the value 3 indicates that this executable is run from a console.</span></span>|
|<span data-ttu-id="278cb-135">**.corflags**</span><span class="sxs-lookup"><span data-stu-id="278cb-135">**.corflags**</span></span>|<span data-ttu-id="278cb-136">Derzeit ein reserviertes Feld in den Metadaten.</span><span class="sxs-lookup"><span data-stu-id="278cb-136">Currently a reserved field in the metadata.</span></span>|

<span data-ttu-id="278cb-137">Ein Assemblymanifest kann eine Reihe unterschiedlicher Direktiven enthalten, je nach den Inhalten der Assembly.</span><span class="sxs-lookup"><span data-stu-id="278cb-137">An assembly manifest can contain a number of different directives, depending on the contents of the assembly.</span></span> <span data-ttu-id="278cb-138">Eine ausführliche Liste mit den Anweisungen im Assemblymanifest finden Sie in der ECMA-Dokumentation, insbesondere unter „Partition II: Metadatendefinition und Semantik) und „Partition III: CIL Instruction Set“ (CIL-Anweisungen):</span><span class="sxs-lookup"><span data-stu-id="278cb-138">For an extensive list of the directives in the assembly manifest, see the Ecma documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set":</span></span>

- [<span data-ttu-id="278cb-139">Standards von ECMA C# und der Common Language Infrastructure</span><span class="sxs-lookup"><span data-stu-id="278cb-139">ECMA C# and Common Language Infrastructure standards</span></span>](../components.md#applicable-standards)
- [<span data-ttu-id="278cb-140">ECMA-335-Standard: Common Language Infrastructure-Standard (CLI)</span><span class="sxs-lookup"><span data-stu-id="278cb-140">Standard ECMA-335 - Common Language Infrastructure (CLI)</span></span>](http://www.ecma-international.org/publications/standards/Ecma-335.htm)

## <a name="see-also"></a><span data-ttu-id="278cb-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="278cb-141">See also</span></span>

- [<span data-ttu-id="278cb-142">Anwendungsdomänen und Assemblys</span><span class="sxs-lookup"><span data-stu-id="278cb-142">Application domains and assemblies</span></span>](../../framework/app-domains/application-domains.md#application-domains-and-assemblies)
- [<span data-ttu-id="278cb-143">Artikel zur Vorgehensweise zu Anwendungsdomänen und Assemblys</span><span class="sxs-lookup"><span data-stu-id="278cb-143">Application domains and assemblies how-to topics</span></span>](../../framework/app-domains/application-domains-and-assemblies-how-to-topics.md)
- [<span data-ttu-id="278cb-144">Ildasm.exe (IL-Disassembler)</span><span class="sxs-lookup"><span data-stu-id="278cb-144">Ildasm.exe (IL Disassembler)</span></span>](../../framework/tools/ildasm-exe-il-disassembler.md)
