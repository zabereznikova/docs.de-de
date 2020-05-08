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
ms.openlocfilehash: a21f3b36e418bbde5dcb90f25a39dae03fde77c9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895211"
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
 Wenn ein <xref:System.AppDomain?displayProperty=nameWithType> verwaltetes Objekt für diese Anwendungsdomäne nicht erstellt wurde, gibt die `S_FALSE` Methode zurück `NULL` und `*ppObject`stellt in dar.  
  
## <a name="remarks"></a>Hinweise  
 Jede Anwendungsdomäne in einem Prozess kann über ein verwaltetes <xref:System.AppDomain?displayProperty=nameWithType> Objekt in der Laufzeit verfügen, das Sie darstellt. Diese Funktion Ruft ein ICorDebug Value-Schnittstellen Objekt ab, das diesem verwalteten <xref:System.AppDomain?displayProperty=nameWithType> Objekt entspricht.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
