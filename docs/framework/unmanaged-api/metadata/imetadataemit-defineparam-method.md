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
ms.openlocfilehash: 2807458549db02598ba05f2aa80fa6ea6fbc5a13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177692"
---
# <a name="imetadataemitdefineparam-method"></a>IMetaDataEmit::DefineParam-Methode
Erstellt eine Parameterdefinition mit der angegebenen Signatur für die Methode, auf die vom angegebenen Token verwiesen wird, und ruft ein Token für diese Parameterdefinition ab.  
  
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
 [in] Das Token für die Methode, deren Parameter definiert wird.  
  
 `ulParamSeq`  
 [in] Die Parametersequenznummer.  
  
 `szName`  
 [in] Der Name des Parameters in Unicode.  
  
 `dwParamFlags`  
 [in] Flags für den Parameter. Dies ist eine `CorParamAttr` Bitmaske von Werten.  
  
 `dwCPlusTypeFlag`  
 [in] `ELEMENT_TYPE_` für den konstanten *\** Wert.  
  
 `pValue`  
 [in] Der konstante Wert für den Parameter.  
  
 `cchValue`  
 [in] Die Größe von in Unicode-Zeichen von `pValue`.  
  
 `ppd`  
 [out] Das `mdParamDef` token zugewiesen.  
  
## <a name="remarks"></a>Bemerkungen  
 Die Sequenzwerte `ulParamSeq` beginnen mit 1 für Parameter. Ein Rückgabewert hat die Sequenznummer 0.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
