---
title: PublicKeyBlob-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PublicKeyBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: PublicKeyBlob
helpviewer_keywords: PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e273570c77b2855d942db580be95b040870a4c01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
|`SigAlgId`|Der Bezeichner für den Signaturalgorithmus (vom Typ `ALG_ID`, wie in WinCrypt.h definiert) des öffentlichen Schlüssels.|  
|`HashAlgId`|Der Bezeichner für die Hash-Algorithmus (des Typs `ALG_ID`, wie in WinCrypt.h definiert) des öffentlichen Schlüssels.|  
|`cbPublicKey`|Die Länge des Schlüssels in Bytes.|  
|`PublicKey`|Ein variabler Länge Bytearray, das den Schlüsselwert in der von der Crypto-API zurückgegebenen Format enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Die `PublicKeyBlob` Struktur dient der [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), und anderen Funktionen zur Darstellung des öffentlichen Schlüssels des ein öffentliches/privates Schlüsselpaar mit starkem Namen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** StrongName.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [StrongNameGetPublicKey-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [StrongNameSignatureGeneration-Funktion](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [Strukturen für starke Namen](http://msdn.microsoft.com/en-us/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
