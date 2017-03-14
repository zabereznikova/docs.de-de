---
title: "/highentropyva (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
helpviewer_keywords: 
  - "highentropyva compiler option (Visual Basic)"
  - "/highentropyva compiler option (Visual Basic)"
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# /highentropyva (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt an, ob eine 64\-Bit\-ausführbare Datei oder eine ausführbare Datei, die von der [\/platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md)\-Compileroption markiert ist, Adressraum\-Layout\-Zufallszuteilung ASLR \(Entropie hoch\) unterstützt.  
  
## Syntax  
  
```  
/highentropyva[+ | -]  
```  
  
## Argumente  
 `+` &#124; `-`  
 Optional.  Die Option ist standardmäßig deaktiviert, oder wenn Sie `/highentropyva-` angeben.  Die Option ist aktiviert, wenn Sie `/highentropyva` oder `/highentropyva+` angeben.  
  
## Hinweise  
 Wenn Sie diese Option angeben, können solche Versionen von Windows\-Kernels höhere Entropie an und verwenden, wenn der Kernel das Layout Adressbereich eines Prozesses als Teil randomisiert ASLR.  Wenn der Kernel höhere Entropie an und kann eine größere Anzahl von Adressen des Arbeitsspeicherbereichs wie Stapeln und Heaps zugeordnet sind.  Daher ist es schwieriger die Position eines bestimmten Arbeitsspeicherbereichs schätzen.  
  
 Wenn die Möglichkeit besteht darin, müssen die ausführbare Ziel und alle Module, von denen sie abhängig ist, befinden, Zeigerwerte, die größer sind als 4 Gigabyte \(GB\) zu behandeln, wenn diese Module als 64\-Bit\-Prozesse ausgeführt werden.  
  
 Weitere Informationen finden Sie unter ASLR. [Mindern Software\-Sicherheitsrisiken](http://go.microsoft.com/fwlink/?LinkId=226234)  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)