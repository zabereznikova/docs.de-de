---
title: 'Vorgehensweise: Bestimmen, ob eine Datei eine Assembly ist'
ms.date: 08/19/2019
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
dev_langs:
- csharp
- vb
ms.openlocfilehash: 1d66c0c166724f195a3cafd9bcbe3c7414c08ebb
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159506"
---
# <a name="how-to-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="73792-102">Vorgehensweise: Bestimmen, ob eine Datei eine Assembly ist</span><span class="sxs-lookup"><span data-stu-id="73792-102">How to: Determine if a file is an assembly</span></span>

<span data-ttu-id="73792-103">Eine Datei ist nur dann eine Assembly, wenn sie verwaltet wird und einen Assemblyeintrag in ihren Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="73792-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="73792-104">Weitere Informationen zu Assemblys und Metadaten finden Sie unter [Assemblymanifest](manifest.md).</span><span class="sxs-lookup"><span data-stu-id="73792-104">For more information on assemblies and metadata, see [Assembly manifest](manifest.md).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="73792-105">So bestimmen Sie manuell, ob eine Datei eine Assembly ist</span><span class="sxs-lookup"><span data-stu-id="73792-105">How to manually determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="73792-106">Starten Sie [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md).</span><span class="sxs-lookup"><span data-stu-id="73792-106">Start the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2. <span data-ttu-id="73792-107">Laden Sie die Datei, die Sie testen möchten.</span><span class="sxs-lookup"><span data-stu-id="73792-107">Load the file you want to test.</span></span>  
  
3. <span data-ttu-id="73792-108">Wenn **ILDASM** meldet, dass die Datei keine portierbare ausführbare Datei (PE, portable executable) ist, ist es keine Assembly.</span><span class="sxs-lookup"><span data-stu-id="73792-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="73792-109">Weitere Informationen finden Sie im Thema [How to: Anzeigen des Assemblyinhalts](view-contents.md).</span><span class="sxs-lookup"><span data-stu-id="73792-109">For more information, see the topic [How to: View assembly contents](view-contents.md).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="73792-110">So bestimmen Sie programmgesteuert, ob eine Datei eine Assembly ist</span><span class="sxs-lookup"><span data-stu-id="73792-110">How to programmatically determine if a file is an assembly</span></span>  
  
1. <span data-ttu-id="73792-111">Rufen Sie die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType>-Methode auf, und übergeben Sie den vollständigen Dateipfad der Datei, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="73792-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> method, passing the full file path and name of the file you are testing.</span></span>  
  
2. <span data-ttu-id="73792-112">Wenn eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst wird, ist die Datei keine Assembly.</span><span class="sxs-lookup"><span data-stu-id="73792-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73792-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="73792-113">Example</span></span>  
<span data-ttu-id="73792-114">In diesem Beispiel wird eine DLL getestet, um festzustellen, ob es sich um eine Assembly handelt.</span><span class="sxs-lookup"><span data-stu-id="73792-114">This example tests a DLL to see if it is an assembly.</span></span>  

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

<span data-ttu-id="73792-115">Die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>-Methode lädt die Testdatei und gibt sie wieder frei, sobald die Informationen gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="73792-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73792-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73792-116">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="73792-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="73792-117">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="73792-118">Programmierkonzepte (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73792-118">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="73792-119">Assemblys in .NET</span><span class="sxs-lookup"><span data-stu-id="73792-119">Assemblies in .NET</span></span>](index.md)
