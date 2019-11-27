---
title: IMetaDataAssemblyImport::GetExportedTypeProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 82302124828a2dab73b445128d7d847e112edd36
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448218"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>IMetaDataAssemblyImport::GetExportedTypeProps-Methode
Ruft den Satz von Eigenschaften des exportierten Typs mit der angegebenen Metadatensignatur ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `mdct`  
 in Ein `mdExportedType` Metadatentoken, das den exportierten Typ darstellt.  
  
 `szName`  
 vorgenommen Der Name des exportierten Typs.  
  
 `cchName`  
 in Die Größe `szName`in breit Zeichen.  
  
 `pchName`  
 vorgenommen Die Anzahl der tatsächlich in `szName` zurückgegebenen breit Zeichen.  
  
 `ptkImplementation`  
 vorgenommen Ein `mdFile`-, `mdAssemblyRef`-oder `mdExportedType` Metadatentoken, das den Zugriff auf die Eigenschaften des exportierten Typs enthält bzw. zulässt.  
  
 `ptkTypeDef`  
 vorgenommen Ein Zeiger auf ein `mdTypeDef` Token, das einen Typ in der Datei darstellt.  
  
 `pdwExportedTypeFlags`  
 vorgenommen Ein Zeiger auf die Flags, die die auf den exportierten Typ angewendeten Metadaten beschreiben. Der Flags-Wert kann ein oder mehrere [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) -Werte sein.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
