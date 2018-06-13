---
title: ICorDebugProcess5::GetTypeLayout-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16da3948d89febc12a72ef54fbc060689a3964c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423246"
---
# <a name="icordebugprocess5gettypelayout-method"></a>ICorDebugProcess5::GetTypeLayout-Methode
Ruft Informationen zum Layout eines Objekts im Arbeitsspeicher auf Grundlage seines Bezeichners Typ ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
#### <a name="parameters"></a>Parameter  
 `id`  
 [in] Ein [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Token, das den Typ angibt, deren Layout erwünscht ist.  
  
 `pLayout`  
 [out] Ein Zeiger auf eine [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) -Struktur, die Informationen zum Layout des Objekts im Arbeitsspeicher enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugProcess5::GetTypeLayout` Methode bietet Informationen zu einem Objekt basierend auf seiner [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), der zurückgegeben wird, indem Sie eine Zahl von sonstigen [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) Methoden. Die Informationen werden bereitgestellt, indem eine [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) -Struktur, die von der-Methode aufgefüllt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [COR_TYPE_LAYOUT-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
