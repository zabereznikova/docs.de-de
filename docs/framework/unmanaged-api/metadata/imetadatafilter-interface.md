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
ms.openlocfilehash: e8b15f478eb3b94b7cdcab3b69d54e7cc99be13b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440169"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="b6c1e-102">IMetaDataFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6c1e-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="b6c1e-103">Stellt Methoden zum Markieren und Filtern von Metadatentoken bereit, um wiederkehrende Aktionen zu vermeiden, die bereits ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="b6c1e-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6c1e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b6c1e-104">Methods</span></span>  
  
|<span data-ttu-id="b6c1e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b6c1e-105">Method</span></span>|<span data-ttu-id="b6c1e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6c1e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6c1e-107">IsTokenMarked-Methode</span><span class="sxs-lookup"><span data-stu-id="b6c1e-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="b6c1e-108">Ruft einen Wert ab, der angibt, ob das angegebene Metadatentoken verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="b6c1e-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="b6c1e-109">MarkToken-Methode</span><span class="sxs-lookup"><span data-stu-id="b6c1e-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="b6c1e-110">Legt einen Wert fest, der angibt, dass das angegebene Metadatentoken verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="b6c1e-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="b6c1e-111">UnmarkAll-Methode</span><span class="sxs-lookup"><span data-stu-id="b6c1e-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="b6c1e-112">Entfernt die Verarbeitungs Markierungen aus allen Token im aktuellen Metadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="b6c1e-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6c1e-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b6c1e-113">Requirements</span></span>  
 <span data-ttu-id="b6c1e-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6c1e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6c1e-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b6c1e-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6c1e-116">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="b6c1e-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6c1e-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6c1e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c1e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6c1e-118">See also</span></span>

- [<span data-ttu-id="b6c1e-119">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b6c1e-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
