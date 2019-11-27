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
ms.openlocfilehash: 3e470250fa0e86610fcc9a6d6e2ca03569d62b54
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449449"
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
 in Das Metadatentoken für die einschließende Klasse des exportierten Typs. Dieser Wert ist `mdExportedTypeNil`, wenn der angeforderte exportierte Typ kein Typ ist.  
  
 `ptkExportedType`  
 vorgenommen Ein Zeiger auf das `mdExportedType` Token, das den exportierten Typ darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die `FindExportedTypeByName`-Methode verwendet die Standardregeln, die vom Common Language Runtime zum Auflösen von Verweisen verwendet werden.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [So sucht Common Language Runtime nach Assemblys](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
