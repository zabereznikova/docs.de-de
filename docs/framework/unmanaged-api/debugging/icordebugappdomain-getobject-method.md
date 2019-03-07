---
title: ICorDebugAppDomain::GetObject-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ca9792df69f859e20f1d9e40754d1cec138945d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480025"
---
# <a name="icordebugappdomaingetobject-method"></a>ICorDebugAppDomain::GetObject-Methode
Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne der common Language Runtime (CLR) ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppObject`  
 [out] Ein Zeiger auf die Adresse eines Objekts der ICorDebugValue-Schnittstelle, die die CLR die Anwendungsdomäne darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn eine verwaltete <xref:System.AppDomain?displayProperty=nameWithType> Objekt noch nicht für diese Anwendungsdomäne erstellt wurde, gibt die Methode zurück `S_FALSE` und `NULL` in `*ppObject`.  
  
## <a name="remarks"></a>Hinweise  
 Jede Anwendungsdomäne, in einem Prozess ist möglicherweise ein verwaltetes <xref:System.AppDomain?displayProperty=nameWithType> Objekt in der Laufzeit, die es darstellt. Diese Funktion ruft ICorDebugValue-Schnittstellenobjekts, das dieser verwalteten entspricht <xref:System.AppDomain?displayProperty=nameWithType> Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
