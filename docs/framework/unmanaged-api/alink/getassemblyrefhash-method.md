---
title: GetAssemblyRefHash-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetAssemblyRefHash
api_location: alink.dll
api_type: COM
f1_keywords: GetAssemblyRefHash
helpviewer_keywords: GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 99ae38025f223d669a428738783676ebc0687554
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getassemblyrefhash-method"></a>GetAssemblyRefHash-Methode
Ruft ein Hash-Blob für eine bestimmte Assembly ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `FileToken`  
 ID der Assembly, auf die der Hashwert verweisen wird.  
  
 `ppvHash`  
 Erhält die resultierende Hash-Blob.  
  
 `pcbHash`  
 Größe, wird der Hash-Blob in Bytes empfängt.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
