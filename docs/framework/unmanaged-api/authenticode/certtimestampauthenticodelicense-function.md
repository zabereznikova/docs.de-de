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
ms.openlocfilehash: fc1a99572406a38aee8133d6435134b78a134175
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674098"
---
# <a name="certtimestampauthenticodelicense-function"></a>CertTimestampAuthenticodeLicense-Funktion

Fügt einer Authenticode-XrML-Lizenz einen Zeitstempel hinzu.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pSignedLicenseBlob`  
 [in] Die signierte Authenticode-XrML-Lizenz, die einen Zeitstempel erhalten soll. Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) Struktur.  
  
 `pwszTimestampURI`  
 [in] Die URL des Zeitstempelservers.  
  
 `pTimestampSignatureBlob`  
 [out] Ein Zeiger auf CRYPT_DATA_BLOB, um die Base64-codierte Zeitstempelsignatur zu erhalten. Es liegt in der Verantwortung des Aufrufers, `pTimestampSignatureBlob` -> `pbData` nach Verwendung von freizugeben `HepFree()` . Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) Struktur.  
  
## <a name="remarks"></a>Hinweise  

 Die Zeitstempelsignatur ist eigentlich eine PKCS #7-SignedData-Nachricht, deren Inhalt die Binärform des SignatureValue aus der Signatur der Lizenz ist. Im Prinzip agiert sie als Gegensignatur für die Lizenz.  
  
## <a name="return-value"></a>Rückgabewert  

 `S_OK`, wenn die Funktion erfolgreich ausgeführt wurde. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Weitere Informationen

- [Authenticode](index.md)
