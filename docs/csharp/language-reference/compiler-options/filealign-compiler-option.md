---
title: "/filealign (C# Compiler Options) | Microsoft Docs"
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
  - "/filealign"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/alignment compiler option [C#]"
  - "filealign compiler option [C#]"
  - "-filealign compiler option [C#]"
  - "/sections compiler option [C#]"
  - "alignment compiler option [C#]"
  - "sections compiler option [C#]"
  - "-sections compiler option [C#]"
  - "/filealign compiler option [C#]"
  - "file sharing [C#]"
  - "-alignment compiler option [C#]"
  - "section alignment [C#]"
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /filealign (C# Compiler Options)
Mit der Option **\/filealign** können Sie die Größe der Abschnitte in der Ausgabedatei festlegen.  
  
## Syntax  
  
```  
/filealign:number  
```  
  
## Argumente  
 `number`  
 ein Wert, der die Größe der Abschnitte in der Ausgabedatei angibt.  Gültige Werte sind 512, 1024, 2048, 4096 und 8192.  Hierbei handelt es sich um Byteangaben.  
  
## Hinweise  
 Jeder Abschnitt wird an einer Grenze ausgerichtet, die einem Vielfachen des **\/filealign**\-Werts entspricht.  Es gibt keinen festen Standardwert.  Wurde **\/filealign** nicht angegeben, wählt die Common Language Runtime zur Kompilierungszeit einen Standardwert aus.  
  
 Durch Angeben der Abschnittsgröße können Sie die Größe der Ausgabedatei steuern.  Es kann hilfreich sein, die Abschnittsgröße zu ändern, wenn Sie Programme auf kleineren Geräten ausführen.  
  
 Mit [DUMPBIN\-Optionen](/visual-cpp/build/reference/dumpbin-options) können Sie Informationen über Abschnitte in der Ausgabedatei anzeigen.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Dateianordnung**.  
  
 Informationen darüber, wie Sie diese Compileroption programmgesteuert festlegen können, finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)