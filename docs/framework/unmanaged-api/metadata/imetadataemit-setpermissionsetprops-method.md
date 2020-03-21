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
ms.openlocfilehash: de4cfdf2a9353eebdebaf4df9e481d06d776ff04
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177486"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a>IMetaDataEmit::SetPermissionSetProps-Methode
Legt Features der Metadatensignatur eines Berechtigungssatzes fest, der durch einen vorherigen Aufruf von [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)definiert wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tk`  
 [in] Ein Metadatentoken, das das zu verstellende Objekt darstellt.  
  
 `dwAction`  
 [in] Ein [CorDeclSecurity-Wert,](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) der den Typ der zu verwendenden deklarativen Sicherheit angibt.  
  
 `pvPermission`  
 [in] Die Berechtigung BLOB.  
  
 `cbPermission`  
 [in] Die Größe von in `pvPermission`Bytes von .  
  
 `ppm`  
 [out] Ein `mdPermission` Metadatentoken, das die aktualisierten Berechtigungen darstellt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
