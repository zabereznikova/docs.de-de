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
ms.openlocfilehash: b5af877c26c20bf64a27618bf24a7bce5b410419
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007779"
---
# <a name="imetadataemitsetpropertyprops-method"></a>IMetaDataEmit::SetPropertyProps-Methode
Legt die in den Metadaten gespeicherten Features für eine Eigenschaft fest, die durch einen vorherigen-Befehl der [DefineProperty-Methode](imetadataemit-defineproperty-method.md)definiert wird.  
  
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
 in Die Anzahl von (Unicode-) Zeichen in `pValue` .  
  
 `mdSetter`  
 in Die Methode, die den Eigenschafts Wert festlegt.  
  
 `mdGetter`  
 in Die Methode, die den Eigenschafts Wert abruft.  
  
 `rmdOtherMethods[]`  
 in Ein Array von anderen Methoden, die der-Eigenschaft zugeordnet sind. Beenden Sie dieses Array mit einem `mdTokenNil` Token.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
