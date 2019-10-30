---
title: ICorDebugRegisterSet::GetRegistersAvailable-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
ms.openlocfilehash: 9d8bd6ab13fa408fd7390aaeb76baee274742f48
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137700"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a>ICorDebugRegisterSet::GetRegistersAvailable-Methode
Ruft eine Bitmaske ab, die angibt, welche Register in diesem [icorentbugregisterset](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) zurzeit verfügbar sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAvailable`  
 vorgenommen Eine Bitmaske, die angibt, welche Register zurzeit verfügbar sind.  
  
## <a name="remarks"></a>Hinweise  
 Ein Register ist möglicherweise nicht verfügbar, wenn der Wert für die jeweilige Situation nicht bestimmt werden kann.  
  
 Die zurückgegebene Maske enthält ein Bit für jedes Register (1 < < dem Register Index). Der Bitwert ist 1, wenn das Register verfügbar ist, oder 0, wenn er nicht verfügbar ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRegisterSet-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
