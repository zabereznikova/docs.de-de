---
title: "/nostdlib (C# Compiler Options) | Microsoft Docs"
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
  - "/nostdlib"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nostdlib compiler option [C#]"
  - "-nostdlib compiler option [C#]"
  - "/nostdlib compiler option [C#]"
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /nostdlib (C# Compiler Options)
**\/nostdlib** verhindert den Import der Datei „mscorlib.dll“, die den gesamten Systemnamespace definiert.  
  
## Syntax  
  
```  
/nostdlib[+ | -]  
```  
  
## Hinweise  
 Verwenden Sie diese Option, wenn Sie Ihren eigenen Systemnamespace und die entsprechenden Objekte definieren oder erstellen möchten.  
  
 Wenn Sie **\/nostdlib** nicht angeben, wird „mscorlib.dll“ in das Programm importiert \(entspricht der Angabe von **\/nostdlib\-**\). Die Angabe von **\/nostdlib** ist mit der Angabe von **\/nostdlib\+** identisch.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** für das Projekt.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Nicht auf mscorlib.dll verweisen**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)