---
title: "/target:library (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/dll"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-target compiler options [C#], /target:library"
  - "target compiler options [C#], /target:library"
  - "/target compiler options [C#], /target:library"
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# /target:library (C# Compiler Options)
Die Option **\/target:library** bewirkt, dass der Compiler anstelle einer EXE\-Datei \(ausführbare Datei\) eine DLL\-Datei \(dynamische Bibliothek\) erstellt.  
  
## Syntax  
  
```  
/target:library  
```  
  
## Hinweise  
 Die DLL wird mit der Erweiterung **.dll** erstellt.  
  
 Wenn nicht durch die Option [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) anders angegeben, erhält die Ausgabedatei den Namen der ersten Eingabedatei.  
  
 Wenn Sie diese Option in der Befehlszeile angeben, werden alle Dateien bis zur nächsten Instanz der Option **\/out** oder der Option **\/target:module** zum Erstellen der DLL\-Datei verwendet.  
  
 Beim Erstellen einer DLL\-Datei wird keine [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)\-Methode benötigt.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite von **Anwendung**.  
  
3.  Ändern Sie die Eigenschaft **Ausgabetyp**.  
  
 Informationen über das programmgesteuerte Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Beispiel  
 In diesem Beispiel wird `in.cs` kompiliert und `in.dll` erstellt:  
  
```  
csc /target:library in.cs  
```  
  
## Siehe auch  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)