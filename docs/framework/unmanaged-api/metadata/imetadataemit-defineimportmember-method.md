---
title: IMetaDataEmit::DefineImportMember-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 81acda4d395563fc8e0000e38036d1aaa0f14471
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222691"
---
# <a name="imetadataemitdefineimportmember-method"></a>IMetaDataEmit::DefineImportMember-Methode
Erstellt einen Verweis auf den angegebenen Member eines Typs oder ein Modul, das außerhalb des aktuellen Bereichs definiert ist, und definiert ein Token für diesen Verweis.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineImportMember (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,   
    [in]  mdToken                  mbMember,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [in]  mdToken                  tkParent,   
    [out] mdMemberRef              *pmr   
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pAssemImport`  
 [in] Ein [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) -Schnittstelle, die die Assembly darstellt, aus dem der Zielmember importiert wird.  
  
 `pbHashValue`  
 [in] Ein Array, das den Hash für die Assembly, die anhand des enthält `pAssemImport`.  
  
 `cbHashValue`  
 [in] Die Anzahl der Bytes im `pbHashValue`-Array.  
  
 `pImport`  
 [in] Ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -Schnittstelle, die den Metadatenbereich darstellt, aus dem der Zielmember importiert wird.  
  
 `mbMember`  
 [in] Das Metadatentoken, das die Ziel-Element angibt. Das Token kann sein ein `mdMethodDef` (für eine Membermethode) `mdProperty` (für einen Membereigenschaft), oder `mdFieldDef` (für ein Memberfeld) token.  
  
 `pAssemEmit`  
 [in] Ein [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) -Schnittstelle, die die Assembly darstellt, in dem der Zielmember importiert wird.  
  
 `tkParent`  
 [in] Die `mdTypeRef` oder `mdModuleRef` token für den Typ oder Modul bzw., besitzt das Target-Element.  
  
 `pmr`  
 [out] Die `mdMemberRef` Token, das in den aktuellen Bereich für den Parameterverweis definiert ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `DefineImportMember` Methode sucht das Element vom angegebenen `mbMember`, d. h. in einem anderen Bereich von angegebenen definiert `pImport`, und ruft dessen Eigenschaften. Sie verwendet diese Informationen zum Aufrufen der [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) -Methode in der aktuellen Bereich für den Parameterverweis zu erstellen.  
  
 Im Allgemeinen, bevor Sie verwenden die `DefineImportMember` -Methode, Sie müssen erstellen, den aktuellen Bereich ein Typverweis oder eine Modul-Referenz für des Zielmembers übergeordnete Klasse, Schnittstelle oder Moduls. Das Metadatentoken für diesen Verweis dann übergeben die `tkParent` Argument. Sie müssen sich nicht um einen Verweis auf den Zielmember übergeordnete zu erstellen, wenn sie später vom Compiler oder Linker aufgelöst wird. Zusammenfassung:  
  
-   Wenn der Zielmember ein Feld oder eine Methode ist, verwenden Sie entweder die [IMetaDataEmit:: DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) oder [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) Methode erstellen Sie einen Typverweis, im aktuellen Bereich, für die übergeordnete Klasse oder Schnittstelle des Members.  
  
-   Wenn der Zielmember eine globale Variable oder Funktion (d. h. nicht Mitglied einer Klasse oder Schnittstelle) ist, verwenden die [DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) Methode, um einen Modulverweis im aktuellen Bereich, für das Element übergeordneten Elements erstellen Modul.  
  
-   Wenn der Zielmember übergeordneten später vom Compiler oder Linker aufgelöst wird, übergeben Sie `mdTokenNil` in `tkParent`. Ist das einzige Szenario, in dem dies gilt, wenn eine globale Funktion oder globale Variable wird aus einer OBJ-Datei, die letztendlich in das aktuelle Modul verknüpft werden, wird importiert, und die Metadaten zusammengeführt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
