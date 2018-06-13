---
title: ICorDebugType2::GetTypeID-Methode
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bc1407f8444b78154981619742bd0da188c4335
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422070"
---
# <a name="icordebugtype2gettypeid-method"></a>ICorDebugType2::GetTypeID-Methode
Ruft eine [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) für diesen Typ.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `id`  
 [out] Ein Zeiger auf die [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) für ICorDebugType.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler. Die `HRESULT` Codes sind unter anderem folgende:  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|`S_OK`|Methode war erfolgreich. Die Methode verfügt über eine gültige abgerufen [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).|  
|`CORDBG_E_CLASS_NOT_LOADED`|Der Typ wurde nicht geladen.|  
|`CORDBG_E_UNSUPPORTED`|Der Typ wird nicht unterstützt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ermöglicht eine Zuordnung zwischen den ICorDebugType, die einen Typ darstellt, auf denen oder kann nicht geladen in die Laufzeit zu einer [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), welche fungiert als ein nicht transparenter, verarbeiten identifiziert einen Typ, der in der Laufzeit geladen.  
  
 Wenn der Typ, der ICorDebugType steht, noch nicht geladen wurde, gibt diese Methode zurück `CORDBG_E_CLASS_NOT_LOADED`.  Wenn der Typ nicht unterstützt wird, gibt es `CORDBG_E_UNSUPPORTED`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugType2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
