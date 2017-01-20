---
title: "/highentropyva (C# Compiler Options) | Microsoft Docs"
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
  - "/highentropyva"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/highentropyva compiler option [C#]"
  - "-highentropyva compiler option [C#]"
  - "highentropyva compiler option [C#]"
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /highentropyva (C# Compiler Options)
Die **\/highentropyva**\-Compileroption weist den Kernel von Windows an, ob eine bestimmte EXE\-Datei hohe Entropie Adressbereichs\-Layout\-Zufallszuteilung \(ASLR\) unterstützt.  
  
## Syntax  
  
```  
/highentropyva[+ | -]  
```  
  
## Argumente  
 `+` &#124; `-`  
 Diese Option gibt an, dass eine 64\-Bit\-ausführbareDatei oder eine ausführbare Datei, die von der Compileroption [\/platform: anycpu](../../../csharp/language-reference/compiler-options/platform-compiler-option.md) markiert ist, einen virtuellen Adressraum hoher Entropie unterstützt.  Die Option ist standardmäßig deaktiviert.  Verwendung von **\/highentropyva\+** oder **\/highentropyva**, sie zu aktivieren.  
  
## Hinweise  
 Die **\/highentropyva** \- Option aktiviert kompatible Versionen des Windows\-Kernels, um höhere Grade an Entropie zu verwenden, wenn sie das Adressbereichslayout eines Prozesses als Teil ASLR randomisiert.  Verwenden von an der höheren Entropie bedeutet, dass eine größere Anzahl von Adressen doppelt belegter wie Stapeln und Heaps belegt werden kann.  Daher liegt es schwieriger, den Speicherort eines bestimmten doppelt belegter einzuschätzen.  
  
 Wenn die **\/highentropyva**\-Compileroption angegeben wird, müssen das ausführbare Ziel und Module, die davon abhängig sind, sein, Zeigerwerte, die größer sind, als 4 Gigabyte \(GB\) zu behandeln, die als 64\-Bit\-Prozess ausgeführt werden.  
  
 Weitere Informationen über ASLR, Sie finden. [Um von Schwachstellen](http://go.microsoft.com/fwlink/?LinkId=226234)