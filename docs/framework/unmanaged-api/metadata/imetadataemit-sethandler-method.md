---
title: IMetaDataEmit::SetHandler-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetHandler
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccb35c12e1d9c2fade9d8760d0a2e39807c92de9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsethandler-method"></a>IMetaDataEmit::SetHandler-Methode
Legt die Methode, die auf die verwiesen wird durch das angegebene `IUnknown` Zeiger als eines Rückrufs für token neue Zuordnungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pUnk`  
 [in] Der Handler registriert.  
  
## <a name="remarks"></a>Hinweise  
 Das Metadatenmodul sendet Benachrichtigung mithilfe der Methode, die von bereitgestellte `SetHandler`, Compiler, die Datensätze nicht auf optimierte Weise generieren und die gespeicherte Datensätze optimieren möchten.  
  
 Wenn die Rückrufmethode nicht über die bereitgestellten `SetHandler`, keine Optimierung erfolgt auf speichern es sei denn, in denen mehrere importtypen Bereiche zusammengeführt wurden mit `IMapToken` auf "Zusammenführen" für die einzelnen Bereiche.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
