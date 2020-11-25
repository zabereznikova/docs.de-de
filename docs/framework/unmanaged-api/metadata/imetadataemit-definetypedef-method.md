---
title: IMetaDataEmit::DefineTypeDef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: 2e75b6322e40fe010e9e0a3412a99c0d3460afae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719358"
---
# <a name="imetadataemitdefinetypedef-method"></a>IMetaDataEmit::DefineTypeDef-Methode

Erstellt eine Typdefinition für einen Common Language Runtime Typ und ruft ein Metadatentoken für diese Typdefinition ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `szTypeDef`  
 in Der Name des Typs in Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` legt. Dies ist eine Bitmaske von `CoreTypeAttr` Werten.  
  
 `tkExtends`  
 in Das Token der Basisklasse. Dabei muss es sich entweder um ein- `mdTypeDef` oder ein- `mdTypeRef` Token handeln.  
  
 `rtkImplements`  
 in Ein Array von-Token, das die Schnittstellen angibt, die diese Klasse oder Schnittstelle implementiert.  
  
 `ptd`  
 vorgenommen Das `mdTypeDef` zugewiesene Token.  
  
## <a name="remarks"></a>Hinweise  

 Ein Flag in `dwTypeDefFlags` gibt an, ob der erstellte Typ ein allgemeiner Typsystem-Verweistyp (Klasse oder Schnittstelle) oder ein allgemeiner Typsystem-Werttyp ist.  
  
 Abhängig von den angegebenen Parametern kann diese Methode als Nebeneffekt auch einen `mdInterfaceImpl` Datensatz für jede Schnittstelle erstellen, die von diesem Typ geerbt oder implementiert wird. Diese Methode gibt jedoch keines dieser `mdInterfaceImpl` Token zurück. Wenn ein Client später ein Token hinzufügen oder ändern möchte `mdInterfaceImpl` , muss er die- `IMetaDataImport` Schnittstelle verwenden, um Sie zu auflisten. Wenn Sie die com-Semantik der- `[default]` Schnittstelle verwenden möchten, sollten Sie die Standardschnittstelle als erstes Element in angeben `rtkImplements` . ein benutzerdefiniertes Attribut, das für die Klasse festgelegt ist, gibt an, dass die Klasse über eine Standardschnittstelle verfügt (bei der es sich immer um das erste Token handelt, das `mdInterfaceImpl` für die Klasse deklariert wurde).  
  
 Jedes Element des `rtkImplements` Arrays enthält ein- `mdTypeDef` oder- `mdTypeRef` Token. Das letzte Element im Array muss sein `mdTokenNil` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
