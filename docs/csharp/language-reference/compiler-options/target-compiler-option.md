---
title: "/target (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/target"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "target compiler options [C#]"
  - "/target compiler options [C#]"
  - "assemblies [C#], compiling"
  - "-target compiler options [C#]"
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# /target (C# Compiler Options)
Sie haben vier Möglichkeiten, die **\/target**\-Compileroption festzulegen:  
  
 [\/target: appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 So eine EXE\-Datei für [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)]\-App erstellen.  
  
 [\/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)  
 Erstellt eine EXE\-Datei.  
  
 [\/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md)  
 Erstellt eine Codebibliothek.  
  
 [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)  
 Erstellt ein Modul.  
  
 [\/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 Erstellt ein Windows\-Programm.  
  
 [\/target: winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
 Um eine Zwischenwinmdobj\-datei erstellen.  
  
 Sofern Sie nicht **\/target:module** angeben, bewirkt **\/target**, dass ein .NET Framework\-Assemblymanifest in eine Ausgabedatei platziert wird.  Weitere Informationen finden Sie unter [Assemblys in der Common Language Runtime \(CLR\)](../Topic/Assemblies%20in%20the%20Common%20Language%20Runtime.md) sowie unter [Allgemeine Attribute](../Topic/Common%20Attributes%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Das Assemblymanifest wird in der ersten EXE\-Ausgabedatei der Kompilierung platziert oder \(falls keine EXE\-Ausgabedatei vorhanden ist\) in der ersten DLL.  In der folgenden Befehlszeile wird das Manifest beispielsweise in `1.exe` platziert:  
  
```  
csc /out:1.exe t1.cs /out:2.netmodule t2.cs  
```  
  
 Der Compiler erstellt lediglich ein Assemblymanifest pro Kompilierung.  Informationen über alle Dateien in einer Kompilierung werden in das Assemblymanifest geschrieben.  Alle Ausgabedateien mit Ausnahme der mit **\/target:module** erstellten Dateien können ein Assemblymanifest enthalten.  Beim Erstellen von mehreren Ausgabedateien über die Befehlszeile kann nur ein Assemblymanifest generiert werden, und dieses muss in der ersten Ausgabedatei gespeichert werden, die in der Befehlszeile genannt wird.  Unabhängig davon, worum es sich bei der ersten Ausgabedatei handelt \(**\/target:exe**, **\/target:winexe**, **\/target:library** oder **\/target:module**\), müssen alle weiteren in derselben Kompilierung erzeugten Ausgabedateien Module sein \(**\/target:module**\).  
  
 Wenn Sie eine Assembly erstellen, können Sie festlegen, dass der Code vollständig oder teilweise mit dem <xref:System.CLSCompliantAttribute>\-Attribut CLS\-kompatibel ist.  
  
```  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 Weitere Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [\/subsystemversion \(Specify minimum subsystem version\)](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)