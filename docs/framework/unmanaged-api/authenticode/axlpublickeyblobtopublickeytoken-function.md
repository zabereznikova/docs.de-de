---
title: _AxlPublicKeyBlobToPublicKeyToken-Funktion
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56333165d179abd79e82f1416342a2700029eb12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401673"
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a>_AxlPublicKeyBlobToPublicKeyToken-Funktion
Berechnet den starken Namen des öffentlichen Schlüsseltokens aus einem CSP PUBLICKEYBLOB-Format.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pCspPublicKeyBlob`  
 [in] Der CSP-BLOB des öffentlichen Schlüssels.  
  
 `ppwszPublicKeyHash`  
 [out] Ein Zeiger auf WCHAR *, um den hexadezimal codierten Hash für den öffentlichen Schlüssel zu erhalten.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Funktion erfolgreich ausgeführt wird, sonst `S_FALSE`.  
  
## <a name="see-also"></a>Siehe auch  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
