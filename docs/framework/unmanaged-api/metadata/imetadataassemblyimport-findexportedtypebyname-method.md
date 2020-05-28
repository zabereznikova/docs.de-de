---
title: IMetaDataAssemblyImport::FindExportedTypeByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
ms.openlocfilehash: ac6de9a16fad6ba9d14f3960ddd28c42c111f254
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009391"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a>IMetaDataAssemblyImport::FindExportedTypeByName-Methode
Ruft bei Angabe des Namens und des einschließenden Typs einen Zeiger auf einen exportierten Typ ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `szName`  
 in Der Name des exportierten Typs.  
  
 `mdtExportedType`  
 in Das Metadatentoken für die einschließende Klasse des exportierten Typs. Dieser Wert ist, wenn es sich `mdExportedTypeNil` bei dem angeforderten exportierten Typ nicht um einen Typ handelt.  
  
 `ptkExportedType`  
 vorgenommen Ein Zeiger auf das `mdExportedType` Token, das den exportierten Typ darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die- `FindExportedTypeByName` Methode verwendet die Standardregeln, die vom-Common Language Runtime zum Auflösen von Verweisen verwendet werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyImport-Schnittstelle](imetadataassemblyimport-interface.md)
- [So sucht Common Language Runtime nach Assemblys](../../deployment/how-the-runtime-locates-assemblies.md)
