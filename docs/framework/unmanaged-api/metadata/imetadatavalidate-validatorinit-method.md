---
title: IMetaDataValidate::ValidatorInit-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataValidate.ValidatorInit
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26f5f6626766d7341ef5c8b2ecbe5e56a17eafdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatavalidatevalidatorinit-method"></a>IMetaDataValidate::ValidatorInit-Methode
Setzt ein Flag, das den Typ des Moduls im aktuellen Metadatenbereich angibt, und registriert die angegebene Rückrufmethode für Validierungsfehler.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwModule`  
 [in] Der Wert der [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) -Enumeration, der den Typ des Moduls im aktuellen Metadatenbereich angibt.  
  
 `pUnk`  
 [in] Ein Zeiger auf ein <<!--zzxref:IUnknown --> `IUnknown`> Instanz, die als ein Funktionsrückruf für Validierungsfehler dient.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataValidate-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
