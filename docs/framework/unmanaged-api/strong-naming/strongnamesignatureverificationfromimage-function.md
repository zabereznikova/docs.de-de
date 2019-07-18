---
title: StrongNameSignatureVerificationFromImage-Funktion
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df2eb9d454f2037ef5f2a09d1309d52a8365e715
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782690"
---
# <a name="strongnamesignatureverificationfromimage-function"></a>StrongNameSignatureVerificationFromImage-Funktion
Überprüft, ob eine Assembly, die bereits im Speicher zugeordnet wurde, für den zugehörigen öffentlichen Schlüssel gültig ist.  
  
 Diese Funktion wurde als veraltet markiert. Verwenden der [ICLRStrongName:: StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbBase`  
 [in] Die relative virtuelle Adresse des Assemblymanifests zugeordnet.  
  
 `dwLength`  
 [in] Die Größe in Bytes, der das zugeordnete Bild.  
  
 `dwInFlags`  
 [in] Flags, die Überprüfung Verhalten zu beeinflussen. Die folgenden Werte werden unterstützt:  
  
- `SN_INFLAG_FORCE_VER` (0 x 00000001) - Überprüfung erzwungen, selbst wenn die registrierungseinstellungen außer Kraft gesetzt werden muss.  
  
- `SN_INFLAG_INSTALL` (0 x 00000002) – gibt an, dass dies die erste überprüfungsanforderung für dieses Image ausgeführt wird.  
  
- `SN_INFLAG_ADMIN_ACCESS` (0 x 00000004) – gibt an, dass der Cache Zugriff nur für Benutzer gewähren, die über Administratorrechte verfügen.  
  
- `SN_INFLAG_USER_ACCESS` (0 x 00000008) – gibt an, dass die Assembly nur auf den aktuellen Benutzer zugreifen kann.  
  
- `SN_INFLAG_ALL_ACCESS` (0 x 00000010) – gibt an, dass der Cache keine Garantie für die zugriffsbeschränkung bereitstellt.  
  
- `SN_INFLAG_RUNTIME` (0 x 80000000) – reserviert für interne Debuggen.  
  
 `pdwOutFlags`  
 [out] Ein Flag für zusätzliche ausgegebenen Informationen. Der folgende Wert wird unterstützt:  
  
- `SN_OUTFLAG_WAS_VERIFIED` (0 x 00000001) – dieser Wert wird festgelegt, um `false` um anzugeben, dass aufgrund von registrierungseinstellungen für die Überprüfung erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Bei erfolgreichem Abschluss; andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `StrongNameSignatureVerificationFromImage` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** Als Ressource in mscoree.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameSignatureVerificationFromImage-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
