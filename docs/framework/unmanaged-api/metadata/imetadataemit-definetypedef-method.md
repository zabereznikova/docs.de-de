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
ms.openlocfilehash: 4f1c3e823b35fcf7d5935eee111e042b2291d216
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175758"
---
# <a name="imetadataemitdefinetypedef-method"></a>IMetaDataEmit::DefineTypeDef-Methode
Erstellt eine Typdefinition für einen Common Language-Laufzeittyp und ruft ein Metadatentoken für diese Typdefinition ab.  
  
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
 [in] Der Name des Typs in Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` Attribute. Dies ist eine `CoreTypeAttr` Bitmaske von Werten.  
  
 `tkExtends`  
 [in] Das Token der Basisklasse. Es muss entweder `mdTypeDef` ein `mdTypeRef` oder ein Token sein.  
  
 `rtkImplements`  
 [in] Ein Array von Token, das die Schnittstellen angibt, die diese Klasse oder Schnittstelle implementiert.  
  
 `ptd`  
 [out] Das `mdTypeDef` token zugewiesen.  
  
## <a name="remarks"></a>Bemerkungen  
 Ein Flag `dwTypeDefFlags` in gibt an, ob es sich bei dem zu erstellenden Typ um einen allgemeinen Typsystemreferenztyp (Klasse oder Schnittstelle) oder einen allgemeinen Typsystemwerttyp handelt.  
  
 Abhängig von den angegebenen Parametern kann diese Methode als `mdInterfaceImpl` Nebeneffekt auch einen Datensatz für jede Schnittstelle erstellen, die von diesem Typ geerbt oder implementiert wird. Diese Methode gibt jedoch keines `mdInterfaceImpl` dieser Token zurück. Wenn ein Client später ein `mdInterfaceImpl` Token hinzufügen oder `IMetaDataImport` ändern möchte, muss er die Schnittstelle verwenden, um sie aufzuzählen. Wenn Sie die COM-Semantik `[default]` der Schnittstelle verwenden möchten, sollten Sie `rtkImplements`die Standardschnittstelle als erstes Element in angeben. Ein benutzerdefiniertes Attribut, das für die Klasse festgelegt ist, gibt an, dass die Klasse über eine Standardschnittstelle verfügt (die immer als das erste `mdInterfaceImpl` für die Klasse deklarierte Token angenommen wird).  
  
 Jedes Element `rtkImplements` des Arrays enthält ein `mdTypeDef` oder `mdTypeRef` ein Token. Das letzte Element im `mdTokenNil`Array muss .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
