---
title: IMetaDataEmit::DefineProperty-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: f11b374ed0ecbfc137c43fb641ae691237604691
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431519"
---
# <a name="imetadataemitdefineproperty-method"></a>IMetaDataEmit::DefineProperty-Methode
Erstellt eine Eigenschafts Definition für den angegebenen Typ mit dem angegebenen `get` und `set` Methodenaccessoren und ruft ein Token für diese Eigenschafts Definition ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineProperty (   
    [in]  mdTypeDef          td,   
    [in]  LPCWSTR            szProperty,   
    [in]  DWORD              dwPropFlags,   
    [in]  PCCOR_SIGNATURE    pvSig,   
    [in]  ULONG              cbSig,   
    [in]  DWORD              dwCPlusTypeFlag,   
    [in]  void const         *pValue,   
    [in]  ULONG              cchValue,   
    [in]  mdMethodDef        mdSetter,   
    [in]  mdMethodDef        mdGetter,   
    [in]  mdMethodDef        rmdOtherMethods[],   
    [out] mdProperty         *pmdProp   
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 in Das Token für die Klasse oder Schnittstelle, für die die Eigenschaft definiert wird.  
  
 `szProperty`  
 in Der Name der Eigenschaft.  
  
 `dwPropFlags`  
 in Die Eigenschaftenflags.  
  
 `pvSig`  
 in Die Eigenschaften Signatur.  
  
 `cbSig`  
 in Die Anzahl der Bytes in `pvSig`.  
  
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
 in Ein Array von anderen Methoden, die der-Eigenschaft zugeordnet sind. Beenden Sie das Array mit einem `mdTokenNil`.  
  
 `pmdProp`  
 vorgenommen Das zugewiesene `mdProperty` Token.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
