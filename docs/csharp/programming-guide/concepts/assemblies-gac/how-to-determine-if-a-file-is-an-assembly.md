---
title: 'Vorgehensweise: Bestimmen, ob eine Datei eine Assembly ist (C#)'
ms.date: 07/20/2015
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
ms.openlocfilehash: e8026ab5fa44b7601e54b5e76ebf9eb434596a07
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340138"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-c"></a><span data-ttu-id="b7aab-102">Vorgehensweise: Bestimmen, ob eine Datei eine Assembly ist (C#)</span><span class="sxs-lookup"><span data-stu-id="b7aab-102">How to: Determine If a File Is an Assembly (C#)</span></span>
<span data-ttu-id="b7aab-103">Eine Datei ist nur dann eine Assembly, wenn sie verwaltet wird und einen Assemblyeintrag in ihren Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="b7aab-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="b7aab-104">Weitere Informationen über Assemblys und Metadaten finden Sie im Thema [Assemblymanifest](../../../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="b7aab-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](../../../../../docs/framework/app-domains/assembly-manifest.md).</span></span>  
  
### <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="b7aab-105">So bestimmen Sie manuell, ob eine Datei eine Assembly ist</span><span class="sxs-lookup"><span data-stu-id="b7aab-105">How to manually determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="b7aab-106">Starten Sie [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="b7aab-106">Start the [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2. <span data-ttu-id="b7aab-107">Laden Sie die Datei, die Sie testen möchten.</span><span class="sxs-lookup"><span data-stu-id="b7aab-107">Load the file you wish to test.</span></span>  
  
3. <span data-ttu-id="b7aab-108">Wenn **ILDASM** meldet, dass die Datei keine portierbare ausführbare Datei (PE, portable executable) ist, ist es keine Assembly.</span><span class="sxs-lookup"><span data-stu-id="b7aab-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="b7aab-109">Weitere Informationen finden Sie im Thema [How to: View Assembly Contents (Vorgehensweise: Anzeigen von Assemblyinhalt)](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span><span class="sxs-lookup"><span data-stu-id="b7aab-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
### <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="b7aab-110">So bestimmen Sie programmgesteuert, ob eine Datei eine Assembly ist</span><span class="sxs-lookup"><span data-stu-id="b7aab-110">How to programmatically determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="b7aab-111">Rufen Sie die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>-Methode auf, und übergeben Sie den vollständigen Dateipfad der Datei, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="b7aab-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2. <span data-ttu-id="b7aab-112">Wenn eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst wird, ist die Datei keine Assembly.</span><span class="sxs-lookup"><span data-stu-id="b7aab-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7aab-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7aab-113">Example</span></span>  
 <span data-ttu-id="b7aab-114">In diesem Beispiel wird eine DLL getestet, um festzustellen, ob es sich um eine Assembly handelt.</span><span class="sxs-lookup"><span data-stu-id="b7aab-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="b7aab-115">Die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>-Methode lädt die Testdatei und gibt sie wieder frei, sobald die Informationen gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="b7aab-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7aab-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7aab-116">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="b7aab-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b7aab-117">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="b7aab-118">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="b7aab-118">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
