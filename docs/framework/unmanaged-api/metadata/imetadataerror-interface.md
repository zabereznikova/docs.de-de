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
ms.openlocfilehash: 277b93267f0537c8e499a8d8f3b456c4396a975c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966342"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="c2c17-102">IMetaDataError-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2c17-102">IMetaDataError Interface</span></span>
<span data-ttu-id="c2c17-103">Stellt einen Rückrufmechanismus zum Melden von Fehlern während der Metadatenzusammenführung bereit.</span><span class="sxs-lookup"><span data-stu-id="c2c17-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2c17-104">Die `IMetaDataError` Schnittstelle muss vom Client implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="c2c17-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2c17-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="c2c17-105">Methods</span></span>  
  
|<span data-ttu-id="c2c17-106">Methode</span><span class="sxs-lookup"><span data-stu-id="c2c17-106">Method</span></span>|<span data-ttu-id="c2c17-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2c17-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2c17-108">OnError-Methode</span><span class="sxs-lookup"><span data-stu-id="c2c17-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="c2c17-109">Gibt Benachrichtigungen zu Fehlern, die während der Zusammenführung der Metadaten auftreten.</span><span class="sxs-lookup"><span data-stu-id="c2c17-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2c17-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2c17-110">Requirements</span></span>  
 <span data-ttu-id="c2c17-111">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2c17-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2c17-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c2c17-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2c17-113">**Fern** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2c17-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2c17-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2c17-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2c17-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2c17-115">See also</span></span>

- [<span data-ttu-id="c2c17-116">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c2c17-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
