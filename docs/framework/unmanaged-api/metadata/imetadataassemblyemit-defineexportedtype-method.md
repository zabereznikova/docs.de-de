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
ms.openlocfilehash: 5702fac139ba602828bb8722a1e3e25d6f1c58f6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625438"
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
  
## <a name="parameters"></a>Parameter  
 `szName`  
 [in] Der Name des Typs, der exportiert werden. Für Version 1.1 von der common Language Runtime, den Namen des exportierten Typs genau den angegebenen Namen übereinstimmen, muss die `TypeDef` für den Typ.  
  
 `tkImplementation`  
 [in] Ein Token, die angeben, in dem die exportierte Typ implementiert wird. Die gültigen Werte und deren jeweilige Bedeutung sind:  
  
- `mdFile` Der Typ wird in einer anderen Datei in dieser Assembly implementiert.  
  
- `mdAssemblyRef` Der Typ wird in einer anderen Assembly implementiert.  
  
- `mdExportedTYpe` Der Typ wird in einem anderen Typ geschachtelt.  
  
- `mdFileNil` Der Typ befindet sich in derselben Datei wie das Manifest und kein geschachtelter Typ ist.  
  
 `tkTypeDef`  
 [in] Ein Token an den Metadaten, der den zu exportierenden angibt. Dieser Wert wird eingegeben die `TypeDef` Tabelle in der Datei, die den Typ implementiert und ist nur relevant, wenn diese Datei in dieser Assembly ist.  
  
 `dwExportedTypeFlags`  
 [in] Eine bitweise Kombination von [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) Enumerationswerte, der die eigenschafteneinstellungen für den exportierten Typ definieren.  
  
 `pmdct`  
 [out] Ein Zeiger auf die zurückgegebenen Metadaten-Token, das den exportierten Typ angibt.  
  
## <a name="remarks"></a>Hinweise  
 Ein `ExportedType` Metadatenstruktur muss definiert werden, für jeden Typ, der von dieser Assembly verfügbar gemacht wird, und in einem Modul nicht mit dem Manifest implementiert wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
