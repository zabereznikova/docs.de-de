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
ms.openlocfilehash: 1c264bfd31f8cd31bacf2d194ddbd07338569294
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447169"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="13dce-102">IMetaDataError-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13dce-102">IMetaDataError Interface</span></span>
<span data-ttu-id="13dce-103">Stellt einen Rückrufmechanismus zur Meldung von Fehlern beim Zusammenführen von Metadaten bereit.</span><span class="sxs-lookup"><span data-stu-id="13dce-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13dce-104">Die `IMetaDataError` -Schnittstelle muss vom Client implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="13dce-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13dce-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="13dce-105">Methods</span></span>  
  
|<span data-ttu-id="13dce-106">Methode</span><span class="sxs-lookup"><span data-stu-id="13dce-106">Method</span></span>|<span data-ttu-id="13dce-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13dce-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13dce-108">OnError-Methode</span><span class="sxs-lookup"><span data-stu-id="13dce-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="13dce-109">Stellt eine Benachrichtigung von Fehlern, die auftreten, während das Zusammenführen von Metadaten bereit.</span><span class="sxs-lookup"><span data-stu-id="13dce-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13dce-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13dce-110">Requirements</span></span>  
 <span data-ttu-id="13dce-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13dce-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13dce-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="13dce-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13dce-113">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="13dce-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13dce-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13dce-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13dce-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13dce-115">See Also</span></span>  
 [<span data-ttu-id="13dce-116">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="13dce-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
