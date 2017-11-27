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
ms.openlocfilehash: ce29990bf9e6b5b670a9a277442adac4ceef2947
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="89397-102">IMetaDataImport::GetFieldMarshal-Methode</span><span class="sxs-lookup"><span data-stu-id="89397-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="89397-103">Ruft einen Zeiger auf den systemeigenen, nicht verwalteten Typ des Felds, das durch das angegebene Field-Metadatentoken dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="89397-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89397-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89397-104">Syntax</span></span>  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89397-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="89397-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="89397-106">[in] Das Metadatentoken, das Interop-Marshalling-Informationen für die abzurufenden Felds darstellt.</span><span class="sxs-lookup"><span data-stu-id="89397-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="89397-107">[out] Ein Zeiger auf die Metadatensignatur der systemeigene Typ des Felds.</span><span class="sxs-lookup"><span data-stu-id="89397-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="89397-108">[out] Die Größe in Bytes des `ppvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="89397-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89397-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="89397-109">Requirements</span></span>  
 <span data-ttu-id="89397-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89397-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89397-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="89397-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89397-112">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="89397-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89397-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89397-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89397-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89397-114">See Also</span></span>  
 [<span data-ttu-id="89397-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89397-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="89397-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="89397-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
