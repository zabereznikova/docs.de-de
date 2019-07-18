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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9e78c4d7319a931ca7090d6f99651bc9660e4af8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782041"
---
# <a name="imetadataemitsetpropertyprops-method"></a>IMetaDataEmit::SetPropertyProps-Methode
Legt die Funktionen, die in den Metadaten für eine Eigenschaft, die definiert, die von einem vorherigen Aufruf von gespeicherten [DefineProperty-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).  
  
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
 [in] Das Token für die Eigenschaft geändert werden  
  
 `dwPropFlags`  
 [in] Die Eigenschaftenflags.  
  
 `dwCPlusTypeFlag`  
 [in] Der Typ der Standardwert der Eigenschaft.  
  
 `pValue`  
 [in] Der Standardwert für die Eigenschaft.  
  
 `cchValue`  
 [in] Die Anzahl von (Unicode-) Zeichen in `pValue`.  
  
 `mdSetter`  
 [in] Die Methode, die den Wert der Eigenschaft festlegt.  
  
 `mdGetter`  
 [in] Die Methode, die den Wert der Eigenschaft abruft.  
  
 `rmdOtherMethods[]`  
 [in] Ein Array von anderen Methoden der Eigenschaft zugeordnet. Beenden Sie dieses Array mit einem `mdTokenNil` token.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
