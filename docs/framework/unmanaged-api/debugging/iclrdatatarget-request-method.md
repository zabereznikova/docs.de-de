---
title: ICLRDataTarget::Request-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
ms.openlocfilehash: e5d7a6b9826a734363d6beeb2e3fab8422964558
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113356"
---
# <a name="iclrdatatargetrequest-method"></a>ICLRDataTarget::Request-Methode
Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um einen Vorgang anzufordern, wie in der-Implementierung definiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `reqCode`  
 in Benutzer definiert.  
  
 `inBufferSize`  
 in Die Größe des Eingabe Puffers, der für die eingehende Anforderung verwendet wird.  
  
 `inBuffer`  
 in Ein Puffer, der die Anforderung enthält.  
  
 `outBufferSize`  
 in Die Größe des Ausgabepuffers, der für die Antwort verwendet wird.  
  
 `outBuffer`  
 vorgenommen Ein Puffer, der die Antwort enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die `Request`-Methode vereinfacht das Hinzufügen von nicht angegebenen benutzerdefinierten Vorgängen. Das heißt, diese Methode bietet Erweiterbarkeit, ohne dass eine Revision der Schnittstellen Definition erforderlich ist.  
  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
