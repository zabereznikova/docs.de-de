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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2eb894a8bac702c30826d1e965c91cae9b259ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448559"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>IMetaDataAssemblyEmit::DefineExportedType-Methode
Erstellt eine `ExportedType`-Struktur, die Metadaten für den angegebenen exportierten Typ enthält, und gibt das zugeordnete Metadatentoken zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `szName`  
 [in] Der Name des Typs, der exportiert werden. Für Version 1.1 von der common Language Runtime den Namen der exportierte Typ muss genau den angegebenen Namen entsprechen den `TypeDef` für den Typ.  
  
 `tkImplementation`  
 [in] Ein Token, die angeben, in denen der exportierte Typ implementiert wird. Die gültigen Werte und ihre zugeordneten Bedeutung sind:  
  
-   `mdFile` Der Typ wird in eine andere Datei in dieser Assembly implementiert.  
  
-   `mdAssemblyRef` Der Typ wird in einer anderen Assembly implementiert.  
  
-   `mdExportedTYpe` Der Typ wird in einem anderen Typ geschachtelt.  
  
-   `mdFileNil` Der Typ befindet sich in der gleichen Datei wie das Manifest und kein geschachtelter Typ ist.  
  
 `tkTypeDef`  
 [in] Ein Token für die Metadaten, die der den zu exportierenden angibt. Dieser Wert eingegeben wird, der `TypeDef` Tabelle in der Datei, die den Typ implementiert und ist nur relevant, wenn diese Datei in dieser Assembly ist.  
  
 `dwExportedTypeFlags`  
 [in] Eine bitweise Kombination von [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) Enumerationswerte, der die eigenschafteneinstellungen für den exportierten Typ definieren.  
  
 `pmdct`  
 [out] Ein Zeiger auf die zurückgegebenen Metadaten-Token, das den exportierten Typ angibt.  
  
## <a name="remarks"></a>Hinweise  
 Ein `ExportedType` Metadatenstruktur muss für jeden Typ, der von dieser Assembly verfügbar gemacht wird, und implementiert wird in einem Modul als dem mit dem Manifest, definiert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
