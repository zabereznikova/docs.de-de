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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0777151d10149ec7311a7761bc7f6bff5ba98e0e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777490"
---
# <a name="imetadataemitdefinetypedef-method"></a>IMetaDataEmit::DefineTypeDef-Methode
Erstellt eine Typdefinition für einen Typ der common Language Runtime und ruft ein Metadatentoken für diese Typdefinition.  
  
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
 [in] Der Name des Typs im Unicode-Format.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` Attribute. Dies ist eine Bitmaske der `CoreTypeAttr` Werte.  
  
 `tkExtends`  
 [in] Das Token der Basisklasse. Es muss entweder eine `mdTypeDef` oder `mdTypeRef` token.  
  
 `rtkImplements`  
 [in] Ein Array von Token, die die Schnittstellen, die diese Klasse oder Schnittstelle implementiert angeben.  
  
 `ptd`  
 [out] Die `mdTypeDef` zugewiesene Token.  
  
## <a name="remarks"></a>Hinweise  
 Ein Flag in `dwTypeDefFlags` angibt, ob der erstellte Typ wird ein common Type System Verweistyp (Klasse oder Schnittstelle) oder ein common Type System-Werttyp ist.  
  
 Je nach den angegebenen Parametern kann diese Methode eine nebenerscheinung erstellt auch möglicherweise eine `mdInterfaceImpl` Datensatz für jede Schnittstelle, die von diesem Typ implementiert oder geerbt. Aber diese Methode gibt nicht zurück um eines dieser `mdInterfaceImpl` Token. Wenn ein Client zum später hinzufügen oder ändern möchte ein `mdInterfaceImpl` token ist, darf Sie verwenden die `IMetaDataImport` Schnittstelle, um diese aufzulisten. Wenn Sie COM-Semantik der verwenden möchten die `[default]` -Schnittstelle, sollten Sie die Standard-Schnittstelle bereitstellen, als das erste Element im `rtkImplements`; ein benutzerdefiniertes Attribut für die Klasse festgelegt wird, dass die Klasse eine Standardschnittstelle angegeben (der wird immer als die zuerst `mdInterfaceImpl` Token für die Klasse deklariert).  
  
 Jedes Element der `rtkImplements` Arrays enthält ein `mdTypeDef` oder `mdTypeRef` token. Das letzte Element im Array muss `mdTokenNil`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
