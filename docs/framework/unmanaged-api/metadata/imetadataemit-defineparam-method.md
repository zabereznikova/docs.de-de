---
title: IMetaDataEmit::DefineParam-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
ms.openlocfilehash: 5b3f89bb14be0d7128682f8702548545b1e50928
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719527"
---
# <a name="imetadataemitdefineparam-method"></a>IMetaDataEmit::DefineParam-Methode

Erstellt eine Parameterdefinition mit der angegebenen Signatur für die Methode, auf die durch das angegebene Token verwiesen wird, und ruft ein Token für diese Parameterdefinition ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineParam (  
    [in]  mdMethodDef md,
    [in]  ULONG       ulParamSeq,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,
    [out] mdParamDef  *ppd
);  
```  
  
## <a name="parameters"></a>Parameter  

 `md`  
 in Das Token für die Methode, deren Parameter definiert wird.  
  
 `ulParamSeq`  
 in Die Sequenznummer des Parameters.  
  
 `szName`  
 in Der Name des Parameters in Unicode.  
  
 `dwParamFlags`  
 in Flags für den Parameter. Dies ist eine Bitmaske von `CorParamAttr` Werten.  
  
 `dwCPlusTypeFlag`  
 [in] `ELEMENT_TYPE_` *\** für den konstanten Wert.  
  
 `pValue`  
 in Der Konstante Wert für den Parameter.  
  
 `cchValue`  
 in Die Größe von in Unicode-Zeichen `pValue` .  
  
 `ppd`  
 vorgenommen Das `mdParamDef` zugewiesene Token.  
  
## <a name="remarks"></a>Hinweise  

 Die Sequenzwerte in `ulParamSeq` beginnen mit 1 für Parameter. Ein Rückgabewert hat eine Sequenznummer von 0.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
