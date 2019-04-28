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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9005dd8fde0d7258bd1dd48b561e4925e87733b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698069"
---
# <a name="iclrdatatargetrequest-method"></a>ICLRDataTarget::Request-Methode
Aufgerufen von der common Language Runtime (CLR) Datenzugriffsdiensten der zum Anfordern eines Vorgangs, wie durch die Implementierung definiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Vom Benutzer definiert.  
  
 `inBufferSize`  
 [in] Die Größe des Eingabepuffers, die für die eingehende Anforderung verwendet wird.  
  
 `inBuffer`  
 [in] Ein Puffer, der die Anforderung enthält.  
  
 `outBufferSize`  
 [in] Die Größe des Ausgabepuffers, die für die Antwort verwendet wird.  
  
 `outBuffer`  
 [out] Ein Puffer mit der Antwort.  
  
## <a name="remarks"></a>Hinweise  
 Die `Request` Methode ermöglicht das Hinzufügen nicht angegebener benutzerdefinierter Vorgänge. Diese Methode, also bereitstellt Erweiterbarkeit ohne Revision der Definition der Schnittstelle.  
  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
