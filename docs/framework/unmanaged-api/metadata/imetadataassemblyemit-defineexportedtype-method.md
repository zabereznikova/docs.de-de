---
title: IMetaDataAssemblyEmit::DefineExportedType-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
ms.openlocfilehash: 44f97ef498eb8e64c55fc86b9f290b9e088293f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432071"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>IMetaDataAssemblyEmit::DefineExportedType-Methode
Erstellt eine `ExportedType`-Struktur, die Metadaten für den angegebenen exportierten Typ enthält, und gibt das zugeordnete Metadatentoken zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `szName`  
 in Der Name des zu exportierenden Typs. Bei Version 1,1 des Common Language Runtime muss der Name des exportierten Typs genau mit dem Namen übereinstimmen, der in der `TypeDef` für den Typ angegeben wurde.  
  
 `tkImplementation`  
 in Ein Token, das angibt, wo der exportierte Typ implementiert wird. Die gültigen Werte und ihre zugeordneten Bedeutungen lauten:  
  
- `mdFile` der Typ in einer anderen Datei in dieser Assembly implementiert wird.  
  
- `mdAssemblyRef` der Typ in einer anderen Assembly implementiert wird.  
  
- `mdExportedTYpe` der Typ in einem anderen Typ geschachtelt ist.  
  
- `mdFileNil` sich der Typ in derselben Datei wie das Manifest befindet und kein Typ ist.  
  
 `tkTypeDef`  
 in Ein Token für die Metadaten, das den zu exportierenden Typ angibt. Dieser Wert wird in der `TypeDef` Tabelle in der Datei eingegeben, die den Typ implementiert, und ist nur relevant, wenn sich diese Datei in dieser Assembly befindet.  
  
 `dwExportedTypeFlags`  
 in Eine bitweise Kombination von [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) -Enumerationswerten, die die Eigenschafts Einstellungen für den exportierten Typ definieren.  
  
 `pmdct`  
 vorgenommen Ein Zeiger auf das zurückgegebene Metadatentoken, das den exportierten Typ angibt.  
  
## <a name="remarks"></a>Hinweise  
 Für jeden Typ, der von dieser Assembly verfügbar gemacht wird, muss eine `ExportedType` Metadatenstruktur definiert werden, die in einem anderen Modul implementiert ist als das, das das Manifest enthält.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
