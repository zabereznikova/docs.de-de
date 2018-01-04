---
title: IMetaDataImport::GetScopeProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetScopeProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 53e77a7bf0bd0aafc205469c4e101f8bfdcbe80b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetscopeprops-method"></a>IMetaDataImport::GetScopeProps-Methode
Ruft den Namen und optional den Versionsbezeichner der Assembly oder des Moduls im aktuellen Metadatenbereich ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `szName`  
 [out] Ein Puffer für die Assembly oder ein Modul Name.  
  
 `cchName`  
 [in] Die Größe in Breitzeichen `szName`.  
  
 `pchName`  
 [out] Die Anzahl der Breitzeichen, die im zurückgegebenen `szName`.  
  
 `pmvid`  
 [out, optional] Ein Zeiger auf eine GUID, die die Version der Assembly oder des Moduls eindeutig identifiziert.  
  
## <a name="remarks"></a>Hinweise  
 Die [IMetaDataEmit:: SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) Methode zum Festlegen dieser Eigenschaften verwendet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
