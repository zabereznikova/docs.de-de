---
title: IMetaDataImport::GetSigFromToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetSigFromToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ab7df32641d4fcd093f1ed31eb9ed7c7954e6bf8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetsigfromtoken-method"></a>IMetaDataImport::GetSigFromToken-Methode
Ruft die binäre Metadatensignatur ab, die dem angegebenen Token zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `mdSig`  
 [in] Das Token für die binäre Metadatensignatur zurückgegeben werden soll.  
  
 `ppvSig`  
 [out] Ein Zeiger auf die zurückgegebenen Metadaten-Signatur.  
  
 `pcbSig`  
 [out] Die Größe in Bytes, der die binäre Metadatensignatur.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
