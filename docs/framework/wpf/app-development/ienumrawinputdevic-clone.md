---
title: "IEnumRAWINPUTDEVIC:Clone | Microsoft Docs"
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
  - "Clone-Methode"
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# IEnumRAWINPUTDEVIC:Clone
Erstellt einen weiteren Enumerator für Geräte für die unformatierte Eingabe, der im selben Zustand wie der aktuelle Enumerator ist und dieselbe Liste durchlaufen soll.  
  
## Syntax  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### Parameter  
 `ppenum`  
  
 \[out\] Adresse einer Ausgabevariable, die den [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md)\-Schnittstellenzeiger empfängt.  Wenn die Methode fehlschlägt, ist der Wert dieser Ausgabevariablen nicht definiert.  
  
## Eigenschaftswert\/Rückgabewert  
 HRESULT: Diese Methode unterstützt die Standardrückgabewerte E\_INVALIDARG, E\_OUTOFMEMORY und E\_UNEXPECTED.  
  
## Hinweise  
 Durch diese Methode ist es möglich, einen Punkt in der Enumerationsfolge aufzuzeichnen, um später zu diesem Punkt zurückzukehren.  Der Aufrufer muss diesen neuen Enumerator separat vom ersten Enumerator freigeben.