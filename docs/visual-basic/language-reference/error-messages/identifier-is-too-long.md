---
title: "Identifier is too long | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30033"
  - "vbc30033"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30033"
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Identifier is too long
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Der Name oder Bezeichner jedes Programmierelements kann maximal 1023 Zeichen Länge haben.  Darüber hinaus darf ein voll gekennzeichneter Name nicht länger als 1023 Zeichen sein.  Das heißt, dass die gesamte Bezeichnerzeichenfolge \(`<namespace>.<...>.<namespace>.<class>.<element>`\) einschließlich der Memberzugriff\-Operatorzeichen \(`.`\) nicht mehr als 1023 Zeichen umfassen darf.  
  
 **Fehler\-ID:** BC30033  
  
### So beheben Sie diesen Fehler  
  
-   Kürzen Sie den Bezeichner.  
  
## Siehe auch  
 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)