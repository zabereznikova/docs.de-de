---
title: ICLRDebugging::CanUnloadNow-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebugging.CanUnloadNow Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type:
- apiref
ms.openlocfilehash: e89d936c528ea7482487a8629dbd882f6f67483e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723570"
---
# <a name="iclrdebuggingcanunloadnow-method"></a>ICLRDebugging::CanUnloadNow-Methode

Bestimmt, ob eine Bibliothek, die von einer [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) -Schnittstelle bereitgestellt wurde, noch verwendet wird oder entladen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
## <a name="parameters"></a>Parameter  

 `hmodule`  
 in Die Basisadresse eines Moduls im Ziel Prozess.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Das Modul, auf das von verwiesen wird, `hmodule` kann entladen werden.|  
|S_FALSE|Das Modul, auf das von verwiesen wird, `hmodule` wird weiterhin verwendet.|  
|COR_E_NOT_CLR|Das gekennzeichnete Modul ist kein CLR-Modul.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Bemerkungen  

 Diese Methode überprüft, ob alle Instanzen von `ICorDebug*` Schnittstellen freigegeben wurden und derzeit kein Thread in einem Aufrufen der [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) -Methode ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
