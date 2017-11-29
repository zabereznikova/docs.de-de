---
title: ICorDebugAppDomain::GetObject-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetObject
api_location: corguids.lib
api_type: COM
f1_keywords: ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c4f923d8e9bf9762d5208dd6e9be527a50a688b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomaingetobject-method"></a>ICorDebugAppDomain::GetObject-Methode
Ruft einen Schnittstellenzeiger auf die common Language Runtime (CLR) Anwendungsdomäne ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppObject`  
 [out] Ein Zeiger auf die Adresse des ICorDebugValue-Schnittstellenobjekts, das die CLR die Anwendungsdomäne darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn ein verwaltetes <xref:System.AppDomain?displayProperty=nameWithType> Objekt wurde nicht für diese Anwendungsdomäne erstellt wurde, gibt die Methode zurück `S_FALSE` und platziert `NULL` in `*ppObject`.  
  
## <a name="remarks"></a>Hinweise  
 Jede Anwendungsdomäne in einem Prozess ist möglicherweise ein verwaltetes <xref:System.AppDomain?displayProperty=nameWithType> Objekt in der Laufzeit, die es darstellt. Diese Funktion ruft eine ICorDebugValue-Schnittstellenobjekts, das dies verwaltet entspricht <xref:System.AppDomain?displayProperty=nameWithType> Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
