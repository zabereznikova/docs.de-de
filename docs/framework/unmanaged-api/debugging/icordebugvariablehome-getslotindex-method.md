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
ms.openlocfilehash: 542bfa05c55ef224d1b9111f9af6c069e9e23542
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790974"
---
# <a name="icordebugvariablehomegetslotindex-method"></a>Icordebugvariablehome:: gezlotindex-Methode
Ruft den verwalteten Slot-Index einer lokalen Variablen ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pSlotIndex`  
 vorgenommen Ein Zeiger auf den slotindex einer lokalen Variablen.  
  
## <a name="return-value"></a>Rückgabewert  
 Die-Methode gibt die folgenden Werte zurück.  
  
|{2&gt;Wert&lt;2}|Beschreibung|  
|-----------|-----------------|  
|`S_OK`|Der Methodenaufrufe hat einen Slot-Index-Wert in `pSlotIndex`zurückgegeben.|  
|`E_FAIL`|Die aktuelle [icorentbugvariablehome](icordebugvariablehome-interface.md) -Instanz stellt ein Funktions Argument dar.|  
  
## <a name="remarks"></a>Hinweise  
 Der Slot-Index kann verwendet werden, um die Metadaten für diese lokale Variable abzurufen.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugVariableHome-Schnittstelle](icordebugvariablehome-interface.md)
