---
title: IMetaDataEmit2::SetGenericParamProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
ms.openlocfilehash: fd7f149e806727d849cdceb3ffbc5dc7392fcf1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177408"
---
# <a name="imetadataemit2setgenericparamprops-method"></a>IMetaDataEmit2::SetGenericParamProps-Methode
Legt Eigenschaftswerte für die generische Parameterdefinition fest, auf die vom angegebenen Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `gp`  
 [in] Das Token für die generische Parameterdefinition, für die Werte festgelegt werden sollen.  
  
 `dwParamFlags`  
 [in] Ein Wert der [CorGenericParamAttr-Enumeration,](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) der den Typ für den generischen Parameter beschreibt.  
  
 `szName`  
 [in] Optional. Der Name des Parameters, für den Werte festgelegt werden sollen.  
  
 `reserved`  
 [in] Für zukünftige Erweiterungen reserviert.  
  
 `rtkConstraints`  
 [in] Optional. Ein Null-Termin-Array von Typeinschränkungen. Arraymember müssen `mdTypeDef`ein `mdTypeRef`, `mdTypeSpec` oder Metadatentoken sein.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
