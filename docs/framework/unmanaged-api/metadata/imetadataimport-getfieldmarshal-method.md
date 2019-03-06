---
title: IMetaDataImport::GetFieldMarshal-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b3c9b879faf49ec7a485641c622d40a684dfb35
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469299"
---
# <a name="imetadataimportgetfieldmarshal-method"></a>IMetaDataImport::GetFieldMarshal-Methode
Ruft einen Zeiger auf den systemeigenen, nicht verwalteten Typ des Felds durch das angegebene Field-Metadatentoken dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tk`  
 [in] Das Metadatentoken, das Feld zum Abrufen von Interop-Marshalling-Informationen darstellt.  
  
 `ppvNativeType`  
 [out] Ein Zeiger auf die Metadatensignatur der systemeigenen Typ des Felds.  
  
 `pcbNativeType`  
 [out] Die Größe in Bytes der `ppvNativeType`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
