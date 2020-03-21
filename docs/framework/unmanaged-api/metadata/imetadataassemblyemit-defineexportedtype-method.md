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
ms.openlocfilehash: 388f227377ddf73fe1297e1c777bb1c0607c13d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177880"
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
 [in] Der Name des zu exportierenden Typs. Für Version 1.1 der Common Language Runtime muss der Name des exportierten Typs genau mit dem Namen übereinstimmen, der im für den `TypeDef` Typ angegeben ist.  
  
 `tkImplementation`  
 [in] Ein Token, das angibt, wo der exportierte Typ implementiert ist. Die gültigen Werte und die zugehörigen Bedeutungen sind:  
  
- `mdFile`Der Typ wird in einer anderen Datei innerhalb dieser Assembly implementiert.  
  
- `mdAssemblyRef`Der Typ wird in einer anderen Assembly implementiert.  
  
- `mdExportedTYpe`Der Typ ist in einem anderen Typ geschachtelt.  
  
- `mdFileNil`Der Typ befindet sich in derselben Datei wie das Manifest und ist kein geschachtelter Typ.  
  
 `tkTypeDef`  
 [in] Ein Token für die Metadaten, das den zu exportierenden Typ angibt. Dieser Wert wird `TypeDef` in die Tabelle in der Datei eingegeben, die den Typ implementiert, und ist nur relevant, wenn sich diese Datei in dieser Assembly befindet.  
  
 `dwExportedTypeFlags`  
 [in] Eine bitweise Kombination von CorTypeAttr-Enumerationswerten, die die Eigenschafteneinstellungen für den exportierten Typ definieren. [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)  
  
 `pmdct`  
 [out] Ein Zeiger auf das zurückgegebene Metadatentoken, das den exportierten Typ angibt.  
  
## <a name="remarks"></a>Bemerkungen  
 Für `ExportedType` jeden Typ, der von dieser Assembly verfügbar gemacht wird und der in einem anderen Modul als dem, das das Manifest enthält, implementiert wird, muss eine Metadatenstruktur definiert werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
