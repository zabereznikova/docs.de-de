---
title: IMetaDataFilter-Schnittstelle
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4196ff2cb2d4ebc401076f603a8a7fdc9b9c76ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143792"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="ff67b-102">IMetaDataFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff67b-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="ff67b-103">Stellt Methoden zum Markieren und Filtern von Metadatentoken bereit, um wiederkehrende Aktionen zu vermeiden, die bereits ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="ff67b-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff67b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ff67b-104">Methods</span></span>  
  
|<span data-ttu-id="ff67b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ff67b-105">Method</span></span>|<span data-ttu-id="ff67b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff67b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff67b-107">IsTokenMarked-Methode</span><span class="sxs-lookup"><span data-stu-id="ff67b-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="ff67b-108">Ruft einen Wert, der angibt, ob das angegebene Metadatentoken verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="ff67b-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="ff67b-109">MarkToken-Methode</span><span class="sxs-lookup"><span data-stu-id="ff67b-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="ff67b-110">Legt einen Wert, der angibt, dass das angegebene Metadatentoken verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="ff67b-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="ff67b-111">UnmarkAll-Methode</span><span class="sxs-lookup"><span data-stu-id="ff67b-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="ff67b-112">Entfernt die Markierungen für die Verarbeitung von allen Token im aktuellen Metadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="ff67b-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff67b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff67b-113">Requirements</span></span>  
 <span data-ttu-id="ff67b-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff67b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff67b-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ff67b-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff67b-116">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="ff67b-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="ff67b-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ff67b-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ff67b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff67b-118">See also</span></span>

- [<span data-ttu-id="ff67b-119">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ff67b-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
