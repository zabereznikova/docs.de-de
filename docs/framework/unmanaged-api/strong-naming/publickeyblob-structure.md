---
title: PublicKeyBlob-Struktur
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd7a4b19613ea771a055af7dd91ec368859ee191
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529133"
---
# <a name="publickeyblob-structure"></a>PublicKeyBlob-Struktur
Stellt den öffentlichen Schlüssel eines öffentlichen/privaten Schlüsselpaars im binären Format dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`SigAlgId`|Der Bezeichner für den Signaturalgorithmus (des Typs `ALG_ID`gemäß WinCrypt.h) des öffentlichen Schlüssels.|  
|`HashAlgId`|Der Bezeichner für den Hashalgorithmus (des Typs `ALG_ID`gemäß WinCrypt.h) des öffentlichen Schlüssels.|  
|`cbPublicKey`|Die Länge des Schlüssels in Bytes.|  
|`PublicKey`|Ein variabler Länge Bytearray, das den Schlüsselwert in der von der CryptoAPI zurückgegebenen Format enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Die `PublicKeyBlob` Struktur dient der [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), und andere Funktionen zur Darstellung des öffentlichen Schlüssels eines öffentlichen/privaten Schlüsselpaars mit starkem Namen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [StrongNameGetPublicKey-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [StrongNameSignatureGeneration-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [Strukturen für starke Namen](https://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
