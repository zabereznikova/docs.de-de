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
ms.openlocfilehash: 2aff86fb63b87869ed13028bd7344afe11363f51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723180"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs-Methode

Ruft einen Enumerator für zwischengespeicherte Windows-Runtime Typen in einer Anwendungsdomäne auf der Grundlage ihrer Schnittstellen Bezeichner ab.  
  
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
 in Die Anzahl der erforderlichen Typen.  
  
 `iidsToResolve`  
 in Ein Zeiger auf ein Array, das die Schnittstellen Bezeichner enthält, die den verwalteten Darstellungen der Windows-Runtime Typen entsprechen, die abgerufen werden sollen.  
  
 `ppTypesEnum`  
 vorgenommen Ein Zeiger auf die Adresse eines icorentbugtypeenum-Schnittstellen Objekts, das die Aufzählung der zwischengespeicherten verwalteten Darstellungen der Windows-Runtime abgerufenen Typen basierend auf den Schnittstellen Bezeichners in ermöglicht `iidsToResolve` .  
  
## <a name="remarks"></a>Hinweise  

 Wenn die Methode keine Informationen für einen bestimmten Schnittstellen Bezeichner abrufen kann, weist der entsprechende Eintrag in der ICorDebugTypeEnum-Auflistung `ELEMENT_TYPE_END` aufgrund von Datenabruf Problemen oder `ELEMENT_TYPE_VOID` bei unbekannten Schnittstellen Bezeichnern den Typ "Fehler" auf.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Windows-Runtime  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugAppDomain3-Schnittstelle](icordebugappdomain3-interface.md)
