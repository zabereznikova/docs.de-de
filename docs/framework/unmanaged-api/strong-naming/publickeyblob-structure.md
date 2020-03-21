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
ms.openlocfilehash: 3b00bf8295a635871bd7263928ff21c97053cc39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176954"
---
# <a name="publickeyblob-structure"></a>PublicKeyBlob-Struktur
Stellt im Binärformat den öffentlichen Schlüssel eines öffentlichen/privaten Schlüsselpaars dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a>Members  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`SigAlgId`|Der Bezeichner für den `ALG_ID`Signaturalgorithmus (vom Typ , wie in WinCrypt.h definiert) des öffentlichen Schlüssels.|  
|`HashAlgId`|Der Bezeichner für den `ALG_ID`Hashalgorithmus (vom Typ , wie in WinCrypt.h definiert) des öffentlichen Schlüssels.|  
|`cbPublicKey`|Die Länge des Schlüssels in Bytes.|  
|`PublicKey`|Ein Bytearray variabler Länge, das den Schlüsselwert in dem von der CryptoAPI zurückgegebenen Format enthält.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die `PublicKeyBlob` Struktur wird von [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)und anderen Funktionen mit starkem Namen verwendet, um den öffentlichen Schlüssel eines öffentlichen/privaten Schlüsselpaars darzustellen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Kopfzeile:** StrongName.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameGetPublicKey-Funktion](strongnamegetpublickey-function.md)
- [StrongNameSignatureGeneration-Funktion](strongnamesignaturegeneration-function.md)
