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
ms.openlocfilehash: 4c3e0953d71020ba62ee4ab68aa9e21ea3f0f521
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675034"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a>IMetaDataEmit::SetPermissionSetProps-Methode

Legt die Features der Metadatensignatur eines Berechtigungs Satzes fest, der durch einen vorherigen [IMetaDataEmit::D efinepermissionset](imetadataemit-definepermissionset-method.md)definiert ist, oder aktualisiert diese.  
  
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
 in Ein Metadatentoken, das das zu ergänzte Objekt darstellt.  
  
 `dwAction`  
 in Ein [CorDeclSecurity](cordeclsecurity-enumeration.md) -Wert, der den Typ der zu verwendenden deklarativen Sicherheit angibt.  
  
 `pvPermission`  
 in Das Berechtigungs-BLOB.  
  
 `cbPermission`  
 in Die Größe von in Bytes `pvPermission` .  
  
 `ppm`  
 vorgenommen Ein `mdPermission` Metadatentoken, das die aktualisierten Berechtigungen darstellt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
