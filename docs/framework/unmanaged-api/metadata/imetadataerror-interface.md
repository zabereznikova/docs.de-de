---
title: IMetaDataError-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError
helpviewer_keywords:
- IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type:
- apiref
ms.openlocfilehash: 44ecb73375f8a408fb0a38c3a2e2913f92ec4ca4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441622"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="0313a-102">IMetaDataError-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0313a-102">IMetaDataError Interface</span></span>
<span data-ttu-id="0313a-103">Provides a callback mechanism for reporting errors during the metadata merge.</span><span class="sxs-lookup"><span data-stu-id="0313a-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0313a-104">The `IMetaDataError` interface must be implemented by the client.</span><span class="sxs-lookup"><span data-stu-id="0313a-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0313a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="0313a-105">Methods</span></span>  
  
|<span data-ttu-id="0313a-106">Methode</span><span class="sxs-lookup"><span data-stu-id="0313a-106">Method</span></span>|<span data-ttu-id="0313a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0313a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0313a-108">OnError-Methode</span><span class="sxs-lookup"><span data-stu-id="0313a-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="0313a-109">Provides notification of errors that occur during the metadata merge.</span><span class="sxs-lookup"><span data-stu-id="0313a-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0313a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0313a-110">Requirements</span></span>  
 <span data-ttu-id="0313a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0313a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0313a-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0313a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0313a-113">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0313a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0313a-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0313a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0313a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0313a-115">See also</span></span>

- [<span data-ttu-id="0313a-116">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0313a-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
