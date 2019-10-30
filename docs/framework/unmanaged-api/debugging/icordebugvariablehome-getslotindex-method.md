---
title: 'Icordebugvariablehome:: gezlotindex-Methode'
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
ms.openlocfilehash: dfc2e91599e7f05d90d56af07b71313e9eecaa51
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121056"
---
# <a name="icordebugvariablehomegetslotindex-method"></a>Icordebugvariablehome:: gezlotindex-Methode
Ruft den verwalteten Slot-Index einer lokalen Variablen ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pSlotIndex`  
 vorgenommen Ein Zeiger auf den slotindex einer lokalen Variablen.  
  
## <a name="return-value"></a>Rückgabewert  
 Die-Methode gibt die folgenden Werte zurück.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`S_OK`|Der Methodenaufrufe hat einen Slot-Index-Wert in `pSlotIndex`zurückgegeben.|  
|`E_FAIL`|Die aktuelle [icorentbugvariablehome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) -Instanz stellt ein Funktions Argument dar.|  
  
## <a name="remarks"></a>Hinweise  
 Der Slot-Index kann verwendet werden, um die Metadaten für diese lokale Variable abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugVariableHome-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
