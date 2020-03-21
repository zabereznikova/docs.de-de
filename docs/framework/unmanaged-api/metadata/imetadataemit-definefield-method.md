---
title: IMetaDataEmit::DefineField-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 8ca5ab70f60de4d783800fb18612a8f04cb9cee1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177713"
---
# <a name="imetadataemitdefinefield-method"></a>IMetaDataEmit::DefineField-Methode
Erstellt eine Definition für ein Feld mit der angegebenen Metadatensignatur und ruft ein Token für diese Felddefinition ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 [in] Das `mdTypeDef` Token für die einschließende Klasse oder Schnittstelle.  
  
 `szName`  
 [in] Der Feldname in Unicode.  
  
 `dwFieldFlags`  
 [in] Die Feldattribute. Dies ist eine `CorFieldAttr` Bitmaske von Werten.  
  
 `pvSigBlob`  
 [in] Die Feldsignatur als BLOB.  
  
 `cbSigBlob`  
 [in] Die Anzahl der `pvSigBlob`Bytes in .  
  
 `dwCPlusTypeFlag`  
 [in] Die `ELEMENT_TYPE_` *\** für den konstanten Wert. Dies `CorElementType` ist ein Wert. Wenn Sie keinen konstanten Wert `ELEMENT_TYPE_END`für das Feld definieren, verwenden Sie .  
  
 `pValue`  
 [in] Der konstante Wert für das Feld.  
  
 `cchValue`  
 [in] Die Größe in (Unicode)-Zeichen von `pValue`.  
  
 `pmd`  
 [out] Das `mdFieldDef` token zugewiesen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
