---
title: 'Vorgehensweise: Anzeigen des Assemblyinhalts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5aff7ec439e845c4be8d43ae622fe44fa2c476c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597865"
---
# <a name="how-to-view-assembly-contents"></a><span data-ttu-id="9bbb6-102">Vorgehensweise: Anzeigen des Assemblyinhalts</span><span class="sxs-lookup"><span data-stu-id="9bbb6-102">How to: View Assembly Contents</span></span>
<span data-ttu-id="9bbb6-103">Sie können den [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) verwenden, um Microsoft Intermediate Language-Informationen (MSIL) in einer Datei anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-103">You can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in a file.</span></span> <span data-ttu-id="9bbb6-104">Wenn die untersuchte Datei eine Assembly ist, kann die Information die Attribute der Assembly enthalten sowie Verweise auf andere Module und Assemblys.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-104">If the file being examined is an assembly, this information can include the assembly's attributes, as well as references to other modules and assemblies.</span></span> <span data-ttu-id="9bbb6-105">Dieses Information kann Ihnen helfen, zu bestimmen, ob eine Datei eine Assembly oder Teil einer Assembly ist und ob die Datei über Verweise auf andere Module oder Assemblys verfügt.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-105">This information can be helpful in determining whether a file is an assembly or part of an assembly, and whether the file has references to other modules or assemblies.</span></span>  
  
### <a name="to-display-the-contents-of-an-assembly-using-ildasmexe"></a><span data-ttu-id="9bbb6-106">So zeigen Sie die Inhalte einer Assembly mithilfe von „Ildasm.exe“ an</span><span class="sxs-lookup"><span data-stu-id="9bbb6-106">To display the contents of an assembly using Ildasm.exe</span></span>  
  
1.  <span data-ttu-id="9bbb6-107">Geben Sie **ildasm** \<*assemblyname*> an der Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-107">Type **ildasm** \<*assembly name*> at the command prompt.</span></span> <span data-ttu-id="9bbb6-108">Beispielsweise disassembliert der folgende Befehl die `Hello.exe`-Assembly.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-108">For example, the following command disassembles the `Hello.exe` assembly.</span></span>  
  
    ```  
    ildasm Hello.exe  
    ```  
  
### <a name="to-view-assembly-manifest-information"></a><span data-ttu-id="9bbb6-109">So zeigen Sie Informationen aus dem Assemblymanifest an</span><span class="sxs-lookup"><span data-stu-id="9bbb6-109">To view assembly manifest information</span></span>  
  
1.  <span data-ttu-id="9bbb6-110">Klicken Sie doppelt auf das Symbol MANIFEST im Fenster „MSIL-Disassembler“.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-110">Double-click the MANIFEST icon in the MSIL Disassembler window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bbb6-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bbb6-111">Example</span></span>  
 <span data-ttu-id="9bbb6-112">Das folgende Beispiel beginnt mit einem einfachen „Hello, World“-Programm.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-112">The following example starts with a basic "Hello, World" program.</span></span> <span data-ttu-id="9bbb6-113">Nachdem Sie das Programm kompiliert haben, verwenden Sie „Ildasm.exe“, um das „Hello.exe“-Assembly zu disassemblieren, und zeigen Sie das Assemblymanifest an.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-113">After compiling the program, use Ildasm.exe to disassemble the Hello.exe assembly and view the assembly manifest.</span></span>  
  
 [!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)]
 [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]  
  
 <span data-ttu-id="9bbb6-114">Führen Sie den Befehl „ildasm.exe“ erneut auf dem „Hello.exe“-Assembly aus, und führen Sie eine Doppelklick auf das Symbol MANIFEST in Fenster IL DASM aus, wodurch folgende Ausgabe erzeugt wird:</span><span class="sxs-lookup"><span data-stu-id="9bbb6-114">Running the command ildasm.exe on the Hello.exe assembly and double-clicking the MANIFEST icon in the IL DASM window produces the following output:</span></span>  
  
