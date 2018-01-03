---
title: GetPublicKeyToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetPublicKeyToken
api_location: alink.dll
api_type: COM
f1_keywords: GetPublicKeyToken
helpviewer_keywords: GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 230c98e85bd0aa3bd2f368965b6f7ac028e43df4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getpublickeytoken-method"></a>GetPublicKeyToken-Methode
Ruft das Token des öffentlichen Schlüssels für eine angegebene Schlüsseldatei oder eines Schlüsselcontainers ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `pszKeyFile`  
 Der Dateiname des Schlüssels.  
  
 `pszKeyContainer`  
 Der Name des Schlüsselcontainers.  
  
 `pvPublicKeyToken`  
 Adresse des Standorts Schlüsseltoken gespeichert werden soll.  
  
 `pcbPublicKeyToken`  
 Gibt die Größe in Bytes, des Puffers erkennbar `pvPublicKeyToken`. Enthält bei der Rückgabe die tatsächliche Anzahl von Bytes verwendet.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h.  
  
## <a name="see-also"></a>Siehe auch  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
