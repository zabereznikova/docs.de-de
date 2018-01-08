---
title: 'Gewusst wie: Ansichtsassemblyinhalt'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8903f7da1c945ff927ad6dfe0a92650849a36439
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-view-assembly-contents"></a>Gewusst wie: Ansichtsassemblyinhalt
Sie können den [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) verwenden, um Microsoft Intermediate Language-Informationen (MSIL) in einer Datei anzuzeigen. Wenn die untersuchte Datei eine Assembly ist, kann die Information die Attribute der Assembly enthalten sowie Verweise auf andere Module und Assemblys. Dieses Information kann Ihnen helfen, zu bestimmen, ob eine Datei eine Assembly oder Teil einer Assembly ist und ob die Datei über Verweise auf andere Module oder Assemblys verfügt.  
  
### <a name="to-display-the-contents-of-an-assembly-using-ildasmexe"></a>So zeigen Sie die Inhalte einer Assembly mithilfe von „Ildasm.exe“ an  
  
1.  Geben Sie **ildasm** \<*assemblyname*> an der Eingabeaufforderung ein. Beispielsweise disassembliert der folgende Befehl die `Hello.exe`-Assembly.  
  
    ```  
    ildasm Hello.exe  
    ```  
  
### <a name="to-view-assembly-manifest-information"></a>So zeigen Sie Informationen aus dem Assemblymanifest an  
  
1.  Klicken Sie doppelt auf das Symbol MANIFEST im Fenster „MSIL-Disassembler“.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel beginnt mit einem einfachen „Hello, World“-Programm. Nachdem Sie das Programm kompiliert haben, verwenden Sie „Ildasm.exe“, um das „Hello.exe“-Assembly zu disassemblieren, und zeigen Sie das Assemblymanifest an.  
  
 [!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)]
 [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]  
  
 Führen Sie den Befehl „ildasm.exe“ erneut auf dem „Hello.exe“-Assembly aus, und führen Sie eine Doppelklick auf das Symbol MANIFEST in Fenster IL DASM aus, wodurch folgende Ausgabe erzeugt wird:  
  
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
  
 In der folgenden Tabelle wird jede Direktive im Assemblymanifest des „Hello.exe“-Assemblys beschrieben, das im Beispiel verwendet wird.  
  
|Direktive|description|  
|---------------|-----------------|  
|**.assembly extern \<** *assemblyname* **>**|Gibt eine andere Assembly an, die Elemente enthält, auf die vom aktuellen Modul verwiesen wird (in diesem Beispiel `mscorlib`).|  
|**.publickeytoken \<** *token* **>**|Gibt den Token des tatsächlichen Schlüssels der verwiesenen Assembly an.|  
|**.ver \<** *versionsnummer* **>**|Gibt die Versionsnummer der verwiesenen Assembly an.|  
|**.assembly \<** *assemblyname* **>**|Gibt den Assemblynamen an.|  
|**.hash algorithm \<** *int32-wert* **>**|Gibt den verwendeten Hashalgorithmus an.|  
|**.ver \<** *versionsnummer* **>**|Gibt die Versionsnummer der Assembly an.|  
|**.module \<** *dateiname* **>**|Gibt den Namen der Module an, aus die eine Assembly besteht. In diesem Beispiel besteht die Assembly aus nur einer Datei.|  
|**.subsystem \<** *wert* **>**|Gibt die Anwendungsumgebung an, die für das Programm erforderlich ist. In diesem Beispiel gibt der Wert 3 an, dass diese ausführbare Datei von einer Konsole aus ausgeführt wird.|  
|**.corflags**|Derzeit ein reserviertes Feld in den Metadaten.|  
  
 Ein Assemblymanifest kann eine Reihe unterschiedlicher Direktiven enthalten, je nach den Inhalten der Assembly. Eine ausführliche Liste mit den Direktiven im Assemblymanifest finden Sie in der ECMA-Dokumentation, besonders unter „Partition II: Metadata Definition and Semantics“ (Partition II: Matadatendefinition und Semantik) und „Partition III: CIL Instruction Set“ (Partition III: CIL-Anweisungssatz). Die Dokumentation ist online verfügbar. Sie finden sie unter [ECMA C# and Common Language Infrastructure Standards (Standards von ECMA C# und Common Language Infrastructure)](http://go.microsoft.com/fwlink/?LinkID=99212) auf MSDN und [Standard ECMA-335 - Common Language Infrastructure (CLI) (Standard ECMA-335 – Common Language Infrastructure (CLI))](http://go.microsoft.com/fwlink/?LinkID=65552) auf der Ecma International-Website.  
  
## <a name="see-also"></a>Siehe auch  
 [Anwendungsdomänen und Assemblys](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346)  
 [Gewusst-wie-Themen zu Anwendungsdomänen und Assemblys](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 [Ildasm.exe (IL-Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)
