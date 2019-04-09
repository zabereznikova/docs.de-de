---
title: _AxlRSAKeyValueToPublicKeyToken function
ms.date: 03/30/2017
api_name:
- _AxlRSAKeyValueToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d60f19fe-7bec-47ba-b60e-ba9ce66abf8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49476a4417e5431842f8e2ba0371c53c5c9f03e9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207824"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a>\_AxlRSAKeyValueToPublicKeyToken-Funktion

Konvertiert einen Modulo und Exponenten in einen starken Namen des öffentlichen Schlüsseltokens.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT _AxlRSAKeyValueToPublicKeyToken (  
    [in]  PCRYPT_DATA_BLOB pModulusBlob,  
    [in]  PCRYPT_DATA_BLOB pExponentBlob,  
    [out] LPWSTR           *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pModulusBlob`  
 [in] Der base64-codierte Modulo-Blob (aus der \<Modulus > Element).  Finden Sie unter den [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) Struktur.  
  
 `pExponentBlob`  
 [in] Der base64-codierte Exponenten-Blob (aus der \<Exponent > Element). Finden Sie unter den [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) Struktur.  
  
 `ppwszPublicKeyToken`  
 [out] Ein Zeiger auf WCHAR *, um den hexadezimal codierten öffentlichen Schlüsseltoken zu erhalten.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK` wenn die Funktion erfolgreich ausgeführt wird. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
