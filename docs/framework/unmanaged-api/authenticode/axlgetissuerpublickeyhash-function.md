---
title: _AxlGetIssuerPublicKeyHash-Funktion
ms.date: 03/30/2017
api_name:
- _AxlGetIssuerPublicKeyHash
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: fb626b41-b888-4625-84c3-2c02b5e3866f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b101a912eb58ed14f81d847ea2fd6ce9f22c065
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787087"
---
# <a name="_axlgetissuerpublickeyhash-function"></a>\_AxlGetIssuerPublicKeyHash-Funktion
Ruft den SHA-1-Hash des öffentlichen Schlüssels ab, der dem privaten Schlüssel zugeordnet wurde, der beim Signieren des festgelegten Zertifikats zur Verwendung kam.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pChainContext`  
 [in] Der Blob für den öffentlichen CSP-Schlüssel Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) -Struktur.  
  
 `ppwszPublicKeyHash`  
 [out] Ein Zeiger auf WCHAR *, um den hexadezimal codierten öffentlichen Schlüsseltoken zu erhalten.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`,wenn die Funktion erfolgreich ausgeführt wird, sonst `S_FALSE`.  
  
## <a name="see-also"></a>Siehe auch

- [Authenticode](index.md)
