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
ms.openlocfilehash: 0b27e36d901c12f5c384eb450e2019050a716b00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="4a547-102">IMetaDataConverter::GetMetaDataFromTypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="4a547-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="4a547-103">Ruft einen Zeiger auf eine [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Instanz, die die Metadatensignatur der Typbibliothek, auf die verwiesen wird durch das angegebene steht `ITypeInfo` Instanz.</span><span class="sxs-lookup"><span data-stu-id="4a547-103">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a547-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a547-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a547-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a547-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="4a547-106">[in] Ein Zeiger auf ein `ITypeInfo` Objekt, das auf die Typbibliothek verweist.</span><span class="sxs-lookup"><span data-stu-id="4a547-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="4a547-107">[out] Ein Zeiger auf einen Speicherort, der die Adresse des empfängt die `IMetaDataImport` Instanz, die die Metadatensignatur darstellt.</span><span class="sxs-lookup"><span data-stu-id="4a547-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a547-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4a547-108">Requirements</span></span>  
 <span data-ttu-id="4a547-109">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a547-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a547-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4a547-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a547-111">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4a547-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a547-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a547-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a547-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a547-113">See Also</span></span>  
 [<span data-ttu-id="4a547-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a547-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="4a547-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a547-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
