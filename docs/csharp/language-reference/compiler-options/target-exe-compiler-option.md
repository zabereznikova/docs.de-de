---
title: "/target:exe (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/exe"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "target compiler options [C#], /target:exe"
  - "/target compiler options [C#], /target:exe"
  - "-target compiler options [C#], /target:exe"
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /target:exe (C# Compiler Options)
Die Option **\/target:exe** bewirkt, dass der Compiler eine ausführbare Konsolenanwendung \(**.exe**\) erstellt.  
  
## Syntax  
  
```  
/target:exe  
```  
  
## Hinweise  
 Die Option **\/target:exe** ist standardmäßig aktiviert.  Die ausführbare Datei wird mit der Erweiterung **.exe** erstellt.  
  
 Verwenden Sie [\/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), um ein ausführbares Windows\-Programm zu erstellen.  
  
 Sofern durch die Option [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) nicht anders angegeben, erhält die Ausgabedatei den Namen der Eingabedatei, die die [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)\-Methode enthält.  
  
 Wenn diese Option in der Befehlszeile angegeben wird, werden alle Dateien bis zur nächsten Option **\/out** oder **\/target:module** für die Erstellung der EXE\-Datei verwendet.  
  
 In den Quellcodedateien, die in eine EXE\-Datei kompiliert werden, wird ausschließlich eine **Main**\-Methode benötigt.  Mit der Compileroption [\/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) können Sie angeben, in welcher Klasse die **Main**\-Methode enthalten ist, falls der Code mehrere Klassen mit einer **Main**\-Methode aufweist.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite von **Anwendung**.  
  
3.  Ändern Sie die Eigenschaft **Ausgabetyp**.  
  
 Informationen über das programmgesteuerte Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Beispiel  
 Im folgenden Beispiel wird in jeder der Befehlszeilen `in.cs` kompiliert und `in.exe` erstellt:  
  
```  
csc /target:exe in.cs  
csc in.cs  
```  
  
## Siehe auch  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)