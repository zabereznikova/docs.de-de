---
title: 'Vorgehensweise: Bestimmen, ob eine Datei eine Assembly ist (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ee402e28374040ab22173788dce421345b2ef3b5
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-determine-if-a-file-is-an-assembly-c"></a><span data-ttu-id="022c1-102">Vorgehensweise: Bestimmen, ob eine Datei eine Assembly ist (C#)</span><span class="sxs-lookup"><span data-stu-id="022c1-102">How to: Determine If a File Is an Assembly (C#)</span></span>
<span data-ttu-id="022c1-103">Eine Datei ist nur dann eine Assembly, wenn sie verwaltet wird und einen Assemblyeintrag in ihren Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="022c1-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="022c1-104">Weitere Informationen über Assemblys und Metadaten finden Sie im Thema [Assemblymanifest](https://msdn.microsoft.com/library/1w45z383).</span><span class="sxs-lookup"><span data-stu-id="022c1-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](https://msdn.microsoft.com/library/1w45z383).</span></span>  
  
### <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="022c1-105">So bestimmen Sie manuell, ob eine Datei eine Assembly ist</span><span class="sxs-lookup"><span data-stu-id="022c1-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="022c1-106">Starten Sie [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1).</span><span class="sxs-lookup"><span data-stu-id="022c1-106">Start the [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1).</span></span>  
  
2.  <span data-ttu-id="022c1-107">Laden Sie die Datei, die Sie testen möchten.</span><span class="sxs-lookup"><span data-stu-id="022c1-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="022c1-108">Wenn **ILDASM** meldet, dass die Datei keine portierbare ausführbare Datei (PE, portable executable) ist, ist es keine Assembly.</span><span class="sxs-lookup"><span data-stu-id="022c1-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="022c1-109">Weitere Informationen finden Sie im Thema [Vorgehensweise: Ansichtsassemblyinhalt](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span><span class="sxs-lookup"><span data-stu-id="022c1-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
### <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="022c1-110">So bestimmen Sie programmgesteuert, ob eine Datei eine Assembly ist</span><span class="sxs-lookup"><span data-stu-id="022c1-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="022c1-111">Rufen Sie die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>-Methode auf, und übergeben Sie den vollständigen Dateipfad der Datei, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="022c1-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="022c1-112">Wenn eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst wird, ist die Datei keine Assembly.</span><span class="sxs-lookup"><span data-stu-id="022c1-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="022c1-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="022c1-113">Example</span></span>  
 <span data-ttu-id="022c1-114">In diesem Beispiel wird eine DLL getestet, um festzustellen, ob es sich um eine Assembly handelt.</span><span class="sxs-lookup"><span data-stu-id="022c1-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
```  
class TestAssembly  
{  
    static void Main()  
    {  
  
        try  
        {  
            System.Reflection.AssemblyName testAssembly =  
                System.Reflection.AssemblyName.GetAssemblyName(@"C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll");  
  
            System.Console.WriteLine("Yes, the file is an assembly.");  
        }  
  
        catch (System.IO.FileNotFoundException)  
        {  
            System.Console.WriteLine("The file cannot be found.");  
        }  
  
        catch (System.BadImageFormatException)  
        {  
            System.Console.WriteLine("The file is not an assembly.");  
        }  
  
        catch (System.IO.FileLoadException)  
        {  
            System.Console.WriteLine("The assembly has already been loaded.");  
        }  
    }  
}  
/* Output (with .NET Framework 3.5 installed):  
    Yes, the file is an assembly.  
*/  
```  
  
 <span data-ttu-id="022c1-115">Die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>-Methode lädt die Testdatei und gibt sie wieder frei, sobald die Informationen gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="022c1-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="022c1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="022c1-116">See Also</span></span>  
 <span data-ttu-id="022c1-117"><xref:System.Reflection.AssemblyName></span><span class="sxs-lookup"><span data-stu-id="022c1-117"><xref:System.Reflection.AssemblyName></span></span>   
 <span data-ttu-id="022c1-118">[C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="022c1-118">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="022c1-119">Assemblies and the Global Assembly Cache (C#) (Assemblys und der globale Assemblycache (C#))</span><span class="sxs-lookup"><span data-stu-id="022c1-119">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)

