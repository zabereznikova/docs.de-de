---
title: "/win32res (C# Compiler Options) | Microsoft Docs"
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
  - "/win32res"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "win32res compiler option"
  - "/win32res compiler option [C#]"
  - "-win32res compiler option [C#]"
  - "win32res compiler option [C#]"
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /win32res (C# Compiler Options)
Die Option **\/win32res** fügt eine Win32\-Ressource in die Ausgabedatei ein.  
  
## Syntax  
  
```  
/win32res:filename  
```  
  
## Argumente  
 `filename`  
 Die Ressourcendatei, die Sie der Ausgabedatei hinzufügen möchten.  
  
## Hinweise  
 Eine Win32\-Ressourcendatei kann mit erstellt werden [Ressourcencompiler](http://go.microsoft.com/fwlink/?LinkId=148370).  Der Ressourcencompiler wird gestartet, wenn Sie ein Visual C\+\+\-Programm kompilieren. Aus der RC\-Datei wird eine RES\-Datei erstellt.  
  
 Eine Win32\-Ressource kann Versions\- oder Bitmap\(Symbol\) Informationen enthalten, die die Erfolgsquote würden, die Anwendung im Datei\-Explorer zu identifizieren.  Wenn Sie **\/win32res** nicht angeben, generiert der Compiler Versionsinformationen auf der Grundlage der Assemblyversion.  
  
 Weitere Informationen über das Verweisen auf eine .NET Framework\-Ressourcendatei finden Sie unter [\/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) bzw. über das Anhängen einer .NET Framework\-Ressourcendatei unter [\/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite von **Anwendung**.  
  
3.  Klicken Sie auf die Schaltfläche **Ressourcendatei**, und wählen Sie mit dem Kombinationsfeld eine Datei aus.  
  
## Beispiel  
 In diesem Beispiel wird `in.cs` kompiliert, die Win32\-Ressourcendatei `rf.res` angefügt und `in.exe` erstellt:  
  
```  
csc /win32res:rf.res in.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)