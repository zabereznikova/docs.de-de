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
ms.openlocfilehash: 4b071bd8e9d96084848c1553385eec5f8beca624
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711727"
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
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|`S_OK`|Der Methodenaufrufe hat einen Slot-Index-Wert in zurückgegeben `pSlotIndex` .|  
|`E_FAIL`|Die aktuelle [icorentbugvariablehome](icordebugvariablehome-interface.md) -Instanz stellt ein Funktions Argument dar.|  
  
## <a name="remarks"></a>Hinweise  

 Der Slot-Index kann verwendet werden, um die Metadaten für diese lokale Variable abzurufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugVariableHome-Schnittstelle](icordebugvariablehome-interface.md)
