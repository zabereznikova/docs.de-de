---
title: ICorDebugInternalFrame2::GetFrameAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
ms.openlocfilehash: 40e64bdb35cff4e6ad6132c0806cfddd2767443c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122673"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a>ICorDebugInternalFrame2::GetFrameAddress-Methode
Gibt die Stapel Adresse des internen Frames zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAddress`  
 vorgenommen Zeiger auf den `CORDB_ADDRESS` für den internen Frame.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Adresse des internen Frames wurde erfolgreich zurückgegeben.|  
|E_FAIL|Die Adresse des internen Frames konnte nicht zurückgegeben werden.|  
|E_INVALIDARG|`pAddress` ist `null`.|  
  
## <a name="remarks"></a>Hinweise  
 Der in `pAddress` zurückgegebene Wert kann verwendet werden, um den Speicherort des internen Frames relativ zu anderen Frames im Stapel zu bestimmen. Selbst bei IA-64-basierten Computern befindet sich der interne Frame nur im Stapel, und es gibt keinen entsprechenden Zeiger auf einen Sicherungs Speicher.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugInternalFrame2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
