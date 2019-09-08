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
ms.openlocfilehash: 8943df861b1bff2b28c68d0233fc336d1b5d4579
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798948"
---
# <a name="strongnamesignatureverification-function"></a>StrongNameSignatureVerification-Funktion
Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält, die gemäß den angegebenen Flags überprüft wird.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
BOOLEAN StrongNameSignatureVerification (  
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
  
- `SN_OUTFLAG_WAS_VERIFIED`(0x00000001): dieser Wert wird auf `false` festgelegt, um anzugeben, dass die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Überprüfung erfolgreich war. `false`andernfalls.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameSignatureVerification-Methode](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [StrongNameSignatureVerificationEx-Methode](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
