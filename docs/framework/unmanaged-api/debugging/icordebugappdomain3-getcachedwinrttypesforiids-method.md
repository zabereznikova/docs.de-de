---
title: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ef8d1c47275d3cbd69c1516b788b950f8535513
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737714"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs-Methode
Ruft einen Enumerator für zwischengespeicherte Windows-Runtime-Typen in einer Anwendungsdomäne, basierend auf ihren Schnittstellenbezeichner ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cReqTypes`  
 [in] Die Anzahl der erforderlichen Typen.  
  
 `iidsToResolve`  
 [in] Ein Zeiger auf ein Array mit den Schnittstellenbezeichner, der für die verwaltete Darstellungen von der Windows-Runtime-Typen abgerufen werden sollen.  
  
 `ppTypesEnum`  
 [out] Ein Zeiger auf die Adresse eines Objekts der "ICorDebugTypeEnum"-Schnittstelle, die Enumeration der zwischengespeicherten verwaltete Darstellungen von der Windows-Runtime-Typen ermöglicht abgerufen, die basierend auf den Schnittstellenbezeichner in `iidsToResolve`.  
  
## <a name="remarks"></a>Hinweise  
 Fällt die Methode zum Abrufen von Informationen für eine bestimmte Schnittstelle-ID, weist der entsprechende Eintrag in der Auflistung "ICorDebugTypeEnum" einen Typ von `ELEMENT_TYPE_END` nach Fehlern aufgrund von Datenproblemen abrufen, oder `ELEMENT_TYPE_VOID` für unbekannte-Schnittstelle Bezeichner.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Windows-Runtime  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugAppDomain3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
