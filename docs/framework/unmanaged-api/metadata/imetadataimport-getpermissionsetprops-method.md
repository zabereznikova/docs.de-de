---
title: IMetaDataImport::GetPermissionSetProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
ms.openlocfilehash: 5faf1a6ae89045b2ef17fab789ee6e5bf23eecf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175342"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a>IMetaDataImport::GetPermissionSetProps-Methode
Ruft die Metadaten <xref:System.Security.PermissionSet?displayProperty=nameWithType> ab, die dem dargestellten durch das angegebene Berechtigungstoken zugeordnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pm`  
 [in] Das Berechtigungsmetadatentoken, das den Berechtigungssatz zum Abrufen der Metadateneigenschaften darstellt.  
  
 `pdwAction`  
 [out] Ein Zeiger auf den Berechtigungssatz.  
  
 `ppvPermission`  
 [out] Ein Zeiger auf die binäre Metadatensignatur des Berechtigungssatzes.  
  
 `pcbPermission`  
 [out] Die Größe in `ppvPermission`Bytes von .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Security.PermissionSet>
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
