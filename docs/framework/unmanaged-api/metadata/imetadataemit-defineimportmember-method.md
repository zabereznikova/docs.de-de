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
ms.openlocfilehash: a7449ffc8a8ccf2db62ab3cff2f9cfaffd0c72a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175862"
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
 [in] Eine [IMetaDataAssemblyImport-Schnittstelle,](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) die die Assembly darstellt, aus der das Zielelement importiert wird.  
  
 `pbHashValue`  
 [in] Ein Array, das den Hash `pAssemImport`für die assembly enthält, die von angegeben wird.  
  
 `cbHashValue`  
 [in] Die Anzahl der Bytes im `pbHashValue`-Array.  
  
 `pImport`  
 [in] Eine [IMetaDataImport-Schnittstelle,](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) die den Metadatenbereich darstellt, aus dem das Zielmitglied importiert wird.  
  
 `mbMember`  
 [in] Das Metadatentoken, das den Zielmember angibt. Das Token kann `mdMethodDef` ein (für `mdProperty` eine Membermethode), (für eine Membereigenschaft) oder `mdFieldDef` (für ein Memberfeld) Token sein.  
  
 `pAssemEmit`  
 [in] Eine [IMetaDataAssemblyEmit-Schnittstelle,](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) die die Assembly darstellt, in die das Zielelement importiert wird.  
  
 `tkParent`  
 [in] Das `mdTypeRef` `mdModuleRef` oder-Token für den Typ bzw. das Modul, dem bzw. dem das Zielelement gehört.  
  
 `pmr`  
 [out] Das `mdMemberRef` Token, das im aktuellen Bereich für den Memberverweis definiert ist.  
  
## <a name="remarks"></a>Bemerkungen  
 Die `DefineImportMember` Methode sucht den Member, der durch `mbMember`angegeben wird, `pImport`der in einem anderen Bereich definiert ist, von angegeben und ruft seine Eigenschaften ab. Es verwendet diese Informationen, um die [IMetaDataEmit::DefineMemberRef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) im aktuellen Bereich aufzurufen, um den Memberverweis zu erstellen.  
  
 Im Allgemeinen müssen `DefineImportMember` Sie vor der Verwendung der Methode im aktuellen Bereich eine Typreferenz oder Modulreferenz für die übergeordnete Klasse, Schnittstelle oder das Modul des Zielmembers erstellen. Das Metadatentoken für diesen Verweis `tkParent` wird dann im Argument übergeben. Sie müssen keinen Verweis auf das übergeordnete Element des Zielmembers erstellen, wenn er später vom Compiler oder Linker aufgelöst wird. Zusammenfassung:  
  
- Wenn es sich bei dem Zielmember um ein Feld oder eine Methode handelt, verwenden Sie entweder die [IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) oder die [IMetaDataEmit::DefineImportType-Methode,](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) um im aktuellen Bereich einen Typverweis für die übergeordnete Klasse oder übergeordnete Schnittstelle des Elements zu erstellen.  
  
- Wenn es sich bei dem Zielelement um eine globale Variable oder globale Funktion (d. h. kein Member einer Klasse oder Schnittstelle) handelt, verwenden Sie die [IMetaDataEmit::DefineModuleRef-Methode,](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) um im aktuellen Bereich einen Modulverweis für das übergeordnete Modul des Elements zu erstellen.  
  
- Wenn das übergeordnete Element des Zielmembers später vom Compiler oder `mdTokenNil` `tkParent`Linker aufgelöst wird, geben Sie . Das einzige Szenario, in dem dies zutrifft, ist, wenn eine globale Funktion oder globale Variable aus einer .obj-Datei importiert wird, die letztendlich mit dem aktuellen Modul verknüpft und die Metadaten zusammengeführt werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
