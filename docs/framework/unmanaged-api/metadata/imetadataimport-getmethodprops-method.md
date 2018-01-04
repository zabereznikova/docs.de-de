---
title: IMetaDataImport::GetMethodProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMethodProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e4e0ae7dfed4b13ea83e16d6380443c9d1b72b06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmethodprops-method"></a>IMetaDataImport::GetMethodProps-Methode
Ruft die Metadaten ab, die der Methode zugeordnet sind, auf die durch das angegebene MethodDef-Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `mb`  
 [in] Das MethodDef-Token, das die Methode zum Zurückgeben von Metadaten für darstellt.  
  
 `pClass`  
 [out] Ein Zeiger auf ein TypeDef-Token, das den Typ darstellt, der die Methode implementiert.  
  
 `szMethod`  
 [out] Ein Zeiger auf einen Puffer, der den Namen der Methode.  
  
 `cchMethod`  
 [in] Die angeforderte Größe des `szMethod`.  
  
 `pchMethod`  
 [out] Ein Zeiger auf die Größe in Breitzeichen `szMethod`, oder im Falle von abschneiden, die tatsächliche Anzahl von Breitzeichen in den Methodennamen.  
  
 `pdwAttr`  
 [out] Ein Zeiger auf die Attribute der Methode zugeordnet.  
  
 `ppvSigBlob`  
 [out] Ein Zeiger auf die binäre Metadatensignatur der Methode.  
  
 `pcbSigBlob`  
 [out] Ein Zeiger auf die Größe in Bytes des `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Ein Zeiger auf die relative virtuelle Adresse der Methode.  
  
 `pdwImplFlags`  
 [out] Ein Zeiger auf die Implementierungsflags für die Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
