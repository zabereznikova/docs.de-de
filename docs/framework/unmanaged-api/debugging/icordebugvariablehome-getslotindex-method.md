---
title: ICorDebugVariableHome::GetSlotIndex-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3534160e14c46bc3f8f5da81c4c14a3191a6238b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553191"
---
# <a name="icordebugvariablehomegetslotindex-method"></a>ICorDebugVariableHome::GetSlotIndex-Methode
Ruft den verwalteten slotindex einer lokalen Variablen ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pSlotIndex`  
 [out] Ein Zeiger auf den slotindex einer lokalen Variablen.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Methode gibt die folgenden Werte an.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`S_OK`|Aufruf der Methode wurde in einen Slot-Indexwert `pSlotIndex`.|  
|`E_FAIL`|Die aktuelle [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Instanz darstellt, ein Funktionsargument.|  
  
## <a name="remarks"></a>Hinweise  
 Die Slot-Index kann zum Abrufen der Metadaten für diese lokale Variable verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugVariableHome-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
