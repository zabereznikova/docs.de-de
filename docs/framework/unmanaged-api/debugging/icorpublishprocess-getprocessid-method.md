---
title: ICorPublishProcess::GetProcessID-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.GetProcessID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a048255e075b01f4c3c7635038b22ab581032524
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessgetprocessid-method"></a>ICorPublishProcess::GetProcessID-Methode
Ruft den Bezeichner des Betriebssystems für diesen Prozess ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pid`  
 [out] Ein Zeiger auf den Bezeichner des Prozesses, der von diesem dargestellt [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorPublishProcess-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
