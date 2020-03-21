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
ms.openlocfilehash: 336ba38bc80fcb2649a12c78691e52c5e4d70bfe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179111"
---
# <a name="iclrdatatargetrequest-method"></a>ICLRDataTarget::Request-Methode
Wird von den ClR-Datenzugriffsdiensten (Common Language Runtime) aufgerufen, um einen Vorgang anzufordern, wie in der Implementierung definiert.  
  
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
 [in] Benutzerdefinierte.  
  
 `inBufferSize`  
 [in] Die Größe des Eingabepuffers, der für die eingehende Anforderung verwendet wird.  
  
 `inBuffer`  
 [in] Ein Puffer, der die Anforderung enthält.  
  
 `outBufferSize`  
 [in] Die Größe des Ausgabepuffers, der für die Antwort verwendet wird.  
  
 `outBuffer`  
 [out] Ein Puffer, der die Antwort enthält.  
  
## <a name="remarks"></a>Bemerkungen  
 Die `Request` Methode erleichtert das Hinzufügen nicht spezifizierter benutzerdefinierter Vorgänge. Das heißt, diese Methode bietet Erweiterbarkeit, ohne dass eine Überarbeitung der Schnittstellendefinition erforderlich ist.  
  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)
