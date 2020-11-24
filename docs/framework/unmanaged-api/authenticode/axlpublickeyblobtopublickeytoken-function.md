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
ms.openlocfilehash: 989e99198efd1519f607a2e3164ff4de584e88af
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679883"
---
# <a name="_axlpublickeyblobtopublickeytoken-function"></a>\_Axlpublickeyblobtopublickeytoken-Funktion

Berechnet das öffentliche Schlüsseltoken für einen starken Namen aus einem CSP PUBLICKEYBLOB-Format.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pCspPublicKeyBlob`  
 [in] Der Blob für den öffentlichen CSP-Schlüssel  
  
 `ppwszPublicKeyHash`  
 [out] Ein Zeiger auf WCHAR *, um den hexadezimal codierten Hash für den öffentlichen Schlüssel zu erhalten.  
  
## <a name="return-value"></a>Rückgabewert  

 `S_OK`,wenn die Funktion erfolgreich ausgeführt wird, sonst `S_FALSE`.  
  
## <a name="see-also"></a>Weitere Informationen

- [Authenticode](index.md)
