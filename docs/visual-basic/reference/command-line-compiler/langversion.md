---
title: "/langversion (Visual Basic) | Microsoft Docs"
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
  - "/langversion compiler option [Visual Basic]"
  - "langversion compiler option [Visual Basic]"
  - "-langversion compiler option [Visual Basic]"
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# /langversion (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Bewirkt, dass der Compiler nur Syntax akzeptiert, die in der angegebenen Sprachversion von Visual Basic enthalten ist.  
  
## Syntax  
  
```  
/langversion:version  
```  
  
## Argumente  
 `version`  
 Erforderlich.  Die Sprachversion, die während der Kompilierung verwendet werden soll.  Akzeptierte Werte sind `9`, `9.0`, `10` und `10.0`.  
  
## Hinweise  
 Die `/langversion`\-Option gibt an, welche Syntax der Compiler akzeptiert.  Wenn Sie beispielsweise die Sprachversion 9.0 angeben, generiert der Compiler Fehler für Syntax, die nur in Version 10.0 und höher gültig ist.  
  
 Sie können diese Option verwenden, wenn Sie Anwendungen entwickeln, die auf andere Versionen von .NET Framework abzielen.  Wenn Sie z. B. auf .NET Framework 3.5 abzielen, können Sie diese Option verwenden, um sicherzustellen, dass Sie keine Syntax aus der Sprachversion 10.0 verwenden.  
  
 `/langversion` kann nur über die Befehlszeile direkt festgelegt werden.  Weitere Informationen finden Sie unter [Festlegen einer bestimmten .NET\-Framework\-Zielversion](/visual-studio/ide/targeting-a-specific-dotnet-framework-version).  
  
## Beispiel  
 Im folgenden Code wird `sample.vb` für Visual Basic 9.0 kompiliert.  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Festlegen einer bestimmten .NET\-Framework\-Zielversion](/visual-studio/ide/targeting-a-specific-dotnet-framework-version)