---
title: "Ein Aufruf f&#252;r eine Eigenschaft oder Methode darf keinen Verweis auf ein privates Objekt enthalten - weder als Argument, noch als R&#252;ckgabewert. | Microsoft Docs"
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
  - "vbrID98"
dev_langs: 
  - "VB"
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Ein Aufruf f&#252;r eine Eigenschaft oder Methode darf keinen Verweis auf ein privates Objekt enthalten - weder als Argument, noch als R&#252;ckgabewert.
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Zu den möglichen Ursachen für diesen Fehler gehören:  
  
-   Ein Client hat eine Eigenschaft oder Methode einer Out\-of\-Process\-Komponente aufgerufen und versucht, einen Verweis auf ein privates Objekt als eines der Argumente zu übergeben.  
  
-   Eine Out\-of\-Process\-Komponente hat eine Callback\-Methode für ihren Client aufgerufen und versucht, einen Verweis auf ein privates Objekt zu übergeben  
  
-   Eine Out\-of\-Process\-Komponente hat versucht, einen Verweis auf ein privates Objekt als Argument eines Ereignisses zu übergeben, das von ihr ausgelöst wurde.  
  
-   Ein Client hat versucht, einem `ByRef`\-Argument eines Ereignisses, das er verarbeitet hat, einen privaten Objektverweis zuzuweisen.  
  
### So beheben Sie diesen Fehler  
  
1.  Entfernen Sie den Verweis.  
  
## Siehe auch  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)