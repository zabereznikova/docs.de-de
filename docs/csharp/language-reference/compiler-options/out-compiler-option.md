---
title: "/out (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/out"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/out compiler option [C#]"
  - "out compiler option [C#]"
  - "-out compiler option [C#]"
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /out (C# Compiler Options)
Die Option **\/out** gibt den Namen der Ausgabedatei an.  
  
## Syntax  
  
```  
/out:filename  
```  
  
## Argumente  
 `filename`  
 Der Name der vom Compiler erstellten Ausgabedatei.  
  
## Hinweise  
 Sie können in der Befehlszeile mehrere Ausgabedateien für die Kompilierung angeben.  Der Compiler erwartet nach der **\/out**\-Option eine oder mehrere Quellcodedateien.  Anschließend werden alle Quellcodedateien in die durch diese **\/out**\-Option festgelegte Ausgabedatei kompiliert.  
  
 Geben Sie den vollständigen Namen und die Erweiterung der zu erstellenden Datei an.  
  
 Wenn Sie den Namen der Ausgabedatei nicht angeben, geschieht Folgendes:  
  
-   Eine EXE\-Datei übernimmt den Namen aus der Quellcodedatei, die die **Main**\-Methode enthält.  
  
-   Ein oder .dll .netmodule nehmen seinen Namen von der ersten Quellcodedatei.  
  
 Eine Quellcodedatei, die für die Kompilierung einer Ausgabedatei verwendet wird, kann nicht in der gleichen Kompilierung zum Kompilieren einer weiteren Ausgabedatei verwendet werden.  
  
 Wenn bei einer Befehlszeilenkompilierung mehrere Ausgabedateien erstellt werden, sollten Sie beachten, dass lediglich eine der Ausgabedateien eine Assembly sein kann und dass es sich dabei nur um die erste \(implizit oder explizit mit **\/out**\) angegebene Ausgabedatei handeln kann.  
  
 Alle als Teil einer Kompilierung erstellten Module werden mit jeder Assembly verknüpft, die auch in dieser Kompilierung erstellt wurde.  Mithilfe von [ildasm.exe](../Topic/Ildasm.exe%20\(IL%20Disassembler\).md) können Sie das Assemblymanifest und somit auch die verknüpften Dateien anzeigen lassen.  
  
 Die Compileroption \/out ist erforderlich, damit eine ausführbare Datei das Ziel einer friend\-Assembly sein kann.  Weitere Informationen finden Sie unter [Friend\-Assemblys](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite von **Anwendung**.  
  
3.  Ändern Sie die Eigenschaft **Assemblyname**.  
  
     So legen Sie diese Compileroption programmgesteuert fest: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> ist eine schreibgeschützte Eigenschaft, die durch eine Kombination aus dem Projekttyp \(ausführbare Datei, Bibliothek usw.\) und dem Assemblynamen bestimmt wird.  Um den Namen der Ausgabedatei festzulegen, ist es erforderlich, eine oder beide Eigenschaften zu ändern.  
  
## Beispiel  
 In diesem Beispiel werden `t.cs` kompiliert sowie die Ausgabedatei `t.exe`, `t2.cs` und die Modulausgabedatei `mymodule.netmodule` erstellt:  
  
```  
csc t.cs /out:mymodule.netmodule /target:module t2.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Friend\-Assemblys](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)