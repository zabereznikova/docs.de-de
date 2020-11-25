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
ms.openlocfilehash: 2c22e45ca3d33b0a81ff0ecd90bf7574c45676bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701847"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="31557-102">IMetaDataFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31557-102">IMetaDataFilter Interface</span></span>

<span data-ttu-id="31557-103">Stellt Methoden zum Markieren und Filtern von Metadatentoken bereit, um wiederkehrende Aktionen zu vermeiden, die bereits ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="31557-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31557-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="31557-104">Methods</span></span>  
  
|<span data-ttu-id="31557-105">Methode</span><span class="sxs-lookup"><span data-stu-id="31557-105">Method</span></span>|<span data-ttu-id="31557-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="31557-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31557-107">IsTokenMarked-Methode</span><span class="sxs-lookup"><span data-stu-id="31557-107">IsTokenMarked Method</span></span>](imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="31557-108">Ruft einen Wert ab, der angibt, ob das angegebene Metadatentoken verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="31557-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="31557-109">MarkToken-Methode</span><span class="sxs-lookup"><span data-stu-id="31557-109">MarkToken Method</span></span>](imetadatafilter-marktoken-method.md)|<span data-ttu-id="31557-110">Legt einen Wert fest, der angibt, dass das angegebene Metadatentoken verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="31557-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="31557-111">UnmarkAll-Methode</span><span class="sxs-lookup"><span data-stu-id="31557-111">UnmarkAll Method</span></span>](imetadatafilter-unmarkall-method.md)|<span data-ttu-id="31557-112">Entfernt die Verarbeitungs Markierungen aus allen Token im aktuellen Metadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="31557-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="31557-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="31557-113">Requirements</span></span>  

 <span data-ttu-id="31557-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31557-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31557-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="31557-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="31557-116">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="31557-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31557-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31557-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31557-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31557-118">See also</span></span>

- [<span data-ttu-id="31557-119">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="31557-119">Metadata Interfaces</span></span>](metadata-interfaces.md)
