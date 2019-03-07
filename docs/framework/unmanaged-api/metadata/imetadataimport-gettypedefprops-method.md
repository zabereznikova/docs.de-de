---
title: IMetaDataImport::GetTypeDefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c4994dedcaac26f06f605532cc4579c78f4e8366
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501343"
---
# <a name="imetadataimportgettypedefprops-method"></a>IMetaDataImport::GetTypeDefProps-Methode
Gibt Metadateninformationen für die <xref:System.Type> durch das angegebene TypeDef-Token dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 [in] Die TypeDef-Token, das die den zurückzugebenden Metadaten darstellt.  
  
 `szTypeDef`  
 [out] Ein Puffer, die den Typnamen enthält.  
  
 `cchTypeDef`  
 [in] Die Größe in Breitzeichen `szTypeDef`.  
  
 `pchTypeDef`  
 [out] Die Anzahl der Breitzeichen, die in zurückgegebenen `szTypeDef`.  
  
 `pdwTypeDefFlags`  
 [out] Ein Zeiger auf Flags, die die Typdefinition ändern. Dieser Wert ist eine Bitmaske aus der [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) Enumeration.  
  
 `ptkExtends`  
 [out] Eine TypeDef oder TypeRef-Metadaten-Token, das den Basistyp des angeforderten Typs darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
