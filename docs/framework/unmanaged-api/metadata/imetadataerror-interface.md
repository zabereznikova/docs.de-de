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
ms.openlocfilehash: 5f5e04787ce0ab0e1c8ecf3c19ba37e76ba38bfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701925"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="b195b-102">IMetaDataError-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b195b-102">IMetaDataError Interface</span></span>

<span data-ttu-id="b195b-103">Stellt einen Rückrufmechanismus zum Melden von Fehlern während der Metadatenzusammenführung bereit.</span><span class="sxs-lookup"><span data-stu-id="b195b-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b195b-104">Die `IMetaDataError` Schnittstelle muss vom Client implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="b195b-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b195b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b195b-105">Methods</span></span>  
  
|<span data-ttu-id="b195b-106">Methode</span><span class="sxs-lookup"><span data-stu-id="b195b-106">Method</span></span>|<span data-ttu-id="b195b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b195b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b195b-108">OnError-Methode</span><span class="sxs-lookup"><span data-stu-id="b195b-108">OnError Method</span></span>](imetadataerror-onerror-method.md)|<span data-ttu-id="b195b-109">Gibt Benachrichtigungen zu Fehlern, die während der Zusammenführung der Metadaten auftreten.</span><span class="sxs-lookup"><span data-stu-id="b195b-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b195b-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b195b-110">Requirements</span></span>  

 <span data-ttu-id="b195b-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b195b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b195b-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b195b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b195b-113">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="b195b-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b195b-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b195b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b195b-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b195b-115">See also</span></span>

- [<span data-ttu-id="b195b-116">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b195b-116">Metadata Interfaces</span></span>](metadata-interfaces.md)
