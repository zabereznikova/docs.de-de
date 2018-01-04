---
title: StrongNameSignatureVerificationEx2-Method
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location: mscoree.dll
api_type: COM
f1_keywords: StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b4faa7fee32d9cab5a75772f29d2014473e2bee0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignatureverificationex2-method"></a>StrongNameSignatureVerificationEx2-Method
Überprüft die Signatur einer Assembly mit starkem Namen, und stellt eine Zuordnung aus dem ECMA-Schlüssel, um eine tatsächliche Taste bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `wszFilePath`  
 [in] Der Pfad zur portable ausführbare (.exe oder .dll)-Datei für die Assembly überprüft werden.  
  
 `fForceVerification`  
 [in] `true` Überprüfung ausführen, auch wenn es zum Überschreiben der registrierungseinstellungen für die erforderlich ist, andernfalls ist `false`.  
  
 `pbEcmaPublicKey`  
 [in] Ein Zeiger auf die Zuordnung aus dem öffentlichen ECMA-Schlüssel auf den tatsächlichen Schlüssel, die zur Überprüfung verwendet werden.  
  
 `cbEcmaPublicKey`  
 [in] Die Länge des tatsächlichen ECMA öffentlichen Schlüssels.  
  
 `pfWasVerified`  
 [out] `true` war die starke Namenssignatur überprüft wurde, andernfalls `false`. Dieser Parameter ist auch festlegen, um `false` , wenn die Überprüfung aufgrund der registrierungseinstellungen für die erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn die Überprüfung erfolgreich war; andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [StrongNameSignatureVerification-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [StrongNameSignatureVerificationEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
