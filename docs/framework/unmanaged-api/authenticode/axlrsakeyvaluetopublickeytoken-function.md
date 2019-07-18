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
ms.openlocfilehash: 4f9981c4cf2e45795576024b797f93831324dbc9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741270"
---
# <a name="axlrsakeyvaluetopublickeytoken-function"></a>\_AxlRSAKeyValueToPublicKeyToken-Funktion

Konvertiert einen Modulo und Exponenten in einen starken Namen des öffentlichen Schlüsseltokens.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 `S_OK`, wenn die Funktion erfolgreich ausgeführt wurde. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch

- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
