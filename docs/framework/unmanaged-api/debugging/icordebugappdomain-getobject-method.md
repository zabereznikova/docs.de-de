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
ms.openlocfilehash: f2c881603cfa0e4b3d2dc8d1e996631b51d1e850
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134712"
---
# <a name="icordebugappdomaingetobject-method"></a>ICorDebugAppDomain::GetObject-Methode
Ruft einen Schnittstellen Zeiger auf die Common Language Runtime (CLR)-Anwendungsdomäne ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppObject`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Schnittstellen Objekts, das die CLR-Anwendungsdomäne darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn ein verwaltetes <xref:System.AppDomain?displayProperty=nameWithType> Objekt für diese Anwendungsdomäne nicht erstellt wurde, gibt die Methode `S_FALSE` zurück und platziert `NULL` in `*ppObject`.  
  
## <a name="remarks"></a>Hinweise  
 Jede Anwendungsdomäne in einem Prozess kann über ein verwaltetes <xref:System.AppDomain?displayProperty=nameWithType> Objekt in der Laufzeit verfügen, das Sie darstellt. Diese Funktion Ruft ein icorentbugvalue-Schnittstellen Objekt ab, das diesem verwalteten <xref:System.AppDomain?displayProperty=nameWithType> Objekt entspricht.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
