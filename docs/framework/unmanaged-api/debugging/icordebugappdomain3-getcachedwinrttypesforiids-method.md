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
ms.openlocfilehash: f8e92ec4f813e8810273a1514298d0739a3d2406
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179060"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs-Methode
Ruft einen Enumerator für zwischengespeicherte Windows-Runtime-Typen in einer Anwendungsdomäne basierend auf ihren Schnittstellenbezeichnern ab.  
  
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
 [in] Ein Zeiger auf ein Array, das die Schnittstellenbezeichner enthält, die den verwalteten Darstellungen der abzurufenden Windows-Runtime-Typen entsprechen.  
  
 `ppTypesEnum`  
 [out] Ein Zeiger auf die Adresse eines "ICorDebugTypeEnum"-Schnittstellenobjekts, das die Aufzählung der zwischengespeicherten verwalteten Darstellungen der `iidsToResolve`abgerufenen Windows-Runtime-Typen basierend auf den Schnittstellenbezeichnern in ermöglicht.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn die Methode keine Informationen für einen bestimmten Schnittstellenbezeichner abruft, enthält der entsprechende Eintrag `ELEMENT_TYPE_END` in der Auflistung "ICorDebugTypeEnum" eine Art von Fehlern aufgrund von Datenabrufproblemen oder `ELEMENT_TYPE_VOID` für unbekannte Schnittstellenbezeichner.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Windows-Runtime  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugAppDomain3-Schnittstelle](icordebugappdomain3-interface.md)
