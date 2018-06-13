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
ms.openlocfilehash: f9995fda70d1d5a3c19c30496de6c32f20015d47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449389"
---
# <a name="imetadataemitdefineimportmember-method"></a>IMetaDataEmit::DefineImportMember-Methode
Erstellt einen Verweis auf das angegebene Element von einem Typ oder Modul, die außerhalb des aktuellen Bereichs definiert ist, und ein Token für diesen Verweis definiert.  
  
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
  
#### <a name="parameters"></a>Parameter  
 `pAssemImport`  
 [in] Ein [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle, die die Assembly darstellt, aus dem der Zielmember importiert wird.  
  
 `pbHashValue`  
 [in] Ein Array, das den Hash für die Assembly gemäß enthält `pAssemImport`.  
  
 `cbHashValue`  
 [in] Die Anzahl der Bytes im `pbHashValue`-Array.  
  
 `pImport`  
 [in] Ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Schnittstelle, die den Metadatenbereich darstellt, aus dem der Zielmember importiert wird.  
  
 `mbMember`  
 [in] Das Metadatentoken, das das Ziel-Element angibt. Das Token kann ein `mdMethodDef` (für eine Membermethode) `mdProperty` (für eine Elementeigenschaft) oder `mdFieldDef` (für ein Memberfeld) token.  
  
 `pAssemEmit`  
 [in] Ein [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) Schnittstelle, die die Assembly darstellt, in dem der Zielmember importiert wird.  
  
 `tkParent`  
 [in] Die `mdTypeRef` oder `mdModuleRef` token für den Typ oder Modul, bzw. der Besitzer ist des Zielelements.  
  
 `pmr`  
 [out] Die `mdMemberRef` Token, das im aktuellen Bereich für den Parameterverweis definiert ist.  
  
## <a name="remarks"></a>Hinweise  
 Die `DefineImportMember` Methode sucht das Element, angegeben durch `mbMember`, d. h. in einem anderen Bereich von angegebenen definiert `pImport`, und ruft dessen Eigenschaften ab. Er verwendet diese Informationen zum Aufrufen der [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) -Methode im aktuellen Bereich für den Parameterverweis zu erstellen.  
  
 Im Allgemeinen vor dem Verwenden der `DefineImportMember` -Methode, Sie müssen erstellen, in den aktuellen Bereich, einen Typverweis oder Modulverweis für die übergeordnete Klasse, Schnittstelle oder Modul des Zielelements. Das Metadatentoken für diesen Verweis dann übergeben der `tkParent` Argument. Sie müssen sich nicht, erstellen einen Verweis auf das Ziel Element übergeordneten Elements aus, wenn sie später vom Compiler oder Linker aufgelöst wird. Zusammenfassung:  
  
-   Das Target-Element ein Feld oder eine Methode ist, verwenden Sie entweder die [IMetaDataEmit:: DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) oder [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) Methode zum Erstellen der eines Typverweis, im aktuellen Bereich für die übergeordnete Klasse oder Schnittstelle des Elements.  
  
-   Wenn der Zielmember eine globale Variable oder Funktion (d. h., kein Mitglied einer Klasse oder Schnittstelle) ist, verwenden die [DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) Methode zum Erstellen eines Modulverweis des aktuellen Bereichs seines übergeordneten Elements Modul.  
  
-   Wenn der Zielmember übergeordneten später vom Compiler oder Linker aufgelöst wird, übergeben Sie `mdTokenNil` in `tkParent`. Ist das einzige Szenario, in dem dies gilt, eine globale Funktion oder globale Variable aus einer OBJ-Datei, die letztendlich in das aktuelle Modul verknüpft, importiert wird und die Metadaten zusammengeführt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
