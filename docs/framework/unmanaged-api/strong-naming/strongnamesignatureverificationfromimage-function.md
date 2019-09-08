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
ms.openlocfilehash: c22339b7d48e89f99d1500cfdda53f00f1234b80
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799076"
---
# <a name="strongnamesignatureverificationfromimage-function"></a>StrongNameSignatureVerificationFromImage-Funktion
Überprüft, ob eine Assembly, die bereits im Speicher zugeordnet wurde, für den zugehörigen öffentlichen Schlüssel gültig ist.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: strongnameverificationfromimage](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) -Methode.  
  
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
 in Die relative virtuelle Adresse des zugeordneten Assemblymanifests.  
  
 `dwLength`  
 in Die Größe (in Bytes) des zugeordneten Bilds.  
  
 `dwInFlags`  
 in Flags, die das Überprüfungs Verhalten beeinflussen. Die folgenden Werte werden unterstützt:  
  
- `SN_INFLAG_FORCE_VER`(0x00000001): erzwingt die Überprüfung, auch wenn es erforderlich ist, Registrierungs Einstellungen zu überschreiben.  
  
- `SN_INFLAG_INSTALL`(0x00000002): gibt an, dass dies die erste Überprüfung für dieses Bild ist.  
  
- `SN_INFLAG_ADMIN_ACCESS`(0x00000004): gibt an, dass der Cache nur Benutzern mit Administratorrechten Zugriff gestattet.  
  
- `SN_INFLAG_USER_ACCESS`(0x00000008): gibt an, dass die Assembly nur für den aktuellen Benutzer zugänglich ist.  
  
- `SN_INFLAG_ALL_ACCESS`(0x00000010): gibt an, dass der Cache keine Garantien für die Zugriffsbeschränkung bereitstellt.  
  
- `SN_INFLAG_RUNTIME`(0x80000000): reserviert für das interne Debuggen.  
  
 `pdwOutFlags`  
 vorgenommen Ein Flag für zusätzliche Ausgabeinformationen. Der folgende Wert wird unterstützt:  
  
- `SN_OUTFLAG_WAS_VERIFIED`(0x00000001): dieser Wert wird auf `false` festgelegt, um anzugeben, dass die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  
 `true`nach erfolgreichem Abschluss: `false`andernfalls.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `StrongNameSignatureVerificationFromImage` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameSignatureVerificationFromImage-Methode](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
