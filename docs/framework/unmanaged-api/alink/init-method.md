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
ms.openlocfilehash: 986ae69e7ebb8f607be5d37fab426bcc787abb26
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445644"
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
  
## <a name="requirements"></a>Voraussetzungen  
 Erfordert "Alink. h"  
  
## <a name="see-also"></a>Siehe auch

- [IALink-Schnittstelle](ialink-interface.md)
- [IALink2-Schnittstelle](ialink2-interface.md)
- [Alink-API](index.md)
