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
ms.openlocfilehash: 81640e8e34335898f4dd7f4f43eafbd3ef191d19
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938157"
---
# <a name="strongnamesignatureverificationex2-method"></a>StrongNameSignatureVerificationEx2-Method
Überprüft die Signatur einer Assembly mit starkem Namen und stellt eine Zuordnung zwischen dem ECMA-Schlüssel und einem echten Schlüssel bereit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `wszFilePath`  
 in Der Pfad zur portablen ausführbaren Datei (exe-oder DLL-Datei) für die zu überprüfende Assembly.  
  
 `fForceVerification`  
 [in] `true`, um die Überprüfung auszuführen, auch wenn es erforderlich ist, Registrierungs Einstellungen zu überschreiben. Andernfalls `false`.  
  
 `pbEcmaPublicKey`  
 in Ein Zeiger auf die Zuordnung vom öffentlichen ECMA-Schlüssel zu dem Schlüssel, der für die Überprüfung verwendet wird.  
  
 `cbEcmaPublicKey`  
 in Die Länge des echten öffentlichen ECMA-Schlüssels.  
  
 `pfWasVerified`  
 [out] `true`, wenn die Signatur des starken Namens überprüft wurde. Andernfalls `false`. Dieser Parameter ist auch auf `false` festgelegt, wenn die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Überprüfung erfolgreich war. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameSignatureVerification-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [StrongNameSignatureVerificationEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
