---
title: IMetaDataImport::GetClassLayout-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetClassLayout
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetClassLayout
helpviewer_keywords:
- IMetaDataImport::GetClassLayout method [.NET Framework metadata]
- GetClassLayout method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 8f35414d-f40b-4b99-8768-9adb675c622a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cece37a6321fc68cbff2957f9753af5f2f916f5f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetclasslayout-method"></a>IMetaDataImport::GetClassLayout-Methode
Ruft Layoutinformationen für die Klasse ab, auf die vom angegebenen TypeDef-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetClassLayout  (   
   [in]  mdTypeDef          td,   
   [out] DWORD              *pdwPackSize,  
   [out] COR_FIELD_OFFSET   rFieldOffset[],  
   [in]  ULONG              cMax,  
   [out] ULONG              *pcFieldOffset,  
   [out] ULONG              *pulClassSize  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `td`  
 [in] Die TypeDef-Token für die Klasse mit dem Layout zurückgegeben werden soll.  
  
 `pdwPackSize`  
 [out] Einer der Werte 1, 2, 4, 8 oder 16, Komprimierungsgröße der-Klasse.  
  
 `rFieldOffset`  
 [out] Ein Array von [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) Werte.  
  
 `cMax`  
 [in] Die maximale Größe des `rFieldOffset`-Arrays.  
  
 `pcFieldOffset`  
 [out] Die Anzahl der Elemente im zurückgegebenen `rFieldOffset`.  
  
 `pulClassSize`  
 [out] Die Größe in Byte der dargestellte Klasse `td`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
