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
ms.openlocfilehash: d31c9c0db306aad3a7c3472ef6329f25aa6c5902
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762655"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a>ICLRStrongName::StrongNameSignatureVerification-Methode
Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält, die entsprechend den angegebenen Flags überprüft wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `wszFilePath`  
 in Der Pfad zur portablen ausführbaren Datei (dll-oder exe-Datei) für die zu überprüfende Assembly.  
  
 `dwInFlags`  
 in Flags zum Ändern des Überprüfungs Verhaltens. Die folgenden Werte werden unterstützt:  
  
- `SN_INFLAG_FORCE_VER`(0x00000001): erzwingt die Überprüfung, auch wenn es erforderlich ist, Registrierungs Einstellungen zu überschreiben.  
  
- `SN_INFLAG_INSTALL`(0x00000002): gibt an, dass dies das erste Mal ist, wenn das Manifest überprüft wird.  
  
- `SN_INFLAG_ADMIN_ACCESS`(0x00000004): gibt an, dass der Cache nur Benutzern mit Administratorrechten Zugriff gestattet.  
  
- `SN_INFLAG_USER_ACCESS`(0x00000008): gibt an, dass die Assembly nur für den aktuellen Benutzer zugänglich ist.  
  
- `SN_INFLAG_ALL_ACCESS`(0x00000010): gibt an, dass der Cache keine Garantien für die Zugriffsbeschränkung bereitstellt.  
  
- `SN_INFLAG_RUNTIME`(0x80000000): reserviert für das interne Debuggen.  
  
 `pdwOutFlags`  
 vorgenommen Flags, die angeben, ob die starke namens Signatur überprüft wurde. Der folgende Wert wird unterstützt:  
  
- `SN_OUTFLAG_WAS_VERIFIED`(0x00000001): dieser Wert wird auf festgelegt, `false` um anzugeben, dass die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameSignatureVerificationEx-Methode](iclrstrongname-strongnamesignatureverificationex-method.md)
- [ICLRStrongName-Schnittstelle](iclrstrongname-interface.md)
