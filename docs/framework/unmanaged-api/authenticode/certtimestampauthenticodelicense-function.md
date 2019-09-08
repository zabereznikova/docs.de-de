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
ms.openlocfilehash: aaf76d4c3d0f5fb59aeb35fae7a7020ee97b74d6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776479"
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
 [in] Die signierte Authenticode-XrML-Lizenz, die einen Zeitstempel erhalten soll. Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) -Struktur.  
  
 `pwszTimestampURI`  
 [in] Die URL des Zeitstempelservers.  
  
 `pTimestampSignatureBlob`  
 [out] Ein Zeiger auf CRYPT_DATA_BLOB, um die Base64-codierte Zeitstempelsignatur zu erhalten. Es liegt in der Verantwortung des Aufrufers `HepFree()` , nach Verwendung von frei `pTimestampSignatureBlob` -> `pbData` zugeben. Siehe [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) -Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Die Zeitstempelsignatur ist eigentlich eine PKCS #7-SignedData-Nachricht, deren Inhalt die Binärform des SignatureValue aus der Signatur der Lizenz ist. Im Prinzip agiert sie als Gegensignatur für die Lizenz.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Funktion erfolgreich ausgeführt wurde. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch

- [Authenticode](index.md)
