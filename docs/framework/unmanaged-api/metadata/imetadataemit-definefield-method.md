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
ms.openlocfilehash: 2bc2b983171dc41d5ac37eda0359f1aaee4ebd6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725754"
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
 in Das `mdTypeDef` Token für die einschließende Klasse oder Schnittstelle.  
  
 `szName`  
 in Der Feldname in Unicode.  
  
 `dwFieldFlags`  
 in Die Feld Attribute. Dies ist eine Bitmaske von `CorFieldAttr` Werten.  
  
 `pvSigBlob`  
 in Die Feld Signatur als BLOB.  
  
 `cbSigBlob`  
 in Die Anzahl von Bytes in `pvSigBlob` .  
  
 `dwCPlusTypeFlag`  
 in Der `ELEMENT_TYPE_` *\** für den konstanten Wert. Dies ist ein- `CorElementType` Wert. Wenn Sie keinen konstanten Wert für das Feld definieren, verwenden Sie `ELEMENT_TYPE_END` .  
  
 `pValue`  
 in Der Konstante Wert für das Feld.  
  
 `cchValue`  
 in Die Größe in (Unicode) Zeichen von `pValue` .  
  
 `pmd`  
 vorgenommen Das `mdFieldDef` zugewiesene Token.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataEmit-Schnittstelle](imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](imetadataemit2-interface.md)
