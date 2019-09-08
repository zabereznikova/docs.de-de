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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639664c6ce5714b554f30bff2569a12bf48d1671
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799124"
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
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** StrongName. h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [StrongNameFreeBuffer-Methode](../hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [ICLRStrongName-Schnittstelle](../hosting/iclrstrongname-interface.md)
