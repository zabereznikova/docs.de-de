---
title: 'Vorgehensweise: Bestimmen Sie, ob eine Datei eine Assembly (Visual Basic) ist.'
ms.date: 07/20/2015
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
ms.openlocfilehash: 47ac7f29509af86819006a4394ca661140b95ab0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316062"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a><span data-ttu-id="5d5f0-102">Vorgehensweise: Bestimmen Sie, ob eine Datei eine Assembly (Visual Basic) ist.</span><span class="sxs-lookup"><span data-stu-id="5d5f0-102">How to: Determine If a File Is an Assembly (Visual Basic)</span></span>
<span data-ttu-id="5d5f0-103">Eine Datei ist nur dann eine Assembly, wenn sie verwaltet wird und einen Assemblyeintrag in ihren Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="5d5f0-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="5d5f0-104">Weitere Informationen über Assemblys und Metadaten finden Sie im Thema [Assemblymanifest](../../../../framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="5d5f0-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](../../../../framework/app-domains/assembly-manifest.md).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="5d5f0-105">So bestimmen Sie manuell, ob eine Datei eine Assembly ist</span><span class="sxs-lookup"><span data-stu-id="5d5f0-105">How to manually determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="5d5f0-106">Starten Sie [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="5d5f0-106">Start the [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2. <span data-ttu-id="5d5f0-107">Laden Sie die Datei, die Sie testen möchten.</span><span class="sxs-lookup"><span data-stu-id="5d5f0-107">Load the file you wish to test.</span></span>  
  
3. <span data-ttu-id="5d5f0-108">Wenn **ILDASM** meldet, dass die Datei keine portierbare ausführbare Datei (PE, portable executable) ist, ist es keine Assembly.</span><span class="sxs-lookup"><span data-stu-id="5d5f0-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="5d5f0-109">Weitere Informationen finden Sie im Thema [How to: View Assembly Contents (Vorgehensweise: Anzeigen von Assemblyinhalt)](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span><span class="sxs-lookup"><span data-stu-id="5d5f0-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="5d5f0-110">So bestimmen Sie programmgesteuert, ob eine Datei eine Assembly ist</span><span class="sxs-lookup"><span data-stu-id="5d5f0-110">How to programmatically determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="5d5f0-111">Rufen Sie die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>-Methode auf, und übergeben Sie den vollständigen Dateipfad der Datei, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="5d5f0-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2. <span data-ttu-id="5d5f0-112">Wenn eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst wird, ist die Datei keine Assembly.</span><span class="sxs-lookup"><span data-stu-id="5d5f0-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d5f0-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5d5f0-113">Example</span></span>  
 <span data-ttu-id="5d5f0-114">In diesem Beispiel wird eine DLL getestet, um festzustellen, ob es sich um eine Assembly handelt.</span><span class="sxs-lookup"><span data-stu-id="5d5f0-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```
  
 <span data-ttu-id="5d5f0-115">Die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>-Methode lädt die Testdatei und gibt sie wieder frei, sobald die Informationen gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="5d5f0-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d5f0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d5f0-116">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="5d5f0-117">Programmierkonzepte</span><span class="sxs-lookup"><span data-stu-id="5d5f0-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="5d5f0-118">Assemblys und der globale Assemblycache (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d5f0-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](index.md)
