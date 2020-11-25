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
ms.openlocfilehash: 458a90bc47711d9f831805faa8468a49f3e0d305
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703996"
---
# <a name="imetadataimportgetfieldprops-method"></a>IMetaDataImport::GetFieldProps-Methode

Ruft Metadaten ab, die dem Feld zugeordnet sind, auf das durch das angegebene FieldDef-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
## <a name="parameters"></a>Parameter  

 `mb`  
 in Ein FieldDef-Token, das das Feld darstellt, für das zugeordnete Metadaten zu erhalten sind.  
  
 `pClass`  
 vorgenommen Ein Zeiger auf ein TypeDef-Token, das den Typ der Klasse darstellt, zu der das Feld gehört.  
  
 `szField`  
 vorgenommen Der Name des Felds.  
  
 `cchField`  
 in Die Größe des Puffers für *szField* in breit Zeichen.  
  
 `pchField`  
 vorgenommen Die tatsächliche Größe des zurückgegebenen Puffers.  
  
 `pdwAttr`  
 vorgenommen Flags, die den Metadaten des Felds zugeordnet sind.  
  
 `ppvSigBlob`  
 in Ein Zeiger auf den binären Metadatenwert, der das Feld beschreibt.  
  
 `pcbSigBlob`  
 vorgenommen Die Größe von in Bytes `ppvSigBlob` .  
  
 `pdwCPlusTypeFlag`  
 vorgenommen Ein Flag, das den Werttyp des Felds angibt.  
  
 `ppValue`  
 vorgenommen Ein konstanter Wert für das Feld.  
  
 `pcchValue`  
 vorgenommen Die Größe in Zeichen von `ppValue` , oder 0 (null), wenn keine Zeichenfolge vorhanden ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
