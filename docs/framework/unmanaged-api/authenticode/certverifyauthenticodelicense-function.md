---
title: CertVerifyAuthenticodeLicense-Funktion
ms.date: 03/30/2017
api_name:
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
ms.openlocfilehash: 388814d1c63f048c0aa231a1d0058a390cba9493
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674059"
---
# <a name="certverifyauthenticodelicense-function"></a>CertVerifyAuthenticodeLicense-Funktion

Überprüft die Gültigkeit einer Authenticode-XrML-Lizenz.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pLicenseBlob`  
 [in] Die Authenticode-XrML-Lizenz, die überprüft werden soll.  
  
 Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) Struktur.  
  
 `dwFlags`  
 [in] Optional. Eine Kombination der folgenden Werte:  
  
- AXL_REVOCATION_NO_CHECK  
  
- AXL_REVOCATION_CHECK_END_CERT_ONLY  
  
- AXL_REVOCATION_CHECK_ENTIRE_CHAIN  
  
- AXL_URL_CACHE_ONLY_RETRIEVAL  
  
- AXL_LIFETIME_SIGNING  
  
- AXL_TRUST_MICROSOFT_ROOT_ONLY  
  
 `pSignerInfo`  
 [out] Für den Erhalt von Informationen über den Signaturgeber. Wenn die Lizenz nicht signiert wurde, ist `dwError` auf TRUST_E_NOSIGNATURE eingestellt. Es liegt in der Verantwortung des Aufrufers, mithilfe der [CertFreeAuthenticodeSignerInfo](certfreeauthenticodesignerinfo-function.md) -Funktion Ressourcen freizugeben, nachdem er verwendet wurde.  
  
 Siehe [AXL_AUTHENTICODE_SIGNER_INFO Struktur](axl-authenticode-signer-info-structure.md).  
  
 `pTimestamperInfo`  
 [out] Für den Erhalt von Informationen über den Ersteller des Zeitstempels, wenn verfügbar. Wenn die Lizenz keinen Zeitstempel erhalten hat, ist `dwError` auf TRUST_E_NOSIGNATURE eingestellt. Es liegt in der Verantwortung des Aufrufers, Ressourcen mithilfe der [certfreeauthenticodetimestamperinfo](certfreeauthenticodetimestamperinfo-function.md) -Funktion nach der Verwendung freizugeben.  
  
 Siehe [AXL_AUTHENTICODE_TIMESTAMPER_INFO Struktur](axl-authenticode-timestamper-info-structure.md).  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt bei Erfolg `S_OK` zurück. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Weitere Informationen

- [Authenticode](index.md)
- [GetHashFromHandle-Methode](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
