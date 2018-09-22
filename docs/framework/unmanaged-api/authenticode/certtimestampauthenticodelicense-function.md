---
title: CertTimestampAuthenticodeLicense-Funktion
ms.date: 03/30/2017
api_name:
- CertTimestampAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd77a8a81718837d55f3018564d0f4ba8fdc95ee
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46695897"
---
# <a name="certtimestampauthenticodelicense-function"></a>CertTimestampAuthenticodeLicense-Funktion
Fügt einer Authenticode-XrML-Lizenz einen Zeitstempel hinzu.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pSignedLicenseBlob`  
 [in] Die signierte Authenticode-XrML-Lizenz, die einen Zeitstempel erhalten soll. Finden Sie unter den [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) Struktur.  
  
 `pwszTimestampURI`  
 [in] Die URL des Zeitstempelservers.  
  
 `pTimestampSignatureBlob`  
 [out] Ein Zeiger auf CRYPT_DATA_BLOB, um die Base64-codierte Zeitstempelsignatur zu erhalten. Es ist der Verantwortung des Aufrufers freigeben `pTimestampSignatureBlob` -> `pbData` mit `HepFree()` nach ihrer Verwendung. Finden Sie unter den [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Die Zeitstempelsignatur ist eigentlich eine PKCS #7-SignedData-Nachricht, deren Inhalt die Binärform des SignatureValue aus der Signatur der Lizenz ist. Im Prinzip agiert sie als Gegensignatur für die Lizenz.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Funktion erfolgreich ausgeführt wird. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
