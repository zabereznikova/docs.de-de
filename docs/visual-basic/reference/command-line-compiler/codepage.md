---
title: "/codepage (Visual Basic) | Microsoft Docs"
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
  - "/codepage compiler option [Visual Basic]"
  - "codepage compiler option [Visual Basic]"
  - "-codepage compiler option [Visual Basic]"
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# /codepage (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt die für alle Quellcodedateien in der Kompilierung zu verwendende Codepage an.  
  
## Syntax  
  
```  
/codepage:id  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`id`|Erforderlich.  Der Compiler verwendet die durch `id` angegebene Codepage zur Interpretation der Codierung der Quelldateien.|  
  
## Hinweise  
 Um Quellcode zu kompilieren, der mit einer bestimmten Codierung gespeichert wurde, können Sie mit `/codepage` die zu verwendende Codepage angeben.  Die `/codepage`\-Option wird auf alle bei der Kompilierung verwendeten Quellcodedateien angewendet.  Weitere Informationen finden Sie unter [Zeichencodierung in .NET Framework](../Topic/Character%20Encoding%20in%20the%20.NET%20Framework.md).  
  
 Die `/codepage`\-Option wird nicht benötigt, wenn die Quellcodedateien mit der aktuellen ANSI\-Codepage, mit Unicode oder mit UTF\-8 und einer Signatur gespeichert wurden.  [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] speichert alle Quellcodedateien standardmäßig mit der aktuellen ANSI\-Codepage, außer wenn der Benutzer eine andere Codierung im Dialogfeld **Codierung** angibt.  [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] verwendet das Dialogfeld **Codierung**, um mit einer anderen Codepage gespeicherte Quellcodedateien zu öffnen.  
  
> [!NOTE]
>  Die `/codepage`\-Option ist innerhalb der Entwicklungsumgebung von [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] nicht verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)