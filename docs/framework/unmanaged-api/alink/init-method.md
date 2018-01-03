---
title: Init-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.Init
api_location: alink.dll
api_type: COM
f1_keywords: Init
helpviewer_keywords: Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 19e37a4df8055f14a72a4c9093cd594a234ae80d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="init-method"></a>Init-Methode
Bereitet Objekte implementieren die [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) für die Verwendung.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `pDispenser`  
 [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) Zeiger auf die Metadatenverteiler.  
  
 `pErrorHandler`  
 [IMetaDataError-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) Zeiger auf eine optionale Schnittstelle der Fehlerbehandlung.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h  
  
## <a name="see-also"></a>Siehe auch  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
