---
title: IMetaDataImport::GetInterfaceImplProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetInterfaceImplProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: afc73536f332bd24fadee33d6321a106ccd175f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="df351-102">IMetaDataImport::GetInterfaceImplProps-Methode</span><span class="sxs-lookup"><span data-stu-id="df351-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="df351-103">Ruft einen Zeiger auf das Metadatentoken für die <xref:System.Type> , der die angegebene Methode implementiert und für die Schnittstelle, die diese Methode deklariert.</span><span class="sxs-lookup"><span data-stu-id="df351-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df351-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df351-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df351-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df351-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="df351-106">[in] Das Metadatentoken, das die Methode, die für die Klassen- und -Token zurückgeben, darstellt.</span><span class="sxs-lookup"><span data-stu-id="df351-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="df351-107">[out] Das Metadatentoken, das die Klasse, die die Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="df351-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="df351-108">[out] Das Metadatentoken, das die Schnittstelle, die die implementierte Methode definiert darstellt.</span><span class="sxs-lookup"><span data-stu-id="df351-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df351-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="df351-109">Requirements</span></span>  
 <span data-ttu-id="df351-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df351-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df351-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="df351-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df351-112">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="df351-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df351-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df351-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df351-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df351-114">See Also</span></span>  
 [<span data-ttu-id="df351-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df351-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="df351-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df351-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
