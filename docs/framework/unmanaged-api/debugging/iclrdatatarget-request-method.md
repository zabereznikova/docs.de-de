---
title: ICLRDataTarget::Request-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.Request
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e0ce905ea21267419e6a68e73f918de8fc364f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetrequest-method"></a>ICLRDataTarget::Request-Methode
Wird von der common Language Runtime (CLR) Daten Access Services zum Anfordern eines Vorgangs aufgerufen, wie durch die Implementierung definiert.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `reqCode`  
 [in] Benutzerdefiniert.  
  
 `inBufferSize`  
 [in] Die Größe des Eingabepuffers, die für die eingehende Anforderung verwendet wird.  
  
 `inBuffer`  
 [in] Ein Puffer, der die Anforderung enthält.  
  
 `outBufferSize`  
 [in] Die Größe des Ausgabepuffers, die für die Antwort verwendet wird.  
  
 `outBuffer`  
 [out] Ein Puffer, die die Antwort enthält.  
  
## <a name="remarks"></a>Hinweise  
 Die `Request` Methode ermöglicht das Hinzufügen von nicht angegebenen benutzerdefinierten Vorgänge. Diese Methode sorgt für Erweiterbarkeit, d. h. ohne Revision der Schnittstellendefinition.  
  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
