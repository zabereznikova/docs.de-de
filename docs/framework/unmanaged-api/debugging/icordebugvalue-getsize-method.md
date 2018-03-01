---
title: ICorDebugValue::GetSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5cf99b35d45c1dda8f187e0206e068c128f347d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluegetsize-method"></a>ICorDebugValue::GetSize-Methode
Ruft die Größe in Bytes des Objekts "ICorDebugValue".  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pSize`  
 [out] Die Größe in Bytes, der dieses Wertobjekt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Typ des Werts ein Verweistyp ist, gibt diese Methode die Größe des Zeigers statt der Größe des Objekts.  
  
 Die `ICorDebugValue::GetSize` -Methode zurückkehrt `COR_E_OVERFLOW` für Objekte, die größer als 4 GB auf 64-Bit-Plattformen sind. Verwenden der [icordebugvalue3:: Getsize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) Methode stattdessen für Objekte, die sind größer als 4 GB.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
    
 [GetSize64-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
