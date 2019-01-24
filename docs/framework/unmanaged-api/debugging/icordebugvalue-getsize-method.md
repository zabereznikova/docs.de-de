---
title: ICorDebugValue::GetSize-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb0030a25dd48ab4236ec2b51891e0ac41aac902
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612618"
---
# <a name="icordebugvaluegetsize-method"></a>ICorDebugValue::GetSize-Methode
Ruft die Größe des dieses "ICorDebugValue"-Objekts in Bytes ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pSize`  
 [out] Die Größe des dieses Wertobjekts in Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Typ des Werts ein Verweistyp ist, gibt diese Methode auf, die Größe des Zeigers, anstatt die Größe des Objekts.  
  
 Die `ICorDebugValue::GetSize` Methodenrückgabe `COR_E_OVERFLOW` für Objekte, die größer als 4 GB auf 64-Bit-Plattformen sind. Verwenden der [icordebugvalue3:: Getsize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) Methode stattdessen für Objekte, die größer sind als 4 GB.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetSize64-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
