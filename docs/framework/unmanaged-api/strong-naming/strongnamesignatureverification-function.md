---
title: StrongNameSignatureVerification-Funktion
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c398663b84637d2551b0d94bd59b9e0994721ba5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124760"
---
# <a name="strongnamesignatureverification-function"></a>StrongNameSignatureVerification-Funktion
Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält, die gemäß den angegebenen Flags überprüft wird.  
  
 Diese Funktion wurde als veraltet markiert. Verwenden der [ICLRStrongName:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) Methode stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `wszFilePath`  
 [in] Der Pfad der übertragbaren ausführbaren Datei (.dll oder .exe) Datei für die Assembly aus, um zu überprüfen.  
  
 `dwInFlags`  
 [in] Flags, die das Verhalten für die Überprüfung zu ändern. Die folgenden Werte werden unterstützt:  
  
-   `SN_INFLAG_FORCE_VER` (0 x 00000001) - Überprüfung erzwungen, selbst wenn die registrierungseinstellungen außer Kraft gesetzt werden muss.  
  
-   `SN_INFLAG_INSTALL` (0 x 00000002) – gibt an, dass dies das erste Mal ist das Manifest wird überprüft.  
  
-   `SN_INFLAG_ADMIN_ACCESS` (0 x 00000004) – gibt an, dass der Cache Zugriff nur für Benutzer gewähren, die über Administratorrechte verfügen.  
  
-   `SN_INFLAG_USER_ACCESS` (0 x 00000008) – gibt an, dass die Assembly nur auf den aktuellen Benutzer zugreifen kann.  
  
-   `SN_INFLAG_ALL_ACCESS` (0 x 00000010) – gibt an, dass der Cache keine Garantie für die zugriffsbeschränkung bereitstellt.  
  
-   `SN_INFLAG_RUNTIME` (0 x 80000000) – reserviert für interne Debuggen.  
  
 `pdwOutFlags`  
 [out] Flags, der angibt, ob die starke Namenssignatur überprüft wurde. Der folgende Wert wird unterstützt:  
  
-   `SN_OUTFLAG_WAS_VERIFIED` (0 x 00000001) – dieser Wert wird festgelegt, um `false` um anzugeben, dass aufgrund von registrierungseinstellungen für die Überprüfung erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Überprüfung erfolgreich war; andernfalls `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameSignatureVerification-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [StrongNameSignatureVerificationEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
