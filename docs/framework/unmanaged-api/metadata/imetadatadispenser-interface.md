---
title: IMetaDataDispenser-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b7c183a6ef61b97920fef5c80b4abad50da25bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444869"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="5af43-102">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5af43-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="5af43-103">Stellt Methoden zum Erstellen eines neuen Bereichs für die Metadaten oder ein vorhandenes öffnen.</span><span class="sxs-lookup"><span data-stu-id="5af43-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5af43-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5af43-104">Methods</span></span>  
  
|<span data-ttu-id="5af43-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5af43-105">Method</span></span>|<span data-ttu-id="5af43-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5af43-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5af43-107">DefineScope-Methode</span><span class="sxs-lookup"><span data-stu-id="5af43-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="5af43-108">Erstellt einen neuen Bereich im Arbeitsspeicher, in dem Sie neue Metadaten erstellen können.</span><span class="sxs-lookup"><span data-stu-id="5af43-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="5af43-109">OpenScope-Methode</span><span class="sxs-lookup"><span data-stu-id="5af43-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="5af43-110">Öffnet eine Datei vorhandene, auf dem Datenträger, und seine Metadaten in den Arbeitsspeicher zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5af43-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="5af43-111">OpenScopeOnMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="5af43-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="5af43-112">Öffnet einen Bereich des Arbeitsspeichers, die vorhandenen Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="5af43-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="5af43-113">Diese Methode öffnet, also einen angegebenen Bereich des Arbeitsspeichers, in denen die vorhandenen Daten als Metadaten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="5af43-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5af43-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5af43-114">Requirements</span></span>  
 <span data-ttu-id="5af43-115">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5af43-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5af43-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5af43-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5af43-117">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5af43-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5af43-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5af43-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af43-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5af43-119">See Also</span></span>  
 [<span data-ttu-id="5af43-120">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5af43-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="5af43-121">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5af43-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
