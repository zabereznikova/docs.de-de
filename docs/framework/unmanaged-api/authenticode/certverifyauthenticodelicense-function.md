---
title: CertVerifyAuthenticodeLicense-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertVerifyAuthenticodeLicense
api_location: clr.dll
api_type: DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16d8067b4cd5d0a7b3db5be5b3b9ed4d689e1b0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="certverifyauthenticodelicense-function"></a>CertVerifyAuthenticodeLicense-Funktion
Überprüft die Gültigkeit einer Authenticode XrML-Lizenz.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pLicenseBlob`  
 [in] Die Authenticode-XrML-Lizenz, die überprüft werden soll.  
  
 Finden Sie unter der [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) Struktur.  
  
 `dwFlags`  
 [in] Optional. Eine Kombination der folgenden Werte:  
  
-   AXL_REVOCATION_NO_CHECK  
  
-   AXL_REVOCATION_CHECK_END_CERT_ONLY  
  
-   AXL_REVOCATION_CHECK_ENTIRE_CHAIN  
  
-   AXL_URL_CACHE_ONLY_RETRIEVAL  
  
-   AXL_LIFETIME_SIGNING  
  
-   AXL_TRUST_MICROSOFT_ROOT_ONLY  
  
 `pSignerInfo`  
 [out] Für den Erhalt von Informationen über den Signaturgeber. Wenn die Lizenz nicht signiert wurde, ist `dwError` auf TRUST_E_NOSIGNATURE eingestellt. Es ist der Verantwortung des Aufrufers zum Freigeben von Ressourcen mithilfe der [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) Funktion nach der Verwendung.  
  
 Finden Sie unter [AXL_AUTHENTICODE_SIGNER_INFO-Struktur](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).  
  
 `pTimestamperInfo`  
 [out] Für den Erhalt von Informationen über den Ersteller des Zeitstempels, wenn verfügbar. Wenn die Lizenz keinen Zeitstempel erhalten hat, ist `dwError` auf TRUST_E_NOSIGNATURE eingestellt. Es ist der Verantwortung des Aufrufers zum Freigeben von Ressourcen mithilfe der [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) Funktion nach der Verwendung.  
  
 Finden Sie unter [AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt bei Erfolg `S_OK` zurück. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)  
 [GetHashFromHandle-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
