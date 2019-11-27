---
title: IMetaDataEmit::SetPropertyProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: 0fdec87324d6efa0f911e37573093c19b93c0349
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440550"
---
# <a name="imetadataemitsetpropertyprops-method"></a>IMetaDataEmit::SetPropertyProps-Methode
Legt die in den Metadaten gespeicherten Features für eine Eigenschaft fest, die durch einen vorherigen-Befehl der [DefineProperty-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)definiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetPropertyProps (   
    [in]  mdProperty      pr,   
    [in]  DWORD           dwPropFlags,   
    [in]  DWORD           dwCPlusTypeFlag,   
    [in]  void const      *pValue,   
    [in]  ULONG           cchValue,   
    [in]  mdMethodDef     mdSetter,   
    [in]  mdMethodDef     mdGetter,   
    [in]  mdMethodDef     rmdOtherMethods[]   
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pr`  
 in Das Token für die Eigenschaft, die geändert werden soll.  
  
 `dwPropFlags`  
 in Eigenschaftenflags.  
  
 `dwCPlusTypeFlag`  
 in Der Typ des Standardwerts der Eigenschaft.  
  
 `pValue`  
 in Der Standardwert für die-Eigenschaft.  
  
 `cchValue`  
 in Die Anzahl von (Unicode-) Zeichen in `pValue`.  
  
 `mdSetter`  
 in Die Methode, die den Eigenschafts Wert festlegt.  
  
 `mdGetter`  
 in Die Methode, die den Eigenschafts Wert abruft.  
  
 `rmdOtherMethods[]`  
 in Ein Array von anderen Methoden, die der-Eigenschaft zugeordnet sind. Beenden Sie dieses Array mit einem `mdTokenNil`-Token.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
