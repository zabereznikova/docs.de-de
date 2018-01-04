---
title: IMetaDataImport::GetUserString-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetUserString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 944d7e6413f35ad56af38dee90dc90f881c1d4cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetuserstring-method"></a>IMetaDataImport::GetUserString-Methode
Ruft das Zeichenfolgenliteral ab, das durch das angegebene Metadatentoken dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stk`  
 [in] Das Zeichenfolgentoken, das an die zugeordnete Zeichenfolge zurückgegeben.  
  
 `szString`  
 [out] Eine Kopie der angeforderten Zeichenfolge.  
  
 `cchString`  
 [in] Die maximale Größe in Breitzeichen der angeforderten `szString`.  
  
 `pchString`  
 [out] Die Größe in Breitzeichen des zurückgegebenen `szString`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