```  
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
  
 <span data-ttu-id="9bbb6-115">In der folgenden Tabelle wird jede Direktive im Assemblymanifest des „Hello.exe“-Assemblys beschrieben, das im Beispiel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-115">The following table describes each directive in the assembly manifest of the Hello.exe assembly used in the example.</span></span>  
  
|<span data-ttu-id="9bbb6-116">Anweisung</span><span class="sxs-lookup"><span data-stu-id="9bbb6-116">Directive</span></span>|<span data-ttu-id="9bbb6-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9bbb6-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9bbb6-118">**.assembly extern \<** *assemblyname* **>**</span><span class="sxs-lookup"><span data-stu-id="9bbb6-118">**.assembly extern \<** *assembly name* **>**</span></span>|<span data-ttu-id="9bbb6-119">Gibt eine andere Assembly an, die Elemente enthält, auf die vom aktuellen Modul verwiesen wird (in diesem Beispiel `mscorlib`).</span><span class="sxs-lookup"><span data-stu-id="9bbb6-119">Specifies another assembly that contains items referenced by the current module (in this example, `mscorlib`).</span></span>|  
|<span data-ttu-id="9bbb6-120">**.publickeytoken \<** *token* **>**</span><span class="sxs-lookup"><span data-stu-id="9bbb6-120">**.publickeytoken \<** *token* **>**</span></span>|<span data-ttu-id="9bbb6-121">Gibt den Token des tatsächlichen Schlüssels der verwiesenen Assembly an.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-121">Specifies the token of the actual key of the referenced assembly.</span></span>|  
|<span data-ttu-id="9bbb6-122">**.ver \<** *versionsnummer* **>**</span><span class="sxs-lookup"><span data-stu-id="9bbb6-122">**.ver \<** *version number* **>**</span></span>|<span data-ttu-id="9bbb6-123">Gibt die Versionsnummer der verwiesenen Assembly an.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-123">Specifies the version number of the referenced assembly.</span></span>|  
|<span data-ttu-id="9bbb6-124">**.assembly \<** *assemblyname* **>**</span><span class="sxs-lookup"><span data-stu-id="9bbb6-124">**.assembly \<** *assembly name* **>**</span></span>|<span data-ttu-id="9bbb6-125">Gibt den Assemblynamen an.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-125">Specifies the assembly name.</span></span>|  
|<span data-ttu-id="9bbb6-126">**.hash algorithm \<** *int32-wert* **>**</span><span class="sxs-lookup"><span data-stu-id="9bbb6-126">**.hash algorithm \<** *int32 value* **>**</span></span>|<span data-ttu-id="9bbb6-127">Gibt den verwendeten Hashalgorithmus an.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-127">Specifies the hash algorithm used.</span></span>|  
|<span data-ttu-id="9bbb6-128">**.ver \<** *versionsnummer* **>**</span><span class="sxs-lookup"><span data-stu-id="9bbb6-128">**.ver \<** *version number* **>**</span></span>|<span data-ttu-id="9bbb6-129">Gibt die Versionsnummer der Assembly an.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-129">Specifies the version number of the assembly.</span></span>|  
|<span data-ttu-id="9bbb6-130">**.module \<** *dateiname* **>**</span><span class="sxs-lookup"><span data-stu-id="9bbb6-130">**.module \<** *file name* **>**</span></span>|<span data-ttu-id="9bbb6-131">Gibt den Namen der Module an, aus die eine Assembly besteht.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-131">Specifies the name of the modules that make up the assembly.</span></span> <span data-ttu-id="9bbb6-132">In diesem Beispiel besteht die Assembly aus nur einer Datei.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-132">In this example, the assembly consists of only one file.</span></span>|  
|<span data-ttu-id="9bbb6-133">**.subsystem \<** *wert* **>**</span><span class="sxs-lookup"><span data-stu-id="9bbb6-133">**.subsystem \<** *value* **>**</span></span>|<span data-ttu-id="9bbb6-134">Gibt die Anwendungsumgebung an, die für das Programm erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-134">Specifies the application environment required for the program.</span></span> <span data-ttu-id="9bbb6-135">In diesem Beispiel gibt der Wert 3 an, dass diese ausführbare Datei von einer Konsole aus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-135">In this example, the value 3 indicates that this executable is run from a console.</span></span>|  
|<span data-ttu-id="9bbb6-136">**.corflags**</span><span class="sxs-lookup"><span data-stu-id="9bbb6-136">**.corflags**</span></span>|<span data-ttu-id="9bbb6-137">Derzeit ein reserviertes Feld in den Metadaten.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-137">Currently a reserved field in the metadata.</span></span>|  
  
 <span data-ttu-id="9bbb6-138">Ein Assemblymanifest kann eine Reihe unterschiedlicher Direktiven enthalten, je nach den Inhalten der Assembly.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-138">An assembly manifest can contain a number of different directives, depending on the contents of the assembly.</span></span> <span data-ttu-id="9bbb6-139">Eine ausführliche Liste mit den Anweisungen im Assemblymanifest finden Sie in der ECMA-Dokumentation, besonders unter „Partition II: Metadata Definition and Semantics“ (Partition II: Metadatendefinition und Semantik) und „Partition III: CIL Instruction Set“ (Partition III: CIL-Anweisungen).</span><span class="sxs-lookup"><span data-stu-id="9bbb6-139">For an extensive list of the directives in the assembly manifest, see the ECMA documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="9bbb6-140">Die Dokumentation ist online verfügbar. Sie finden sie unter [ECMA C# and Common Language Infrastructure Standards (Standards von ECMA C# und Common Language Infrastructure)](https://go.microsoft.com/fwlink/?LinkID=99212) auf MSDN und [Standard ECMA-335 - Common Language Infrastructure (CLI) (Standard ECMA-335 – Common Language Infrastructure (CLI))](https://go.microsoft.com/fwlink/?LinkID=65552) auf der Ecma International-Website.</span><span class="sxs-lookup"><span data-stu-id="9bbb6-140">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bbb6-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bbb6-141">See also</span></span>
- [<span data-ttu-id="9bbb6-142">Anwendungsdomänen und Assemblys</span><span class="sxs-lookup"><span data-stu-id="9bbb6-142">Application Domains and Assemblies</span></span>](https://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)
- [<span data-ttu-id="9bbb6-143">Gewusst-wie-Themen zu Anwendungsdomänen und Assemblys</span><span class="sxs-lookup"><span data-stu-id="9bbb6-143">Application Domains and Assemblies How-to Topics</span></span>](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)
- [<span data-ttu-id="9bbb6-144">Ildasm.exe (IL-Disassembler)</span><span class="sxs-lookup"><span data-stu-id="9bbb6-144">Ildasm.exe (IL Disassembler)</span></span>](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)
