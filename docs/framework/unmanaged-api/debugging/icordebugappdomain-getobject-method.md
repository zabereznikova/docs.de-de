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
ms.openlocfilehash: 1201ac0dca9cbd48c24b2621eba079ae672fd310
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737852"
---
# <a name="icordebugappdomaingetobject-method"></a>ICorDebugAppDomain::GetObject-Methode
Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne der common Language Runtime (CLR) ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
