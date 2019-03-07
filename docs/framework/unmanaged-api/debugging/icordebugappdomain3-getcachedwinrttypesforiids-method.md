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
ms.openlocfilehash: 601110d37fabbff01aeb14d8ca69a27a2463353f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491412"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs-Methode
Ruft einen Enumerator ab, für die Zwischenspeicherung [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen in einer Anwendungsdomäne auf der Grundlage von deren Schnittstellenbezeichner.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Ein Zeiger auf ein Array, das die verwaltete Darstellung der entsprechenden Schnittstellenbezeichner enthält den [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen abgerufen werden sollen.  
  
 `ppTypesEnum`  
 [out] Ein Zeiger auf die Adresse einer "ICorDebugTypeEnum"-Schnittstellenobjekts, das ermöglicht die Enumeration, der die zwischengespeicherten verwaltete Darstellungen der [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen abgerufen, die basierend auf den Schnittstellenbezeichner in `iidsToResolve`.  
  
## <a name="remarks"></a>Hinweise  
 Fällt die Methode zum Abrufen von Informationen für eine bestimmte Schnittstelle-ID, weist der entsprechende Eintrag in der Auflistung "ICorDebugTypeEnum" einen Typ von `ELEMENT_TYPE_END` nach Fehlern aufgrund von Datenproblemen abrufen, oder `ELEMENT_TYPE_VOID` für unbekannte-Schnittstelle Bezeichner.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugAppDomain3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
