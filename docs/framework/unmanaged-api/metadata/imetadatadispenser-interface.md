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
ms.openlocfilehash: dda284fc86f0a82472c59d6bab08fd4a87364723
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225975"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="f173d-102">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f173d-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="f173d-103">Stellt Methoden zum Erstellen eines neuen Metadaten-Bereichs, oder öffnen Sie eine vorhandene Ressourcengruppe.</span><span class="sxs-lookup"><span data-stu-id="f173d-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f173d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f173d-104">Methods</span></span>  
  
|<span data-ttu-id="f173d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f173d-105">Method</span></span>|<span data-ttu-id="f173d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f173d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f173d-107">DefineScope-Methode</span><span class="sxs-lookup"><span data-stu-id="f173d-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="f173d-108">Erstellt einen neuen Bereich im Arbeitsspeicher, in dem Sie neue Metadaten erstellen können.</span><span class="sxs-lookup"><span data-stu-id="f173d-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="f173d-109">OpenScope-Methode</span><span class="sxs-lookup"><span data-stu-id="f173d-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="f173d-110">Öffnet eine vorhandene, auf dem Datenträger-Datei, und seine Metadaten in den Arbeitsspeicher zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f173d-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="f173d-111">OpenScopeOnMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="f173d-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="f173d-112">Öffnet einen Bereich des Arbeitsspeichers, die vorhandenen Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="f173d-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="f173d-113">Diese Methode öffnet, also einen angegebenen Bereich des Arbeitsspeichers, die in der die vorhandenen Daten als Metadaten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="f173d-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f173d-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f173d-114">Requirements</span></span>  
 <span data-ttu-id="f173d-115">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f173d-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f173d-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f173d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f173d-117">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f173d-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f173d-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f173d-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f173d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f173d-119">See also</span></span>

- [<span data-ttu-id="f173d-120">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f173d-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="f173d-121">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f173d-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
