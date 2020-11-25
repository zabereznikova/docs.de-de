---
title: IMetaDataImport::GetMemberProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: f01d65a339c77e6af3e768c620f17ef0190c1e58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733218"
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps-Methode

Ruft Informationen ab, die in den Metadaten für eine angegebene Element Definition gespeichert sind, einschließlich des Namens, der binären Signatur und der relativen virtuellen Adresse des Members, auf den <xref:System.Type> das angegebene Metadatentoken verweist. Dies ist eine einfache Hilfsmethode: Wenn *MB* ein MethodDef-Wert ist, wird **GetMethod-** Eigenschaften aufgerufen. Wenn *MB* ein FieldDef-Wert ist, wird **GetField-** Eigenschaften aufgerufen. Weitere Informationen finden Sie in diesen anderen Methoden.
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] ULONG             *pulCodeRVA,
   [out] DWORD             *pdwImplFlags,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `mb`  
 in Das Token, das auf den Member verweist, für den die zugeordneten Metadaten zu erhalten sind.  
  
 `pClass`  
 vorgenommen Ein Zeiger auf das Metadatentoken, das die Klasse des Members darstellt.  
  
 `szMember`  
 vorgenommen Der Name des Members.  
  
 `cchMember`  
 in Die Größe des Puffers in breit Zeichen `szMember` .  
  
 `pchMember`  
 vorgenommen Die Größe des zurückgegebenen Namens in breit Zeichen.  
  
 `pdwAttr`  
 vorgenommen Alle Flagwerte, die auf den Member angewendet werden.  
  
 `ppvSigBlob`  
 vorgenommen Ein Zeiger auf die binäre Metadatensignatur des Members.  
  
 `pcbSigBlob`  
 vorgenommen Die Größe von in Bytes `ppvSigBlob` .  
  
 `pulCodeRVA`  
 vorgenommen Ein Zeiger auf die relative virtuelle Adresse des Members.  
  
 `pdwImplFlags`  
 vorgenommen Alle Methodenimplementierungsflags, die dem Element zugeordnet sind.  
  
 `pdwCPlusTypeFlag`  
 vorgenommen Ein Flag, das eine markiert <xref:System.ValueType> . Dabei handelt es sich um einen der- `ELEMENT_TYPE_*` Werte.
  
 `ppValue`  
 vorgenommen Ein konstanter Zeichen folgen Wert, der von diesem Member zurückgegeben wird.  
  
 `pcchValue`  
 vorgenommen Die Größe in Zeichen von `ppValue` oder 0 (null), wenn `ppValue` keine Zeichenfolge enthält.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
