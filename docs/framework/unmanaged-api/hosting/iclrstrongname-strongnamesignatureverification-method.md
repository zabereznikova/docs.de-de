---
title: ICLRStrongName::StrongNameSignatureVerification-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c15b8e416a5070f59a4df44b3e670e2eb9316b5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630549"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a>ICLRStrongName::StrongNameSignatureVerification-Methode
Ruft einen Wert, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält, die gemäß den angegebenen Flags überprüft wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StrongNameSignatureVerification (  
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
  
- `SN_INFLAG_FORCE_VER` (0 x 00000001) - Überprüfung erzwungen, selbst wenn die registrierungseinstellungen außer Kraft gesetzt werden muss.  
  
- `SN_INFLAG_INSTALL` (0 x 00000002) – gibt an, dass dies das erste Mal ist das Manifest wird überprüft.  
  
- `SN_INFLAG_ADMIN_ACCESS` (0 x 00000004) – gibt an, dass der Cache Zugriff nur für Benutzer gewähren, die über Administratorrechte verfügen.  
  
- `SN_INFLAG_USER_ACCESS` (0 x 00000008) – gibt an, dass die Assembly nur auf den aktuellen Benutzer zugreifen kann.  
  
- `SN_INFLAG_ALL_ACCESS` (0 x 00000010) – gibt an, dass der Cache keine Garantie für die zugriffsbeschränkung bereitstellt.  
  
- `SN_INFLAG_RUNTIME` (0 x 80000000) – reserviert für interne Debuggen.  
  
 `pdwOutFlags`  
 [out] Flags, der angibt, ob die starke Namenssignatur überprüft wurde. Der folgende Wert wird unterstützt:  
  
- `SN_OUTFLAG_WAS_VERIFIED` (0 x 00000001) – dieser Wert wird festgelegt, um `false` um anzugeben, dass aufgrund von registrierungseinstellungen für die Überprüfung erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameSignatureVerificationEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
