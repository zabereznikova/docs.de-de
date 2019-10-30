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
ms.openlocfilehash: 6c58a0726e0869178838999c6b000e0ad975f145
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140609"
---
# <a name="publickeyblob-structure"></a>PublicKeyBlob-Struktur
Stellt den öffentlichen Schlüssel eines öffentlichen/privaten Schlüssel Paars im Binärformat dar.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
|`SigAlgId`|Der Bezeichner für den Signatur Algorithmus (vom Typ `ALG_ID`, wie in Wincrypt. h definiert) des öffentlichen Schlüssels.|  
|`HashAlgId`|Der Bezeichner für den Hash Algorithmus (vom Typ `ALG_ID`, wie in Wincrypt. h definiert) des öffentlichen Schlüssels.|  
|`cbPublicKey`|Die Länge des Schlüssels in Bytes.|  
|`PublicKey`|Ein Bytearray variabler Länge, das den Schlüsselwert in dem Format enthält, das von der CryptoAPI zurückgegeben wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `PublicKeyBlob` Struktur wird von [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)und anderen starken Namens Funktionen verwendet, um den öffentlichen Schlüssel eines öffentlichen/privaten Schlüssel Paars darzustellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameGetPublicKey-Funktion](strongnamegetpublickey-function.md)
- [StrongNameSignatureGeneration-Funktion](strongnamesignaturegeneration-function.md)
