---
title: Init-Methode
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
ms.openlocfilehash: 25a1c29ab94a785304b83d5b1bcb2d7176742a68
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726017"
---
# <a name="init-method"></a>Init-Methode

Bereitet Objekte vor, die die [IALink-Schnittstelle](ialink-interface.md) zur Verwendung implementieren.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a>Parameter  

 `pDispenser`  
 [IMetaDataDispenserEx-Schnittstellen](../metadata/imetadatadispenserex-interface.md) Zeiger auf den metadatendispenser.  
  
 `pErrorHandler`  
 [IMetaDataError-Schnittstellen](../metadata/imetadataerror-interface.md) Zeiger auf eine optionale Schnittstelle zur Fehlerbehandlung.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [ALink-API](index.md)
