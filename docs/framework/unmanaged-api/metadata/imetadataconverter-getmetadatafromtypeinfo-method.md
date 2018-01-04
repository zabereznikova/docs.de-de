---
title: IMetaDataConverter::GetMetaDataFromTypeInfo-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataConverter.GetMetaDataFromTypeInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66e090efc9ce8a8fc1ca5de8d8f7a60f9ca17b9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a>IMetaDataConverter::GetMetaDataFromTypeInfo-Methode
Ruft einen Zeiger auf eine [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Instanz, die die Metadatensignatur der Typbibliothek, auf die verwiesen wird durch das angegebene steht `ITypeInfo` Instanz.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pITI`  
 [in] Ein Zeiger auf ein `ITypeInfo` Objekt, das auf die Typbibliothek verweist.  
  
 `ppMDI`  
 [out] Ein Zeiger auf einen Speicherort, der die Adresse des empfängt die `IMetaDataImport` Instanz, die die Metadatensignatur darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
