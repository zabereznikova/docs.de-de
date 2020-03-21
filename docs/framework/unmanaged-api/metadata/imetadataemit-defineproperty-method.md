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
ms.openlocfilehash: eb3ecbf39376e7126b5ec93a26badcbf5076d1db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175784"
---
# <a name="imetadataemitdefineproperty-method"></a>IMetaDataEmit::DefineProperty-Methode
Erstellt eine Eigenschaftsdefinition für den `get` angegebenen `set` Typ mit den angegebenen und Methodenaccessoren und ruft ein Token für diese Eigenschaftsdefinition ab.  
  
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
 [in] Das Token für die Klasse oder Schnittstelle, für die die Eigenschaft definiert wird.  
  
 `szProperty`  
 [in] Der Name der Eigenschaft.  
  
 `dwPropFlags`  
 [in] Die Eigenschaftsflags.  
  
 `pvSig`  
 [in] Die Eigenschaftssignatur.  
  
 `cbSig`  
 [in] Die Anzahl der `pvSig`Bytes in .  
  
 `dwCPlusTypeFlag`  
 [in] Der Typ des Standardwerts der Eigenschaft.  
  
 `pValue`  
 [in] Der Standardwert für die Eigenschaft.  
  
 `cchValue`  
 [in] Die Anzahl der (Unicode)-Zeichen in `pValue`.  
  
 `mdSetter`  
 [in] Die Methode, die den Eigenschaftswert festlegt.  
  
 `mdGetter`  
 [in] Die Methode, die den Eigenschaftswert abruft.  
  
 `rmdOtherMethods[]`  
 [in] Ein Array anderer Methoden, die der Eigenschaft zugeordnet sind. Beenden Sie das `mdTokenNil`Array mit einer .  
  
 `pmdProp`  
 [out] Das `mdProperty` token zugewiesen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
