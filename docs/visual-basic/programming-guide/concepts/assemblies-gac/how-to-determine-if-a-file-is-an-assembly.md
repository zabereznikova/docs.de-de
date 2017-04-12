---
title: 'Gewusst wie: bestimmen, ob eine Datei eine Assembly (Visual Basic) ist | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2e58363369ae4420879310bf09ed89cdd4f5b5cc
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a>Gewusst wie: bestimmen, ob eine Datei eine Assembly (Visual Basic) ist.
Eine Datei ist eine Assembly, wenn sie verwaltet wird und einen Assemblyeintrag in ihren Metadaten enthält. Weitere Informationen über Assemblys und Metadaten finden Sie im Thema [Assemblymanifest](https://msdn.microsoft.com/library/1w45z383).  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>Gewusst wie: manuell ermitteln, ob eine Datei eine Assembly ist  
  
1.  Starten Sie die [Ildasm.exe (IL-Disassembler)](https://msdn.microsoft.com/library/f7dy01k1).  
  
2.  Laden Sie die Datei, die Sie testen möchten.  
  
3.  Wenn **ILDASM** meldet, dass die Datei keiner PE (portable Executable)-Datei ist, und es keine Assembly ist. Weitere Informationen finden Sie im Thema [How to: View Assembly Contents](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709).  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>Gewusst wie: Programmgesteuertes bestimmen, ob eine Datei eine Assembly ist  
  
1.  Rufen Sie die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>-Methode und übergeben den vollständigen Pfad und den Namen der Datei, die Sie testen.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A>  
  
2.  Wenn eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst wird, die Datei ist keine Assembly.</xref:System.BadImageFormatException>  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel testet eine DLL, um festzustellen, ob es sich um eine Assembly ist.  
  
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
  
 Die <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>-Methode lädt die Testdatei und gibt Sie frei, sobald die Daten gelesen wurden.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A>  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName>   
 [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)   
 [Assemblys und dem globalen Assemblycache (Visual Basic)](index.md)
