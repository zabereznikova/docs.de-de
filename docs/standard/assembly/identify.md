---
title: 'Vorgehensweise: Bestimmen, ob eine Datei eine Assembly ist'
ms.date: 08/19/2019
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
dev_langs:
- csharp
- vb
ms.openlocfilehash: 1d66c0c166724f195a3cafd9bcbe3c7414c08ebb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159506"
---
# <a name="how-to-determine-if-a-file-is-an-assembly"></a>Vorgehensweise: Bestimmen, ob eine Datei eine Assembly ist

Eine Datei ist nur dann eine Assembly, wenn sie verwaltet wird und einen Assemblyeintrag in ihren Metadaten enthält. Weitere Informationen zu Assemblys und Metadaten finden Sie unter [Assemblymanifest](manifest.md).  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>So bestimmen Sie manuell, ob eine Datei eine Assembly ist  
  
1. Starten Sie [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md).  
  
2. Laden Sie die Datei, die Sie testen möchten.  
  
3. Wenn **ILDASM** meldet, dass die Datei keine portierbare ausführbare Datei (PE, portable executable) ist, ist es keine Assembly. Weitere Informationen finden Sie im Thema [How to: Anzeigen des Assemblyinhalts](view-contents.md).  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>So bestimmen Sie programmgesteuert, ob eine Datei eine Assembly ist  
  
1. Rufen Sie die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType>-Methode auf, und übergeben Sie den vollständigen Dateipfad der Datei, die Sie überprüfen möchten.  
  
2. Wenn eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst wird, ist die Datei keine Assembly.  
  
## <a name="example"></a>Beispiel  
In diesem Beispiel wird eine DLL getestet, um festzustellen, ob es sich um eine Assembly handelt.  

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

Die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>-Methode lädt die Testdatei und gibt sie wieder frei, sobald die Informationen gelesen wurden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection.AssemblyName>
- [C#-Programmierhandbuch](../../csharp/programming-guide/index.md)
- [Programmierkonzepte (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
- [Assemblys in .NET](index.md)
