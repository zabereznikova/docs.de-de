---
title: "/target:winexe (C# Compiler Options) | Microsoft Docs"
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
  - "/target:winexe"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/target compiler options [C#], /target:winexe"
  - "-target compiler options [C#], /target:winexe"
  - "target compiler options [C#], /target:winexe"
ms.assetid: b5a0619c-8caa-46a5-a743-1cf68408ad7a
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /target:winexe (C# Compiler Options)
Die Option **\/target:winexe** bewirkt, dass der Compiler ein ausführbares Windows\-Programm \(**.exe**\) erstellt.  
  
## Syntax  
  
```  
/target:winexe  
```  
  
## Hinweise  
 Die ausführbare Datei wird mit der Erweiterung **.exe** erstellt.  Ein Windows\-Programm ist eine Anwendung, die eine Benutzeroberfläche entweder aus der .NET Framework\-Bibliothek oder mit den Win32\-APIs bereitstellt.  
  
 Verwenden Sie [\/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md), um eine Konsolenanwendung zu erstellen.  
  
 Sofern durch die Option [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) nicht anders angegeben, erhält die Ausgabedatei den Namen der Eingabedatei, die die [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)\-Methode enthält.  
  
 Wird diese Option in der Befehlszeile angegeben, werden alle Dateien bis zur nächsten Option **\/out** bzw. [\/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) für die Erstellung des Windows\-Programms verwendet.  
  
 In den Quellcodedateien, die in eine EXE\-Datei kompiliert werden, wird ausschließlich eine **Main**\-Methode benötigt.  Mit der Option [\/main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) können Sie die Klasse angeben, in der die **Main**\-Methode enthalten ist, falls der Code mehrere Klassen mit einer **Main**\-Methode aufweist.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite von **Anwendung**.  
  
3.  Ändern Sie die Eigenschaft **Ausgabetyp**.  
  
 Informationen über das programmgesteuerte Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Beispiel  
 In diesem Beispiel wird `in.cs` in ein Windows\-Programm kompiliert:  
  
```  
csc /target:winexe in.cs  
```  
  
## Siehe auch  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)