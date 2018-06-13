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
ms.openlocfilehash: b197aa539e60a9dbcee55cf190c44b45da3a5fb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402014"
---
# <a name="axlgetissuerpublickeyhash-function"></a>_AxlGetIssuerPublicKeyHash-Funktion
Ruft den SHA-1-Hash des öffentlichen Schlüssels ab, der dem privaten Schlüssel zugeordnet wurde, der beim Signieren des festgelegten Zertifikats zur Verwendung kam.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT _AxlGetIssuerPublicKeyHash (  
    [in]  IN PCRYPT_DATA_BLOB   pChainContext,  
    [out] LPWSTR                *ppwszPublicKeyHash  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pChainContext`  
 [in] Der CSP-BLOB des öffentlichen Schlüssels. Finden Sie unter der [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) Struktur.  
  
 `ppwszPublicKeyHash`  
 [out] Ein Zeiger auf WCHAR * zum Erhalt des hexadezimal codierten öffentlichen Schlüsseltokens.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Funktion erfolgreich ausgeführt wird, sonst `S_FALSE`.  
  
## <a name="see-also"></a>Siehe auch  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
