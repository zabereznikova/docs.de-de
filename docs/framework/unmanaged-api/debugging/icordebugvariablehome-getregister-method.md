---
title: ICorDebugVariableHome::GetRegister-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetRegister
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f16e4bfe4767e1b49d7dacf0481e8911a90e178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablehomegetregister-method"></a>ICorDebugVariableHome::GetRegister-Methode
Ruft die Registrierung, die eine Variable mit einem Speicherort enthält `VLT_REGISTER`, und die Basisregister für eine Variable mit einem Speicherort `VLT_REGISTER_RELATIVE`.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pRegister`  
 [out] Ein CorDebugRegister-Enumerationswert, der die Registrierung für eine Variable mit einem Speicherort angibt `VLT_REGISTER`, und die Basisregister für eine Variable mit einem Speicherort `VLT_REGISTER_RELATIVE`.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Methode gibt die folgenden Werte zurück:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`S_OK`|Die Variable ist, in dem Register, angegeben durch die `pRegister` Argument.|  
|`E_FAIL`|Die Variable ist nicht in ein Register oder an einem Speicherort relativ zum Registrieren.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [VariableLocationType-Enumeration](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 [ICorDebugVariableHome-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
