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
ms.openlocfilehash: ec8a24251ac4f0701b1adab19829078270229ced
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004594"
---
# <a name="imetadataemitdefineimportmember-method"></a>IMetaDataEmit::DefineImportMember-Methode
Erstellt einen Verweis auf den angegebenen Member eines Typs oder Moduls, der außerhalb des aktuellen Bereichs definiert ist, und definiert ein Token für diesen Verweis.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
 in Eine [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) -Schnittstelle, die die Assembly darstellt, aus der der Zielmember importiert wird.  
  
 `pbHashValue`  
 in Ein Array, das den Hash für die durch angegebene Assembly enthält `pAssemImport` .  
  
 `cbHashValue`  
 [in] Die Anzahl der Bytes im `pbHashValue`-Array.  
  
 `pImport`  
 in Eine [IMetaDataImport](imetadataimport-interface.md) -Schnittstelle, die den Metadatenbereich darstellt, aus dem der Zielmember importiert wird.  
  
 `mbMember`  
 in Das Metadatentoken, das den Zielmember angibt. Das Token kann ein `mdMethodDef` (für eine Member-Methode), `mdProperty` (für eine Element Eigenschaft) oder `mdFieldDef` (für ein Element Feld) sein.  
  
 `pAssemEmit`  
 in Eine [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) -Schnittstelle, die die Assembly darstellt, in die der Zielmember importiert wird.  
  
 `tkParent`  
 in Das- `mdTypeRef` oder- `mdModuleRef` Token für den Typ bzw. das Modul, das den Zielmember besitzt.  
  
 `pmr`  
 vorgenommen Das `mdMemberRef` Token, das im aktuellen Gültigkeitsbereich für den Element Verweis definiert wird.  
  
## <a name="remarks"></a>Hinweise  
 Die `DefineImportMember` -Methode sucht nach dem durch angegebenen Member, der `mbMember` in einem anderen Bereich definiert ist, der durch angegeben wird, `pImport` und ruft seine Eigenschaften ab. Diese Informationen werden verwendet, um die [IMetaDataEmit::D efinemembership Ref](imetadataemit-definememberref-method.md) -Methode im aktuellen Bereich aufzurufen, um den Element Verweis zu erstellen.  
  
 Im Allgemeinen müssen Sie vor der Verwendung der `DefineImportMember` -Methode im aktuellen Bereich einen Typverweis oder Modul Verweis für die übergeordnete Klasse, Schnittstelle oder das Modul des Zielmembers erstellen. Das Metadatentoken für diesen Verweis wird dann im-Argument weitergegeben `tkParent` . Sie müssen keinen Verweis auf das übergeordnete Element des Zielmembers erstellen, wenn es später durch den Compiler oder den Linker aufgelöst wird. Zusammenfassung:  
  
- Wenn das Zielmember ein Feld oder eine Methode ist, verwenden Sie entweder die [IMetaDataEmit::D efinetyperefbyname](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) -Methode oder die [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md) -Methode, um im aktuellen Bereich einen Typverweis für die übergeordnete Klasse oder übergeordnete Schnittstelle des Elements zu erstellen.  
  
- Wenn das Zielmember eine globale Variable oder globale Funktion (d. h. kein Member einer Klasse oder Schnittstelle) ist, verwenden Sie die [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md) -Methode, um einen Modul Verweis im aktuellen Bereich für das übergeordnete Modul des Elements zu erstellen.  
  
- Wenn das übergeordnete Element des Zielmembers später durch den Compiler oder den Linker aufgelöst wird, übergeben Sie `mdTokenNil` `tkParent` . Das einzige Szenario, in dem dies zutrifft, ist, wenn eine globale Funktion oder globale Variable aus einer OBJ-Datei importiert wird, die letztendlich mit dem aktuellen Modul und den zusammengeführten Metadaten verknüpft wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
