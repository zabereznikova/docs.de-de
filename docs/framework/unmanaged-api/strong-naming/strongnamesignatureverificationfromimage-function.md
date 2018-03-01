---
title: StrongNameSignatureVerificationFromImage-Funktion
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
- StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 178dcbae4f8ec40ac9ef14fc00109c83ab87c21a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignatureverificationfromimage-function"></a>StrongNameSignatureVerificationFromImage-Funktion
Überprüft, ob eine Assembly, die bereits in den Arbeitsspeicher zugeordnet wurde für den zugehörigen öffentlichen Schlüssel gültig ist.  
  
 Diese Funktion ist veraltet. Verwenden der [ICLRStrongName:: StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pbBase`  
 [in] Die relative virtuelle Adresse des zugeordneten Assemblymanifests.  
  
 `dwLength`  
 [in] Die Größe in Bytes, der das zugeordnete Bild.  
  
 `dwInFlags`  
 [in] Flags, die das Überprüfungsverhalten beeinflussen. Die folgenden Werte werden unterstützt:  
  
-   `SN_INFLAG_FORCE_VER`(0 x 00000001) - Überprüfung erzwingt, auch wenn es zum Überschreiben der registrierungseinstellungen für die erforderlich ist.  
  
-   `SN_INFLAG_INSTALL`(0 x 00000002) – gibt an, dass dies die erste Überprüfung für dieses Image ausgeführt wird.  
  
-   `SN_INFLAG_ADMIN_ACCESS`(0 x 00000004) – gibt an, dass der Cache Zugriff nur für Benutzer gewährt wird, die über Administratorrechte verfügen.  
  
-   `SN_INFLAG_USER_ACCESS`(0 x 00000008) – gibt an, dass die Assembly nur auf den aktuellen Benutzer zugreifen kann.  
  
-   `SN_INFLAG_ALL_ACCESS`(0 x 00000010) – gibt an, dass keine Gewährleistung der Einschränkung der Cache bereitstellt.  
  
-   `SN_INFLAG_RUNTIME`(0 x 80000000) - reserviert für interne Debuggen.  
  
 `pdwOutFlags`  
 [out] Ein Flag für zusätzliche Ausgabeinformationen. Der folgende Wert wird unterstützt:  
  
-   `SN_OUTFLAG_WAS_VERIFIED`(0 x 00000001) - dieser Wert wird festgelegt, um `false` um anzugeben, dass die Überprüfung aufgrund der registrierungseinstellungen für die erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`Bei erfolgreichem Abschluss; andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `StrongNameSignatureVerificationFromImage` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** als Ressource in mscoree.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [StrongNameSignatureVerificationFromImage-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
