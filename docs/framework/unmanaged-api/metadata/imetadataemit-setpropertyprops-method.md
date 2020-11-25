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
ms.openlocfilehash: 553a82475f241fac3a56c1fb009e3ed56b2c14f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704252"
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
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
