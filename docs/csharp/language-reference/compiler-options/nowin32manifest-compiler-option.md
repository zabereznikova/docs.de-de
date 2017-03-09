---
title: "/nowin32manifest (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/nowin32manifest"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nowin32manifest compiler option [C#]"
  - "-nowin32manifest compiler option [C#]"
  - "/nowin32manifest compiler option [C#]"
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /nowin32manifest (C# Compiler Options)
Weisen Sie den Compiler mit der **\/nowin32manifest**\-Option an, kein Anwendungsmanifest in die ausführbare Datei einzubetten.  
  
## Syntax  
  
```  
/nowin32manifest  
```  
  
## Hinweise  
 Wenn Sie diese Option verwenden, unterliegt die Anwendung der Virtualisierung unter Windows Vista, es sei denn, Sie stellen ein Anwendungsmanifest in einer Win32\-Ressourcendatei oder bei einem späteren Buildschritt bereit.  Weitere Informationen über Virtualisierung finden Sie unter [New UAC Technologies for Windows Vista](http://msdn.microsoft.com/de-de/80efa4c7-3904-45c5-82e8-2d558fe67db9).  
  
 Legen Sie in Visual Studio diese Option auf der Seite für die **Anwendungseigenschaften** fest, indem Sie in der Dropdownliste **Manifest** die Option **Anwendung ohne Manifest erstellen** auswählen.  Weitere Informationen finden Sie unter [Seite "Anwendung", Projekt\-Designer \(C\#\)](/visual-studio/ide/reference/application-page-project-designer-csharp).  
  
 Weitere Informationen über das Erstellen von Manifesten finden Sie unter [\/win32manifest \(Import a Custom Win32 Manifest File\)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)