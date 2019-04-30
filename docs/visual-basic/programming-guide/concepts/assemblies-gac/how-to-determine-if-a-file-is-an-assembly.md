---
title: 'Vorgehensweise: Bestimmen Sie, ob eine Datei eine Assembly (Visual Basic) ist.'
ms.date: 07/20/2015
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
ms.openlocfilehash: 47ac7f29509af86819006a4394ca661140b95ab0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022167"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a>Vorgehensweise: Bestimmen Sie, ob eine Datei eine Assembly (Visual Basic) ist.
Eine Datei ist nur dann eine Assembly, wenn sie verwaltet wird und einen Assemblyeintrag in ihren Metadaten enthält. Weitere Informationen über Assemblys und Metadaten finden Sie im Thema [Assemblymanifest](../../../../framework/app-domains/assembly-manifest.md).  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>So bestimmen Sie manuell, ob eine Datei eine Assembly ist  
  
1. Starten Sie [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).  
  
2. Laden Sie die Datei, die Sie testen möchten.  
  
3. Wenn **ILDASM** meldet, dass die Datei keine portierbare ausführbare Datei (PE, portable executable) ist, ist es keine Assembly. Weitere Informationen finden Sie im Thema [How to: View Assembly Contents (Vorgehensweise: Anzeigen von Assemblyinhalt)](../../../../framework/app-domains/how-to-view-assembly-contents.md).  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>So bestimmen Sie programmgesteuert, ob eine Datei eine Assembly ist  
  
1. Rufen Sie die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>-Methode auf, und übergeben Sie den vollständigen Dateipfad der Datei, die Sie überprüfen möchten.  
  
2. Wenn eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst wird, ist die Datei keine Assembly.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine DLL getestet, um festzustellen, ob es sich um eine Assembly handelt.  
  
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
- [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)
- [Assemblys und der globale Assemblycache (Visual Basic)](index.md)
