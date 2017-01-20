---
title: "/nologo (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-nologo compiler option [Visual Basic]"
  - "banners, suppressing startup"
  - "nologo compiler option [Visual Basic]"
  - "/nologo compiler option [Visual Basic]"
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /nologo (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Unterdrückt die Anzeige der Copyrightinformationen sowie der Informationsmeldungen während der Kompilierung.  
  
## Syntax  
  
```  
/nologo  
```  
  
## Hinweise  
 Wenn Sie `/nologo` angeben, zeigt der Compiler keine Copyrightinformationen an.  In der Standardeinstellung ist `/nologo` nicht aktiviert.  
  
> [!NOTE]
>  Die Option `/nologo` ist nicht innerhalb der Entwicklungsumgebung von Visual Studio verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Beispiel  
 Mit dem folgenden Code wird `T2.vb` kompiliert. Copyrightinformationen werden nicht angezeigt.  
  
```  
vbc /nologo t2.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)