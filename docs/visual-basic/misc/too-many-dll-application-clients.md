---
title: "Zu viele Clients f&#252;r die DLL-Anwendung | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID47"
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Zu viele Clients f&#252;r die DLL-Anwendung
Die Dynamic Link Library \(DLL\) für [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kann nur einer begrenzten Anzahl von Hostanwendungen Zugriff gewähren. Ihre Anwendung und andere Clientanwendungen, die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\- Hosts sind \(von denen auf einige möglicherweise von Ihrer Anwendung zugegriffen wird\), versuchen gleichzeitig, auf die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-DLL zuzugreifen.  
  
### So beheben Sie diesen Fehler  
  
-   Reduzieren Sie die Anzahl der geöffneten Anwendungen, die auf [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] zugreifen.  
  
## Siehe auch  
 [Error Types](../../visual-basic/programming-guide/language-features/error-types.md)