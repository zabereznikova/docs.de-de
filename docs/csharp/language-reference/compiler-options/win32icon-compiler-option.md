---
title: "/win32icon (C# Compiler Options) | Microsoft Docs"
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
  - "/win32icon"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "win32icon compiler option [C#]"
  - "/win32icon compiler option [C#]"
  - "-win32icon compiler option [C#]"
ms.assetid: 756d9b6d-ab07-41b7-ba58-5bd88f711138
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /win32icon (C# Compiler Options)
Die Option **\/win32icon** fügt eine ICO\-Datei in der Ausgabedatei ein, die die Ausgabedatei die gewünschte Darstellung im Datei\-Explorer gibt.  
  
## Syntax  
  
```  
/win32icon:filename  
```  
  
## Argumente  
 `filename`  
 die ICO\-Datei, die Sie der Ausgabedatei hinzufügen möchten.  
  
## Hinweise  
 Eine ICO\-Datei kann mit erstellt werden [Ressourcencompiler](http://go.microsoft.com/fwlink/?LinkId=148370).  Der Ressourcencompiler wird gestartet, wenn Sie ein Visual C\+\+\-Programm kompilieren. Die ICO\-Datei wird anhand der RC\-Datei erstellt.  
  
 Weitere Informationen über das Verweisen auf eine .NET Framework\-Ressourcendatei finden Sie unter [\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) bzw. über das Anhängen einer .NET Framework\-Ressourcendatei unter [\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md).  Informationen zum Importieren einer RES\-Datei finden Sie unter [\/win32res](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite von **Anwendung**.  
  
3.  Ändern Sie die Eigenschaft **Anwendungssymbol**.  
  
 Informationen darüber, wie Sie diese Compileroption programmgesteuert festlegen können, finden Sie unter <xref:VSLangProj80.ProjectProperties3.ApplicationIcon%2A>.  
  
## Beispiel  
 In diesem Beispiel wird `in.cs` kompiliert, die ICO\-Datei `rf.ico` wird angehängt, und `in.exe` wird erstellt:  
  
```  
csc /win32icon:rf.ico in.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)