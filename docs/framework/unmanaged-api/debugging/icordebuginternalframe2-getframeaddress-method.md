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
ms.openlocfilehash: 05a9ab58acb3bf5829fd231ae6d8bcc96ae06da6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724870"
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
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Adresse des internen Frames wurde erfolgreich zurückgegeben.|  
|E_FAIL|Die Adresse des internen Frames konnte nicht zurückgegeben werden.|  
|E_INVALIDARG|`pAddress` ist `null`.|  
  
## <a name="remarks"></a>Hinweise  

 Der Wert, der in zurückgegeben `pAddress` wird, kann verwendet werden, um den Speicherort des internen Frames in Relation zu anderen Frames im Stapel zu bestimmen. Selbst bei IA-64-basierten Computern befindet sich der interne Frame nur im Stapel, und es gibt keinen entsprechenden Zeiger auf einen Sicherungs Speicher.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugInternalFrame2-Schnittstelle](icordebuginternalframe2-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
