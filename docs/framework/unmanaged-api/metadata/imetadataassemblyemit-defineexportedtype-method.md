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
ms.openlocfilehash: 6b30218cc7373494870ec54a3196857fcc5c08a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689419"
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
 in Der Name des zu exportierenden Typs. Bei Version 1,1 des Common Language Runtime muss der Name des exportierten Typs genau mit dem Namen übereinstimmen, der in der `TypeDef` für den Typ angegeben ist.  
  
 `tkImplementation`  
 in Ein Token, das angibt, wo der exportierte Typ implementiert wird. Die gültigen Werte und ihre zugeordneten Bedeutungen lauten:  
  
- `mdFile` Der Typ wird in einer anderen Datei in dieser Assembly implementiert.  
  
- `mdAssemblyRef` Der Typ wird in einer anderen Assembly implementiert.  
  
- `mdExportedTYpe` Der Typ ist in einem anderen Typ geschachtelt.  
  
- `mdFileNil` Der Typ befindet sich in der gleichen Datei wie das Manifest und ist kein Typ.  
  
 `tkTypeDef`  
 in Ein Token für die Metadaten, das den zu exportierenden Typ angibt. Dieser Wert wird in der- `TypeDef` Tabelle in der-Datei eingegeben, die den-Typ implementiert, und ist nur relevant, wenn sich diese Datei in dieser Assembly befindet.  
  
 `dwExportedTypeFlags`  
 in Eine bitweise Kombination von [CorTypeAttr](cortypeattr-enumeration.md) -Enumerationswerten, die die Eigenschafts Einstellungen für den exportierten Typ definieren.  
  
 `pmdct`  
 vorgenommen Ein Zeiger auf das zurückgegebene Metadatentoken, das den exportierten Typ angibt.  
  
## <a name="remarks"></a>Hinweise  

 `ExportedType`Für jeden Typ, der von dieser Assembly verfügbar gemacht wird, muss eine Metadatenstruktur definiert werden, die in einem anderen Modul implementiert ist als das, das das Manifest enthält.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyEmit-Schnittstelle](imetadataassemblyemit-interface.md)
