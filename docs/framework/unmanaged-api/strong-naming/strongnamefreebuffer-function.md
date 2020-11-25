---
title: StrongNameFreeBuffer-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
ms.openlocfilehash: d93bda046a79dbdec2195eee48fefc1e5538b2e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732254"
---
# <a name="strongnamefreebuffer-function"></a>StrongNameFreeBuffer-Funktion

Gibt Speicher frei, der bei einem vorherigen Aufruf einer Funktion für starke Namen wie [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md) oder [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) zugewiesen wurde.  
  
 Diese Funktion ist veraltet. Verwenden Sie stattdessen die [ICLRStrongName:: strongnamefrebuffer](../hosting/iclrstrongname-strongnamefreebuffer-method.md) -Methode.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
VOID StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pbMemory`  
 in Ein Zeiger auf den frei verfügbaren Arbeitsspeicher.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [StrongNameFreeBuffer-Methode](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
