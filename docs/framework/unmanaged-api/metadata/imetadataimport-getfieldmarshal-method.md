---
title: IMetaDataImport::GetFieldMarshal-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetFieldMarshal
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a41b766dc377a62ad7d1d3ee7ebe5632a81cce2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetfieldmarshal-method"></a>IMetaDataImport::GetFieldMarshal-Methode
Ruft einen Zeiger auf den systemeigenen, nicht verwalteten Typ des Felds, das durch das angegebene Field-Metadatentoken dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `tk`  
 [in] Das Metadatentoken, das Interop-Marshalling-Informationen für die abzurufenden Felds darstellt.  
  
 `ppvNativeType`  
 [out] Ein Zeiger auf die Metadatensignatur der systemeigene Typ des Felds.  
  
 `pcbNativeType`  
 [out] Die Größe in Bytes des `ppvNativeType`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
