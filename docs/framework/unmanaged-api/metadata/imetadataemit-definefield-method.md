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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 057bae1d702fa091ebc3d3178c9fba35d5dd3d90
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777659"
---
# <a name="imetadataemitdefinefield-method"></a>IMetaDataEmit::DefineField-Methode
Erstellt eine Definition für ein Feld mit der angegebenen Metadaten-Signatur und ruft ein Token, Field-Definition ab.  
  
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
 [in] Die `mdTypeDef` token für die einschließende Klasse oder Schnittstelle.  
  
 `szName`  
 [in] Der Name des Felds im Unicode-Format.  
  
 `dwFieldFlags`  
 [in] Die Attribute des Felds. Dies ist eine Bitmaske der `CorFieldAttr` Werte.  
  
 `pvSigBlob`  
 [in] Die Feldsignatur als BLOB.  
  
 `cbSigBlob`  
 [in] Die Anzahl der Bytes im `pvSigBlob`.  
  
 `dwCPlusTypeFlag`  
 [in] Die `ELEMENT_TYPE_` *\** für den konstanten Wert. Dies ist eine `CorElementType` Wert. Wenn einen konstanten Wert für das Feld nicht zu definieren, verwenden Sie `ELEMENT_TYPE_END`.  
  
 `pValue`  
 [in] Der Konstante Wert für das Feld.  
  
 `cchValue`  
 [in] Die Größe in Zeichen (Unicode) der `pValue`.  
  
 `pmd`  
 [out] Die `mdFieldDef` zugewiesene Token.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
