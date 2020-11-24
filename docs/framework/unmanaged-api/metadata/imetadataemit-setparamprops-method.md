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
ms.openlocfilehash: b0cc28807938bcfb9b2465093ff4cfb94066ee98
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675060"
---
# <a name="imetadataemitsetparamprops-method"></a>IMetaDataEmit::SetParamProps-Methode

Legt die Features eines Methoden Parameters fest, der durch einen vorherigen [IMetaDataEmit::D efineparam](imetadataemit-defineparam-method.md)definiert wurde, oder ändert Sie.  
  
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
 in Das Token für den Zielparameter.  
  
 `szName`  
 in Der Name des Parameters in Unicode.  
  
 `dwParamFlags`  
 in Die Flags für den Parameter.  
  
 `dwCPlusTypeFlag`  
 in Der ELEMENT_TYPE_ * für den konstanten Wert.  
  
 `pValue`  
 in Der Konstante Wert für den Parameter.  
  
 `cchValue`  
 in Die Größe in (Unicode) Zeichen von `pValue` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
