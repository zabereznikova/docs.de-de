---
title: IEnumRAWINPUTDEVIC:Clone
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db218ec824dfe163946b0c1bd412efd0f78f4ad8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ienumrawinputdevicclone"></a>IEnumRAWINPUTDEVIC:Clone
Erstellt einen weiteren Enumerator für Geräte für die unformatierte Eingabe, der denselben Zustand wie der aktuelle Enumerator aufweist und dieselbe Liste durchlaufen soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppenum`  
  
 [out] Adresse des Output-Variable, die empfängt die [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) Schnittstellenzeiger auf. Wenn die Methode fehlschlägt, ist der Wert dieser Variablen Ausgabe nicht definiert.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT: Diese Methode unterstützt die Standardrückgabewerte E_INVALIDARG und E_OUTOFMEMORY E_UNEXPECTED.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Methode ist es möglich, einen Punkt in der Enumerationsfolge zu erfassen, um bis zu diesem Zeitpunkt zu einem späteren Zeitpunkt zurück. Der Aufrufer muss diesen neuen Enumerator separat aus dem ersten Enumerator freigeben.
