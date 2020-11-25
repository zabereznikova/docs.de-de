---
title: ICLRDataTarget3::GetExceptionThreadID-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
ms.openlocfilehash: 0a8b7a90cd909379f870f6a501a940386d2e1451
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723596"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a>ICLRDataTarget3::GetExceptionThreadID-Methode

Wird durch die Common Language Runtime (CLR)-Datenzugriffsdienste aufgerufen, um die ID des Threads abzurufen, der die Ausnahme ausgelöst hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `threadID`  
 [out] Die ID des Threads, der die Ausnahme ausgelöst hat.  
  
## <a name="return-value"></a>Rückgabewert  

 Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler. Zu den `HRESULT`-Codes können u. a. folgende Codes gehören:  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|`S_OK`|Methode war erfolgreich.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Für die Ausnahme konnte keine gültige Thread-ID gefunden werden.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRDataTarget3-Schnittstelle](iclrdatatarget3-interface.md)
- [GetExceptionContextRecord-Methode](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [GetExceptionRecord-Methode](iclrdatatarget3-getexceptionrecord-method.md)
