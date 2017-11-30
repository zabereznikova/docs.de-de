---
title: IMetaDataImport::GetFieldProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetFieldProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d5874169e0f8c452b177309702444ea84858557e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetfieldprops-method"></a>IMetaDataImport::GetFieldProps-Methode
Ruft Metadaten ab, die dem Feld zugeordnet sind, auf das durch das angegebene FieldDef-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,   
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `mb`  
 [in] Ein FieldDef-Token, die zugeordneten Metadaten für die abzurufenden Felds darstellt.  
  
 `pClass`  
 [out] Ein Zeiger auf ein TypeDef-Token, das den Typ der Klasse darstellt, der das Feld angehört.  
  
 `szField`  
 [out] Der Name des Felds.  
  
 `cchField`  
 [in] Die Größe in Breitzeichen des Puffers für *SzField*.  
  
 `pchField`  
 [out] Die tatsächliche Größe des zurückgegebenen Puffers.  
  
 `pdwAttr`  
 [out] Flags, die Metadaten für das Feld zugeordnet werden.  
  
 `ppvSigBlob`  
 [in] Ein Zeiger auf den binären Metadatenwert, der das Feld beschreibt.  
  
 `pcbSigBlob`  
 [out] Die Größe in Bytes des `ppvSigBlob`.  
  
 `pdwCPlusTypeFlag`  
 [out] Ein Flag, das den Wert des Felds angibt.  
  
 `ppValue`  
 [out] Ein konstanter Wert für das Feld.  
  
 `pcchValue`  
 [out] Die Größe in Zeichen von `ppValue`, oder NULL, wenn keine Zeichenfolge vorhanden ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
