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
ms.openlocfilehash: 37f1f6055ec8fa68fe804780d2893d20c978e6bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188629"
---
# <a name="imetadataerror-interface"></a><span data-ttu-id="8a921-102">IMetaDataError-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a921-102">IMetaDataError Interface</span></span>
<span data-ttu-id="8a921-103">Stellt einen Rückrufmechanismus zur Meldung von Fehlern bei der Metadatenzusammenführung bereit.</span><span class="sxs-lookup"><span data-stu-id="8a921-103">Provides a callback mechanism for reporting errors during the metadata merge.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a921-104">Die `IMetaDataError` Schnittstelle muss durch den Client implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="8a921-104">The `IMetaDataError` interface must be implemented by the client.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a921-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="8a921-105">Methods</span></span>  
  
|<span data-ttu-id="8a921-106">Methode</span><span class="sxs-lookup"><span data-stu-id="8a921-106">Method</span></span>|<span data-ttu-id="8a921-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a921-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a921-108">OnError-Methode</span><span class="sxs-lookup"><span data-stu-id="8a921-108">OnError Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|<span data-ttu-id="8a921-109">Stellt eine Benachrichtigung von Fehlern, während das Zusammenführen von Metadaten bereit.</span><span class="sxs-lookup"><span data-stu-id="8a921-109">Provides notification of errors that occur during the metadata merge.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a921-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a921-110">Requirements</span></span>  
 <span data-ttu-id="8a921-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a921-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a921-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8a921-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a921-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="8a921-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8a921-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8a921-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8a921-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a921-115">See also</span></span>

- [<span data-ttu-id="8a921-116">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8a921-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
