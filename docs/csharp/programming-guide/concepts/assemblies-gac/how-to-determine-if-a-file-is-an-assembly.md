---
title: 'Vorgehensweise: Bestimmen, ob eine Datei eine Assembly ist (C#) | Microsoft-Dokumentation'
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4de303da9215fb07ecbb6bfff78d18dcd246aad3
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-determine-if-a-file-is-an-assembly-c"></a>Vorgehensweise: Bestimmen, ob eine Datei eine Assembly ist (C#)
Eine Datei ist nur dann eine Assembly, wenn sie verwaltet wird und einen Assemblyeintrag in ihren Metadaten enthält. Weitere Informationen über Assemblys und Metadaten finden Sie im Thema [Assemblymanifest](https://msdn.microsoft.com/library/1w45z383).  
  
### <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>So bestimmen Sie manuell, ob eine Datei eine Assembly ist  
  
1.  Starten Sie [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1).  
  
2.  Laden Sie die Datei, die Sie testen möchten.  
  
3.  Wenn **ILDASM** meldet, dass die Datei keine portierbare ausführbare Datei (PE, portable executable) ist, ist es keine Assembly. Weitere Informationen finden Sie im Thema [Vorgehensweise: Ansichtsassemblyinhalt](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709).  
  
### <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>So bestimmen Sie programmgesteuert, ob eine Datei eine Assembly ist  
  
1.  Rufen Sie die Methode <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> auf, und übergeben Sie den vollständigen Pfad und Namen der Datei, die Sie testen.  
  
2.  Wenn eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst wird, ist die Datei keine Assembly.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine DLL getestet, um festzustellen, ob es sich um eine Assembly handelt.  
  
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
  
 Die Methode <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> lädt die Testdatei und gibt sie frei, sobald die Informationen gelesen wurden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Reflection.AssemblyName>   
 [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)   
 [Assemblies and the Global Assembly Cache (C#) (Assemblys und der globale Assemblycache (C#))](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)
