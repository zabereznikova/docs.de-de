---
title: "&#39;&lt;functionname&gt;&#39; is not declared (Smart Device/Visual Basic Compiler Error) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30766"
  - "vbc30766"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30766"
ms.assetid: 13918600-6087-40d7-8134-32aa9d3bfda4
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;functionname&gt;&#39; is not declared (Smart Device/Visual Basic Compiler Error)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

\<`functionname`\> ist nicht deklariert.  Datei\-E\/A\-Funktionalität ist normalerweise im `Microsoft.VisualBasic`\-Namespace verfügbar, die verwendete Version von .NET Compact Framework unterstützt sie jedoch nicht.  
  
 **Fehler\-ID:** BC30766  
  
### So beheben Sie diesen Fehler  
  
-   Führen Sie Dateioperationen mit Funktionen durch, die im `System.IO`\-Namespace definiert sind.  
  
## Siehe auch  
 <xref:System.IO>   
 [File Access with Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)