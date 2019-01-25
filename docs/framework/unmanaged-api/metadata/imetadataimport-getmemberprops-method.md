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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98d7be5adc81cff09b121265e7d5b5f712122607
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611409"
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps-Methode
Ruft Metadateninformationen, einschließlich der Namen, die binäre Signatur und die relative virtuelle Adresse, von der <xref:System.Type> Member vom angegebenen Metadatentoken verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 `mb`  
 [in] Das Token, das Element zum Abrufen der zugehörigen Metadaten für verweist.  
  
 `pClass`  
 [out] Ein Zeiger auf das Metadatentoken, das die Klasse des Elements darstellt.  
  
 `szMember`  
 [out] Der Name des Elements.  
  
 `cchMember`  
 [in] Die Größe in Breitzeichen die `szMember` Puffer.  
  
 `pchMember`  
 [out] Die Größe in Breitzeichen der zurückgegebene Name.  
  
 `pdwAttr`  
 [out] Alle Flagwerte, die auf den Member angewendet wird.  
  
 `ppvSigBlob`  
 [out] Ein Zeiger auf die binäre Metadatensignatur des Elements.  
  
 `pcbSigBlob`  
 [out] Die Größe in Bytes der `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Ein Zeiger auf die relative virtuelle Adresse des Elements.  
  
 `pdwImplFlags`  
 [out] Alle Methodenimplementierungsflags, der dem Element zugeordnet wird.  
  
 `pdwCPlusTypeFlag`  
 [out] Ein Flag, das kennzeichnet eine <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Eine Zeichenfolgenkonstante, die von diesem Element zurückgegeben.  
  
 `pcchValue`  
 [out] Die Größe in Zeichen des `ppValue`, oder NULL, wenn `ppValue` errichtet keine Zeichenfolge.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
