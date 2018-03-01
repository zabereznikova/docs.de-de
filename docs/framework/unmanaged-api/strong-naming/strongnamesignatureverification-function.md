---
title: StrongNameSignatureVerification-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0950efd6c5323aa6a0cd2f1455ac3226b21a2b92
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignatureverification-function"></a>StrongNameSignatureVerification-Funktion
Ruft einen Wert, der angibt, ob das Assemblymanifest im angegebenen Pfad eine starke Namenssignatur enthält, die gemäß den angegebenen Flags überprüft wird.  
  
 Diese Funktion ist veraltet. Verwenden der [ICLRStrongName:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `wszFilePath`  
 [in] Der Pfad zur portable ausführbare (.dll oder .exe)-Datei für die Assembly aus, um zu überprüfen.  
  
 `dwInFlags`  
 [in] Flags, um das Verhalten für die Überprüfung zu ändern. Die folgenden Werte werden unterstützt:  
  
-   `SN_INFLAG_FORCE_VER`(0 x 00000001) - Überprüfung erzwingt, auch wenn es zum Überschreiben der registrierungseinstellungen für die erforderlich ist.  
  
-   `SN_INFLAG_INSTALL`(0 x 00000002) – gibt an, dass dies das erste Mal ist das Manifest wird überprüft.  
  
-   `SN_INFLAG_ADMIN_ACCESS`(0 x 00000004) – gibt an, dass der Cache Zugriff nur für Benutzer gewährt wird, die über Administratorrechte verfügen.  
  
-   `SN_INFLAG_USER_ACCESS`(0 x 00000008) – gibt an, dass die Assembly nur auf den aktuellen Benutzer zugreifen kann.  
  
-   `SN_INFLAG_ALL_ACCESS`(0 x 00000010) – gibt an, dass keine Gewährleistung der Einschränkung der Cache bereitstellt.  
  
-   `SN_INFLAG_RUNTIME`(0 x 80000000) - reserviert für interne Debuggen.  
  
 `pdwOutFlags`  
 [out] Flags, die angibt, ob die Signatur mit starkem Namen überprüft wurde. Der folgende Wert wird unterstützt:  
  
-   `SN_OUTFLAG_WAS_VERIFIED`(0 x 00000001) - dieser Wert wird festgelegt, um `false` um anzugeben, dass die Überprüfung aufgrund der registrierungseinstellungen für die erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Überprüfung erfolgreich war; andernfalls `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [StrongNameSignatureVerification-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [StrongNameSignatureVerificationEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
