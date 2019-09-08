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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf96770dd58c9b84596c082a615f626ec723cc6c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787248"
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
  
## <a name="requirements"></a>Anforderungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
