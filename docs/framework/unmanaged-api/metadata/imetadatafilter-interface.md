---
title: IMetaDataFilter-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0918802a146940fb7579279e56f752bd114c746c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="b35db-102">IMetaDataFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b35db-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="b35db-103">Stellt Methoden zum Markieren und Filtern von Metadatentoken bereit, um wiederkehrende Aktionen zu vermeiden, die bereits ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="b35db-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b35db-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b35db-104">Methods</span></span>  
  
|<span data-ttu-id="b35db-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b35db-105">Method</span></span>|<span data-ttu-id="b35db-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b35db-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b35db-107">IsTokenMarked-Methode</span><span class="sxs-lookup"><span data-stu-id="b35db-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="b35db-108">Ruft einen Wert, der angibt, ob das angegebene Metadatentoken verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="b35db-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="b35db-109">MarkToken-Methode</span><span class="sxs-lookup"><span data-stu-id="b35db-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="b35db-110">Legt einen Wert, der angibt, dass das angegebene Metadatentoken verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="b35db-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="b35db-111">UnmarkAll-Methode</span><span class="sxs-lookup"><span data-stu-id="b35db-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="b35db-112">Entfernt die Markierungen für die Verarbeitung von allen Token im aktuellen Metadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="b35db-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b35db-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b35db-113">Requirements</span></span>  
 <span data-ttu-id="b35db-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b35db-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b35db-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b35db-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b35db-116">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="b35db-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b35db-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b35db-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b35db-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b35db-118">See Also</span></span>  
 [<span data-ttu-id="b35db-119">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b35db-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
