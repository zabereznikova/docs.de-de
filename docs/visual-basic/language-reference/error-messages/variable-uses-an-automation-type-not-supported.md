---
title: "Variable uses an Automation type not supported in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID458"
dev_langs: 
  - "VB"
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Variable uses an Automation type not supported in Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Sie haben versucht, eine Variable zu verwenden, die in einer Typ\- oder Objektbibliothek definiert ist und einen Datentyp aufweist, der von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] nicht unterstützt wird.  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie eine Variable eines Typs, der von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] erkannt wird.  
  
     \- oder \-  
  
-   Wenn dieser Fehler bei der Verwendung von `FileGet` oder `FileGetOBject` auftritt, stellen Sie sicher, dass der Schreibvorgang in die Datei, die Sie verwenden möchten, mit `FilePut` oder `FilePutObject` erfolgt ist.  
  
## Siehe auch  
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)