---
title: CertTimestampAuthenticodeLicense-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertTimestampAuthenticodeLicense
api_location: clr.dll
api_type: DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ec863e9accbd2156b6eeed5857ff86075cf0a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
 [in] Die signierte Authenticode-XrML-Lizenz, die einen Zeitstempel erhalten soll. Finden Sie unter der [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) Struktur.  
  
 `pwszTimestampURI`  
 [in] Die URL des Zeitstempelservers.  
  
 `pTimestampSignatureBlob`  
 [out] Ein Zeiger auf CRYPT_DATA_BLOB, um die Base64-codierte Zeitstempelsignatur zu erhalten. Es ist Aufgabe des Aufrufers frei `pTimestampSignatureBlob` -> `pbData` mit `HepFree()` nach ihrer Verwendung. Finden Sie unter der [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) Struktur.  
  
## <a name="remarks"></a>Hinweise  
 Die Zeitstempelsignatur ist eigentlich eine PKCS #7-SignedData-Nachricht, deren Inhalt die Binärform des SignatureValue aus der Signatur der Lizenz ist. Im Prinzip agiert sie als Gegensignatur für die Lizenz.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Funktion erfolgreich ausgeführt wird. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
