---
title: GetPublicKeyToken-Methode
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d1b28eadc9f09abff799f99d1d6012c98b1d3dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215767"
---
# <a name="getpublickeytoken-method"></a>GetPublicKeyToken-Methode
Ruft das Token des öffentlichen Schlüssels für eine angegebene Schlüsseldatei oder Schlüsselcontainer ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  
 `pszKeyFile`  
 Der Dateiname des Schlüssels.  
  
 `pszKeyContainer`  
 Der Name des Schlüsselcontainers.  
  
 `pvPublicKeyToken`  
 Die Adresse, in dem Token des Schlüssels ist, gespeichert werden.  
  
 `pcbPublicKeyToken`  
 Gibt die Größe in Byte des Puffers erkennbar `pvPublicKeyToken`. Enthält bei der Rückgabe die tatsächliche Anzahl von Bytes verwendet.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h an.  
  
## <a name="see-also"></a>Siehe auch

- [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [ALink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
