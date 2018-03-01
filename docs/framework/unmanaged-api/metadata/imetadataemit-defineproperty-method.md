---
title: IMetaDataEmit::DefineProperty-Methode
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: accc6503cc9fb87d39a429331dc82ff5717f6989
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineproperty-method"></a>IMetaDataEmit::DefineProperty-Methode
Erstellt eine Eigenschaftsdefinition für den angegebenen Typ mit dem angegebenen `get` und `set` Methodenaccessoren und ruft ein Token auf, Eigenschaftsdefinition ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 `td`  
 [in] Das Token für die Klasse oder Schnittstelle, die auf dem die Eigenschaft definiert wird.  
  
 `szProperty`  
 [in] Der Name der Eigenschaft.  
  
 `dwPropFlags`  
 [in] Die Eigenschaftenflags.  
  
 `pvSig`  
 [in] Die Signatur der Eigenschaft.  
  
 `cbSig`  
 [in] Die Anzahl der Bytes im `pvSig`.  
  
 `dwCPlusTypeFlag`  
 [in] Der Typ des Standardwerts für die Eigenschaft.  
  
 `pValue`  
 [in] Der Standardwert für die Eigenschaft.  
  
 `cchValue`  
 [in] Die Anzahl von (Unicode-) Zeichen `pValue`.  
  
 `mdSetter`  
 [in] Die Methode, die den Wert der Eigenschaft festlegt.  
  
 `mdGetter`  
 [in] Die Methode, die den Eigenschaftswert abruft.  
  
 `rmdOtherMethods[]`  
 [in] Ein Array von anderen Methoden, die der Eigenschaft zugeordnet werden soll. Beenden Sie das Array mit einem `mdTokenNil`.  
  
 `pmdProp`  
 [out] Die `mdProperty` Token zugewiesen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
