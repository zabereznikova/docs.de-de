---
title: IMetaDataEmit::DefineTypeDef-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: da8fed37605252139428aa40bb3785c242d95cac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinetypedef-method"></a>IMetaDataEmit::DefineTypeDef-Methode
Erstellt eine Typdefinition für einen Typ der common Language Runtime und ruft ein Metadatentoken für diese Typdefinition erzeugen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `szTypeDef`  
 [in] Der Name des Typs im Unicode-Format.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` Attribute. Dies ist eine Bitmaske der `CoreTypeAttr` Werte.  
  
 `tkExtends`  
 [in] Das Token der Basisklasse. Es muss entweder ein `mdTypeDef` oder ein `mdTypeRef` token.  
  
 `rtkImplements`  
 [in] Ein Array von Token, die die Schnittstellen, die diese Klasse oder Schnittstelle implementiert wird, angeben.  
  
 `ptd`  
 [out] Die `mdTypeDef` Token zugewiesen.  
  
## <a name="remarks"></a>Hinweise  
 Ein Flag in `dwTypeDefFlags` angibt, ob der erstellte Typ wird ein common Type System Verweistyp (Klasse oder Schnittstelle) oder ein common Type systemwerttyp ist.  
  
 Abhängig von den Parametern angegeben wird, diese Methode als Nebeneffekt erstellt auch möglicherweise eine `mdInterfaceImpl` Datensatz für jede Schnittstelle, die von diesem Typ implementiert oder geerbt. Aber diese Methode gibt keinen zurück eines dieser `mdInterfaceImpl` Token. Wenn ein Client zu einem späteren Zeitpunkt hinzufügen oder ändern möchte ein `mdInterfaceImpl` token muss verwendet werden die `IMetaDataImport` Schnittstelle, um sie aufzulisten. Wenn Sie COM-Semantik der verwenden möchten die `[default]` -Schnittstelle, sollten Sie die Standardschnittstelle bereitstellen, als das erste Element im `rtkImplements`; ein benutzerdefiniertes Attribut für die Klasse wird angegeben, dass die Klasse eine Standardschnittstelle verfügt über (dem wird immer vorausgesetzt werden der zuerst `mdInterfaceImpl` Token für die Klasse deklariert).  
  
 Jedes Element der `rtkImplements` Arrays enthält ein `mdTypeDef` oder `mdTypeRef` token. Das letzte Element im Array muss `mdTokenNil`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
