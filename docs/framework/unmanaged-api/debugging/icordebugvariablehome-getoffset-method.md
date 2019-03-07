---
title: ICorDebugVariableHome::GetOffset-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6880584fe407d651010fad885c2dd5983ad4dfcf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492464"
---
# <a name="icordebugvariablehomegetoffset-method"></a>ICorDebugVariableHome::GetOffset-Methode
Ruft den Offset aus dem Basis-Register für eine Variable ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pOffset`  
 [out] Der Offset aus dem Basis-Register.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Methode gibt die folgenden Werte:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`S_OK`|Die Variable ist in einem Register bezogene-Speicherort.|  
|`E_FAIL`|Die Variable ist nicht in einem Register bezogene-Speicherort.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugVariableHome-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
