---
title: IMetaDataEmit::DefineField-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineField
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2c4b5604c3daec78744eb8902a30750571b9f82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinefield-method"></a>IMetaDataEmit::DefineField-Methode
Erstellt eine Definition für ein Feld mit der angegebenen Metadatensignatur und ruft ein Token, Field-Definition ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 `td`  
 [in] Die `mdTypeDef` token für die einschließende Klasse oder Schnittstelle.  
  
 `szName`  
 [in] Der Name des Felds im Unicode-Format.  
  
 `dwFieldFlags`  
 [in] Die Attribute des Felds. Dies ist eine Bitmaske der `CorFieldAttr` Werte.  
  
 `pvSigBlob`  
 [in] Die Feldsignatur hat wie ein BLOB.  
  
 `cbSigBlob`  
 [in] Die Anzahl der Bytes im `pvSigBlob`.  
  
 `dwCPlusTypeFlage`  
 [in] Die `ELEMENT_TYPE_`  *\**  für den konstanten Wert. Dies ist ein `CorElementType` Wert. Wenn einen konstanten Wert für das Feld nicht definieren, verwenden Sie `ELEMENT_TYPE_END`.  
  
 `pValue`  
 [in] Der Konstante Wert für das Feld.  
  
 `cchValue`  
 [in] Die Größe in Zeichen (Unicode) der `pValue`.  
  
 `pmd`  
 [out] Die `mdFieldDef` Token zugewiesen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
