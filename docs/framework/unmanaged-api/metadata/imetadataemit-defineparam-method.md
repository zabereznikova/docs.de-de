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
ms.openlocfilehash: 5c81bc82e19bce658336e4860a61f2721e17423d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431691"
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
 in Die Größe `pValue`in Unicode-Zeichen.  
  
 `ppd`  
 vorgenommen Das zugewiesene `mdParamDef` Token.  
  
## <a name="remarks"></a>Hinweise  
 Die Sequenzwerte in `ulParamSeq` mit 1 für Parameter beginnen. Ein Rückgabewert hat eine Sequenznummer von 0.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
