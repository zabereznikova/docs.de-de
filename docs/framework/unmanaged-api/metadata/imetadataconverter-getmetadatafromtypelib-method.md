---
title: IMetaDataConverter::GetMetaDataFromTypeLib-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataConverter.GetMetaDataFromTypeLib
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f2438c2d5402f6cff695ecc9832329ff826ded01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="72199-102">IMetaDataConverter::GetMetaDataFromTypeLib-Methode</span><span class="sxs-lookup"><span data-stu-id="72199-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="72199-103">Ruft einen Schnittstellenzeiger auf eine [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Instanz, die die Metadatensignatur der Typbibliothek, dargestellt durch das angegebene steht `ITypeLib` Instanz.</span><span class="sxs-lookup"><span data-stu-id="72199-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72199-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72199-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72199-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="72199-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="72199-106">[in] Zeiger auf ein `ITypeLib` Objekt, das die Typbibliothek darstellt.</span><span class="sxs-lookup"><span data-stu-id="72199-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="72199-107">[out] Zeiger auf einen Speicherort, der die Adresse des empfängt die `IMetaDataImport` Instanz, die die Metadatensignatur darstellt.</span><span class="sxs-lookup"><span data-stu-id="72199-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72199-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="72199-108">Requirements</span></span>  
 <span data-ttu-id="72199-109">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72199-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72199-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="72199-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72199-111">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="72199-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="72199-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72199-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72199-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72199-113">See Also</span></span>  
 [<span data-ttu-id="72199-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72199-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="72199-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72199-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
