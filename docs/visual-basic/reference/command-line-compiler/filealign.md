---
title: "/filealign | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "sections compiler option [Visual Basic]"
  - "alignment compiler option [Visual Basic]"
  - "-filealign compiler option [Visual Basic]"
  - "section alignment"
  - "/filealign compiler option [Visual Basic]"
  - "filealign compiler option [Visual Basic]"
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# /filealign
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt an, wo die Abschnitte der Ausgabedatei auszurichten sind.  
  
## Syntax  
  
```  
/filealign:number  
```  
  
## Argumente  
 `number`  
 Erforderlich.  Ein Wert, der die Ausrichtung der Abschnitte in der Ausgabedatei angibt.  Gültige Werte sind 512, 1024, 2048, 4096 und 8192.  Hierbei handelt es sich um Byteangaben.  
  
## Hinweise  
 Mit der `/filealign`\-Option geben Sie die Ausrichtung von Abschnitten in der Ausgabedatei an.  Abschnitte sind zusammenhängende Arbeitsspeicherblöcke in einer PE\-\(Portable Executable\-\)Datei, die entweder Code oder Daten enthält.  Mit der `/filealign`\-Option können Sie Ihre Anwendung mit einer nicht standardmäßigen Ausrichtung kompilieren. Diese Option wird von den meisten Entwicklern in der Regel nicht benötigt.  
  
 Jeder Abschnitt wird an einer Grenze ausgerichtet, die ein Vielfaches des `/filealign`\-Werts ist.  Es gibt keinen festen Standardwert.  Wurde `/filealign` nicht angegeben, wählt der Compiler zur Kompilierungszeit einen Standardwert aus.  
  
 Durch Angeben der Abschnittsgröße können Sie die Größe der Ausgabedatei ändern.  Es kann hilfreich sein, die Abschnittsgröße zu ändern, wenn Sie Programme auf kleineren Geräten ausführen.  
  
> [!NOTE]
>  Die `/filealign`\-Option ist in der Entwicklungsumgebung von Visual Studio nicht verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)