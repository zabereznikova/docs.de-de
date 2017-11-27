---
title: IMetaDataImport::GetMemberProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMemberProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b52d3130400310379c69eb0202217d1cd37ff18d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps-Methode
Ruft Metadateninformationen, einschließlich Name, binäre Signatur und relative virtuelle Adresse, von der <xref:System.Type> Member auf, die vom angegebenen Metadatentoken verwiesen wird.  
  
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
 [in] Das Token, das Element, um die zugehörigen Metadaten für erhalten verweist.  
  
 `pClass`  
 [out] Ein Zeiger auf das Metadatentoken, das die Klasse des Elements darstellt.  
  
 `szMember`  
 [out] Der Name des Elements.  
  
 `cchMember`  
 [in] Die Größe in Breitzeichen der `szMember` Puffer.  
  
 `pchMember`  
 [out] Die Größe in Breitzeichen mit den zurückgegebenen Namen.  
  
 `pdwAttr`  
 [out] Alle Flagwerte, die auf das Element angewendet wird.  
  
 `ppvSigBlob`  
 [out] Ein Zeiger auf die binäre Metadatensignatur des Members.  
  
 `pcbSigBlob`  
 [out] Die Größe in Bytes des `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Ein Zeiger auf die relative virtuelle Adresse des Elements.  
  
 `pdwImplFlags`  
 [out] Alle Methodenimplementierungsflags, die dem Element zugeordnet wird.  
  
 `pdwCPlusTypeFlag`  
 [out] Ein Flag, das kennzeichnet eine <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Eine Zeichenfolgenkonstante, die von diesem Element zurückgegeben.  
  
 `pcchValue`  
 [out] Die Größe in Zeichen des `ppValue`, oder NULL, wenn `ppValue` errichtet keine Zeichenfolge.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
