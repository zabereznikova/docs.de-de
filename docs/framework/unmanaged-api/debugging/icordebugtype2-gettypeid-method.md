---
title: 'ICorDebugType2:: GetTypeId-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
ms.openlocfilehash: 2a4a0bfae6f9a1970f0d4aca8b37f8fc68194462
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725689"
---
# <a name="icordebugtype2gettypeid-method"></a>ICorDebugType2:: GetTypeId-Methode

Ruft eine [COR_TYPEID](cor-typeid-structure.md) für diesen Typ ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `id`  
 vorgenommen Ein Zeiger auf die [COR_TYPEID](cor-typeid-structure.md) für diesen ICorDebugType.  
  
## <a name="return-value"></a>Rückgabewert  

 Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler. Die `HRESULT` Codes umfassen Folgendes:  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|`S_OK`|Methode war erfolgreich. Die Methode hat einen gültigen [COR_TYPEID](cor-typeid-structure.md)abgerufen.|  
|`CORDBG_E_CLASS_NOT_LOADED`|Der Typ wurde nicht geladen.|  
|`CORDBG_E_UNSUPPORTED`|Der Typ wird nicht unterstützt.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Methode stellt eine Zuordnung aus dem ICorDebugType bereit, der einen Typ darstellt, der möglicherweise nicht in die Laufzeit geladen wurde, in einen [COR_TYPEID](cor-typeid-structure.md), der als nicht transparentes Handle fungiert, das einen Typ identifiziert, der in die Laufzeit geladen wurde.  
  
 Wenn der Typ, den der ICorDebugType darstellt, noch nicht geladen wurde, gibt diese Methode zurück `CORDBG_E_CLASS_NOT_LOADED` .  Wenn der Typ nicht unterstützt wird, wird zurückgegeben `CORDBG_E_UNSUPPORTED` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugType2-Schnittstelle](icordebugtype2-interface.md)
