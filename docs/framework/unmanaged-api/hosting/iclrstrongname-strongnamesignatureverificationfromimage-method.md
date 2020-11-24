---
title: ICLRStrongName::StrongNameSignatureVerificationFromImage-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type:
- apiref
ms.openlocfilehash: 134b32b6b281a08997849f4c23edfc1f357dadcd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674397"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a>ICLRStrongName::StrongNameSignatureVerificationFromImage-Methode

Überprüft, ob eine Assembly, die bereits im Speicher zugeordnet wurde, für den zugehörigen öffentlichen Schlüssel gültig ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT StrongNameSignatureVerificationFromImage (  
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
  
- `SN_INFLAG_FORCE_VER` (0x00000001): erzwingt die Überprüfung, auch wenn es erforderlich ist, Registrierungs Einstellungen zu überschreiben.  
  
- `SN_INFLAG_INSTALL` (0x00000002): gibt an, dass dies die erste Überprüfung für dieses Bild ist.  
  
- `SN_INFLAG_ADMIN_ACCESS` (0x00000004): gibt an, dass der Cache nur Benutzern mit Administratorrechten Zugriff gestattet.  
  
- `SN_INFLAG_USER_ACCESS` (0x00000008): gibt an, dass die Assembly nur für den aktuellen Benutzer zugänglich ist.  
  
- `SN_INFLAG_ALL_ACCESS` (0x00000010): gibt an, dass der Cache keine Garantien für die Zugriffsbeschränkung bereitstellt.  
  
- `SN_INFLAG_RUNTIME` (0x80000000): reserviert für das interne Debuggen.  
  
 `pdwOutFlags`  
 vorgenommen Ein Flag für zusätzliche Ausgabeinformationen. Der folgende Wert wird unterstützt:  
  
- `SN_OUTFLAG_WAS_VERIFIED` (0x00000001): dieser Wert wird auf festgelegt, `false` um anzugeben, dass die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.  
  
## <a name="return-value"></a>Rückgabewert  

 `S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRStrongName-Schnittstelle](iclrstrongname-interface.md)
