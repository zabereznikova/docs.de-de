---
title: "Gewusst wie: Ansichtsassemblyinhalt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Assemblymanifest, Anzeigen von Informationen"
  - "Ildasm.exe"
  - "MSIL-Disassembler"
  - "Assemblys [.NET Framework], Anzeigen von Inhalten"
  - "Anzeigen von Assemblyinformationen"
  - "MSIL"
  - "Anzeigen von MSIL-Informationen"
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Ansichtsassemblyinhalt
Verwenden Sie [Ildasm.exe \(IL Disassembler\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md), um MSIL\-Informationen \(Microsoft Intermediate Language\) in einer Datei anzuzeigen.  Wenn es sich bei der untersuchten Datei um eine Assembly handelt, können diese Informationen Assemblyattribute sowie Verweise auf andere Assemblys und Module enthalten.  Diese Informationen können Ihnen helfen herauszufinden, ob eine Datei eine Assembly bzw. Teil einer Assembly ist und ob sie Verweise auf andere Module oder Assemblys enthält.  
  
### So zeigen Sie den Inhalt einer Assembly mit Ildasm.exe an  
  
1.  *Assemblyname*\>\-Typ **ildasm** \<an der Eingabeaufforderung.  Zum Beispiel disassembliert der folgende Befehl die `Hello.exe`\-Assembly.  
  
    ```  
    ildasm Hello.exe  
    ```  
  
### So zeigen Sie Assemblymanifestinformationen an  
  
1.  Doppelklicken Sie auf das MANIFEST\-Symbol im Fenster MSIL Disassembler.  
  
## Beispiel  
 Das folgende Beispiel beginnt mit einem einfachen "Hello, World"\-Programm.  Verwenden Sie nach dem Kompilieren des Programms Ildasm.exe, um die Hello.exe\-Assembly zu disassemblieren und das Assemblymanifest anzuzeigen.  
  
 [!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)]
 [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]  
  
 Wenn Sie den Befehl ildasm.exe für die Hello.exe\-Assembly ausführen und auf das Symbol MANIFEST im Fenster IL DASM doppelklicken, wird die folgende Ausgabe erstellt:  
  
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
  
 In der folgenden Tabelle werden alle Direktiven im Assemblymanifest der "Hello.exe"\-Assembly beschrieben, die im Beispiel verwendet wird.  
  
|Direktive|**Beschreibung**|  
|---------------|----------------------|  
|**.assembly extern \<** *Assemblyname* **\>**|Gibt eine andere Assembly an, die Elemente enthält, auf die im aktuellen Modul verwiesen wird \(in diesem Beispiel `mscorlib`\).|  
|**.publickeytoken \<** *Token* **\>**|Gibt das Token des tatsächlichen Schlüssels der Assembly an, auf die verwiesen wird.|  
|**.ver \<** *Versionsnummer* **\>**|Gibt die Versionsnummer der Assembly an, auf die verwiesen wird.|  
|**.assembly \<** *Assemblyname* **\>**|Gibt den Assemblynamen an.|  
|**\>** int32\-Wert  **.hash algorithm \<**|Gibt den verwendeten Hashalgorithmus an.|  
|**.ver \<** *Versionsnummer* **\>**|Gibt die Versionsnummer der Assembly an.|  
|**.module \<** *Dateiname* **\>**|Gibt den Namen der Module an, aus denen die Assembly besteht.  In diesem Beispiel besteht die Assembly aus nur einer Datei.|  
|**.subsystem \<** *Wert* **\>**|Gibt die für das Programm benötigte Anwendungsumgebung an.  In diesem Beispiel zeigt der Wert 3 an, dass das Programm von der Konsole aus ausgeführt wird.|  
|**.corflags**|Momentan ein reserviertes Feld innerhalb der Metadaten.|  
  
 Ein Assemblymanifest kann je nach Inhalt der Assembly mehrere verschiedene Direktiven enthalten.  Eine umfassende Liste der Direktiven im Assemblymanifest finden Sie in der ECMA\-Dokumentation, insbesondere in "Partition II: Metadata Definition and Semantics" und "Partition III: CIL Instruction Set".  Die Dokumentation ist online sein; finden Sie unter [ECMA C\# und Common Language\-Infrastruktur Standards](http://go.microsoft.com/fwlink/?LinkID=99212) auf MSDN und [Standard ECMA\-335 \- Common Language Infrastructure \(CLI\)](http://go.microsoft.com/fwlink/?LinkID=65552) auf der Ecma\-International\-Website.  
  
## Siehe auch  
 [Application Domains and Assemblies](http://msdn.microsoft.com/de-de/433b04ae-4ba8-4849-9dbd-79194f240346)   
 [Gewusst\-wie\-Themen zu Anwendungsdomänen und Assemblys](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)   
 [Ildasm.exe \(IL Disassembler\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)