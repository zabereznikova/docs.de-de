---
title: CertFreeAuthenticodeTimestamperInfo-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertFreeAuthenticodeTimestamperInfo
api_location: clr.dll
api_type: DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 353bba880cfa8a5ecf9ed826fbb529e31f790a12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a>CertFreeAuthenticodeTimestamperInfo-Funktion
Macht Ressourcen frei der [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pTimestamperInfo`  
 [in, out] Informationen über den Ersteller des Zeitstempels, die veröffentlicht werden sollen. Finden Sie unter der [AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md) Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Funktion erfolgreich ausgeführt wird. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
