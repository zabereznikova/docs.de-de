---
title: IMetaDataEmit::SetParamProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8448de17ad974bc77021a7880b7d8576c69ae75
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750913"
---
# <a name="imetadataemitsetparamprops-method"></a>IMetaDataEmit::SetParamProps-Methode
Legt fest oder ändert Sie Features eines Methodenparameters, die von einem vorherigen Aufruf von definiert wurde [DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pd`  
 [in] Das Token für den Target-Parameter.  
  
 `szName`  
 [in] Der Name des Parameters im Unicode-Format.  
  
 `dwParamFlags`  
 [in] Die Flags für den Parameter.  
  
 `dwCPlusTypeFlag`  
 [in] Die ELEMENT_TYPE_ * für den konstanten Wert.  
  
 `pValue`  
 [in] Der Konstante Wert für den Parameter.  
  
 `cchValue`  
 [in] Die Größe in Zeichen (Unicode) der `pValue`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
