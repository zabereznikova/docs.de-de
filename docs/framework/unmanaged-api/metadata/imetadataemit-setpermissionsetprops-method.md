---
title: IMetaDataEmit::SetPermissionSetProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d80e3206f74c3c50c8436563b0e39d1229a963b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446368"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a>IMetaDataEmit::SetPermissionSetProps-Methode
Legt fest oder aktualisiert Sie Features der Metadatensignatur der einen Berechtigungssatz, der durch einen vorherigen Aufruf definierten [DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `tk`  
 [in] Ein Metadatentoken, das das Objekt, das ausgestattet sein darstellt.  
  
 `dwAction`  
 [in] Ein [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) Wert, der den Typ des zu verwendenden deklarative Sicherheit angibt.  
  
 `pvPermission`  
 [in] Die BLOB-Berechtigung.  
  
 `cbPermission`  
 [in] Die Größe in Bytes, der `pvPermission`.  
  
 `ppm`  
 [out] Ein `mdPermission` Metadatentoken, das die aktualisierten Berechtigungen darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
