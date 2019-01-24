---
title: IMetaDataImport::GetFieldProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fc4e8140485902e4677bca0228bc125c64b497f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671862"
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
 [in] Ein FieldDef-Token, das Feld zum Abrufen der zugehörigen Metadaten für darstellt.  
  
 `pClass`  
 [out] Ein Zeiger auf ein TypeDef-Token, das den Typ der Klasse darstellt, das Feld gehört.  
  
 `szField`  
 [out] Der Name des Felds.  
  
 `cchField`  
 [in] Die Größe in Zeichen des Puffers für *SzField*.  
  
 `pchField`  
 [out] Die tatsächliche Größe des zurückgegebenen Puffers.  
  
 `pdwAttr`  
 [out] Flags, die mit den Metadaten des Felds.  
  
 `ppvSigBlob`  
 [in] Ein Zeiger auf die binäre Metadatenwert, der die Felder beschrieben werden.  
  
 `pcbSigBlob`  
 [out] Die Größe in Bytes der `ppvSigBlob`.  
  
 `pdwCPlusTypeFlag`  
 [out] Ein Flag, das den Wert des Felds angibt.  
  
 `ppValue`  
 [out] Ein konstanter Wert für das Feld.  
  
 `pcchValue`  
 [out] Die Größe in Zeichen des `ppValue`, oder NULL, wenn keine Zeichenfolge vorhanden ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
