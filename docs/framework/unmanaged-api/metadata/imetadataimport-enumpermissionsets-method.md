---
title: IMetaDataImport::EnumPermissionSets-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumPermissionSets
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f31d35f21a16983b6ab9c23f1f65c3916b5138d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenumpermissionsets-method"></a>IMetaDataImport::EnumPermissionSets-Methode
Zählt Berechtigungen für die Objekte in einem angegebenen Metadatenbereich auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,   
   [in]      mdToken       tk,   
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `phEnum`  
 [in, out] Ein Zeiger auf den Enumerator. Dies muss für den ersten Aufruf dieser Methode NULL sein.  
  
 `tk`  
 [in] Ein Metadatentoken, das schränkt den Bereich der Suche oder NULL, um den größtmöglichen Bereich zu suchen.  
  
 `dwActions`  
 [in] Flags zur Darstellung der <xref:System.Security.Permissions.SecurityAction> in aufzunehmenden Werte `rPermission`, oder 0 (null), um alle Aktionen zurückzugeben.  
  
 `rPermission`  
 [out] Das Array zum Speichern der Berechtigung-Token verwendet wird.  
  
 `cMax`  
 [in] Die maximale Größe des `rPermission`-Arrays.  
  
 `pcTokens`  
 [out] Die Anzahl der Permission-Token im zurückgegebenen `rPermission`.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|`S_OK`|`EnumPermissionSets`wurde erfolgreich zurückgegeben.|  
|`S_FALSE`|Es sind keine Token aufgelistet werden. In diesem Fall `pcTokens` 0 (null).|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
