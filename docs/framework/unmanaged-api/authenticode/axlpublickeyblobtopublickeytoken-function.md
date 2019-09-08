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
ms.openlocfilehash: b4d720480e4c8b21b3aa56ce81634a26ac9c75de
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776675"
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
  
## <a name="see-also"></a>Siehe auch

- [Authenticode](index.md)
