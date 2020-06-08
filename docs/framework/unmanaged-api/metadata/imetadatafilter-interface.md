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
ms.openlocfilehash: 821936d20a421739e8eb3d5df228888df7f022e3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503782"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="ffd35-102">IMetaDataFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ffd35-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="ffd35-103">Stellt Methoden zum Markieren und Filtern von Metadatentoken bereit, um wiederkehrende Aktionen zu vermeiden, die bereits ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="ffd35-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ffd35-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ffd35-104">Methods</span></span>  
  
|<span data-ttu-id="ffd35-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ffd35-105">Method</span></span>|<span data-ttu-id="ffd35-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ffd35-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ffd35-107">IsTokenMarked-Methode</span><span class="sxs-lookup"><span data-stu-id="ffd35-107">IsTokenMarked Method</span></span>](imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="ffd35-108">Ruft einen Wert ab, der angibt, ob das angegebene Metadatentoken verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="ffd35-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="ffd35-109">MarkToken-Methode</span><span class="sxs-lookup"><span data-stu-id="ffd35-109">MarkToken Method</span></span>](imetadatafilter-marktoken-method.md)|<span data-ttu-id="ffd35-110">Legt einen Wert fest, der angibt, dass das angegebene Metadatentoken verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="ffd35-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="ffd35-111">UnmarkAll-Methode</span><span class="sxs-lookup"><span data-stu-id="ffd35-111">UnmarkAll Method</span></span>](imetadatafilter-unmarkall-method.md)|<span data-ttu-id="ffd35-112">Entfernt die Verarbeitungs Markierungen aus allen Token im aktuellen Metadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="ffd35-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffd35-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ffd35-113">Requirements</span></span>  
 <span data-ttu-id="ffd35-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffd35-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffd35-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ffd35-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ffd35-116">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="ffd35-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ffd35-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffd35-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffd35-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="ffd35-118">See also</span></span>

- [<span data-ttu-id="ffd35-119">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ffd35-119">Metadata Interfaces</span></span>](metadata-interfaces.md)
