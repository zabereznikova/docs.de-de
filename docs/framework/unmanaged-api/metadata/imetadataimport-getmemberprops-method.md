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
ms.openlocfilehash: bc5bbba2fa4a95955e52a2e083a2097178b5d96a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437516"
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps-Methode
Ruft Informationen ab, die in den Metadaten für eine angegebene Element Definition, einschließlich des Namens, der binären Signatur und der relativen virtuellen Adresse, des <xref:System.Type> Members gespeichert sind, auf den durch das angegebene Metadatentoken verwiesen wird. Dies ist eine einfache Hilfsmethode: Wenn *MB* ein MethodDef-Wert ist, wird **GetMethod-** Eigenschaften aufgerufen. Wenn *MB* ein FieldDef-Wert ist, wird **GetField-** Eigenschaften aufgerufen. Weitere Informationen finden Sie in diesen anderen Methoden. 
  
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
 in Die Größe des `szMember` Puffers in breit Zeichen.  
  
 `pchMember`  
 vorgenommen Die Größe des zurückgegebenen Namens in breit Zeichen.  
  
 `pdwAttr`  
 vorgenommen Alle Flagwerte, die auf den Member angewendet werden.  
  
 `ppvSigBlob`  
 vorgenommen Ein Zeiger auf die binäre Metadatensignatur des Members.  
  
 `pcbSigBlob`  
 vorgenommen Die Größe `ppvSigBlob`in Byte.  
  
 `pulCodeRVA`  
 vorgenommen Ein Zeiger auf die relative virtuelle Adresse des Members.  
  
 `pdwImplFlags`  
 vorgenommen Alle Methodenimplementierungsflags, die dem Element zugeordnet sind.  
  
 `pdwCPlusTypeFlag`  
 vorgenommen Ein Flag, das eine <xref:System.ValueType>markiert. Dabei handelt es sich um einen der `ELEMENT_TYPE_*`-Werte.
  
 `ppValue`  
 vorgenommen Ein konstanter Zeichen folgen Wert, der von diesem Member zurückgegeben wird.  
  
 `pcchValue`  
 vorgenommen Die Größe in Zeichen `ppValue`, oder 0 (null), wenn `ppValue` keine Zeichenfolge enthält.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
