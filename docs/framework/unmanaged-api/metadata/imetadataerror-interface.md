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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe2f683ae46d1ee6205f97536976a358e86fc53d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720378"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="88fbd-102">IMetaDataError-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="88fbd-102">IMetaDataError Interface</span></span>
<span data-ttu-id="88fbd-103">Stellt einen Rückrufmechanismus zur Meldung von Fehlern bei der Metadatenzusammenführung bereit.</span><span class="sxs-lookup"><span data-stu-id="88fbd-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88fbd-104">Die `IMetaDataError` Schnittstelle muss durch den Client implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="88fbd-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="88fbd-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="88fbd-105">Methods</span></span>  
  
|<span data-ttu-id="88fbd-106">Methode</span><span class="sxs-lookup"><span data-stu-id="88fbd-106">Method</span></span>|<span data-ttu-id="88fbd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88fbd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="88fbd-108">OnError-Methode</span><span class="sxs-lookup"><span data-stu-id="88fbd-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="88fbd-109">Stellt eine Benachrichtigung von Fehlern, während das Zusammenführen von Metadaten bereit.</span><span class="sxs-lookup"><span data-stu-id="88fbd-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88fbd-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="88fbd-110">Requirements</span></span>  
 <span data-ttu-id="88fbd-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88fbd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88fbd-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="88fbd-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="88fbd-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="88fbd-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="88fbd-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88fbd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88fbd-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88fbd-115">See also</span></span>
- [<span data-ttu-id="88fbd-116">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="88fbd-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
