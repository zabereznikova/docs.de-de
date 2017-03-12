---
title: "SimplifiedChinese und VbStrConv.TraditionalChinese k&#246;nnen nicht kombiniert werden. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrArgument_StrConvSCandTC"
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# SimplifiedChinese und VbStrConv.TraditionalChinese k&#246;nnen nicht kombiniert werden.
Die Anwendung versucht, die sich gegenseitig ausschließenden `VbStrConv`\-Enumerationsmember `SimplifiedChinese` und `TraditionalChinese` zu kombinieren.  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie entweder  `VbStrConv.SimplifiedChinese` oder `VbStrConv.TraditionalChinese`.  
  
## Siehe auch  
 <xref:System.Globalization>   
 [NICHT IM BUILD: VbStrConv\-Enumeration](http://msdn.microsoft.com/de-de/59f83dd9-6361-47df-a836-02ba9d4cb936)   
 [Einführung in internationale Anwendungen basierend auf .NET Framework](/visual-studio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)