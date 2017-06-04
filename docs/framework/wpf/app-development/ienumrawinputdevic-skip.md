---
title: "IEnumRAWINPUTDEVIC:Skip | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Skip-Methode"
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# IEnumRAWINPUTDEVIC:Skip
Weist den Enumerator an, die nächsten `celt`\-Elemente in der Enumeration zu überspringen, sodass der nächste Aufruf von [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) diese Elemente nicht zurückgibt.  
  
## Syntax  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### Parameter  
 `celt`  
  
 \[in\] Anzahl der Elemente, die übersprungen werden sollen.  
  
## Eigenschaftswert\/Rückgabewert  
 HRESULT: S\_OK, wenn die Anzahl der Elemente `celt` ist. Andernfalls S\_FALSE.