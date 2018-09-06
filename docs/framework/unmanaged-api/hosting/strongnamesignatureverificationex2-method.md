---
title: StrongNameSignatureVerificationEx2-Method
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e47c2ac69317b2d2db489dce9a0102b5fe304c05
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856876"
---
# <a name="strongnamesignatureverificationex2-method"></a>StrongNameSignatureVerificationEx2-Method
Überprüft die Signatur einer Assembly mit starkem Namen, und stellt eine Zuordnung zwischen den ECMA-Schlüssel zu einem echten Schlüssel.  
  
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
 [in] Der Pfad der übertragbaren ausführbaren Datei (.exe oder .dll) Datei für die Assembly überprüft werden.  
  
 `fForceVerification`  
 [in] `true` Überprüfung ausführen, auch wenn es ist erforderlich, um registrierungseinstellungen außer Kraft zu setzen ist, andernfalls `false`.  
  
 `pbEcmaPublicKey`  
 [in] Ein Zeiger auf die Zuordnung aus dem öffentlichen Schlüssel der ECMA auf den tatsächlichen Schlüssel, die für die Überprüfung verwendet werden.  
  
 `cbEcmaPublicKey`  
 [in] Die Länge des tatsächlichen ECMA öffentlichen Schlüssels.  
  
 `pfWasVerified`  
 [out] `true` war die starke Namenssignatur überprüft wird; anderenfalls `false`. Dieser Parameter wird auch festgelegt, um `false` , wenn die Überprüfung aufgrund der registrierungseinstellungen für die erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK` Wenn die Überprüfung erfolgreich war; andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [StrongNameSignatureVerification-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [StrongNameSignatureVerificationEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
