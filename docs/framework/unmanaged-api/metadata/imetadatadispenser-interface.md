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
ms.openlocfilehash: c798aeba46adf91a8c13f8143c00f02173a0bb52
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726105"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="8de28-102">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8de28-102">IMetaDataDispenser Interface</span></span>

<span data-ttu-id="8de28-103">Stellt Methoden bereit, um einen neuen Metadatenbereich zu erstellen, oder öffnet einen vorhandenen.</span><span class="sxs-lookup"><span data-stu-id="8de28-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8de28-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="8de28-104">Methods</span></span>  
  
|<span data-ttu-id="8de28-105">Methode</span><span class="sxs-lookup"><span data-stu-id="8de28-105">Method</span></span>|<span data-ttu-id="8de28-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8de28-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8de28-107">DefineScope-Methode</span><span class="sxs-lookup"><span data-stu-id="8de28-107">DefineScope Method</span></span>](imetadatadispenser-definescope-method.md)|<span data-ttu-id="8de28-108">Erstellt einen neuen Bereich im Speicher, in dem Sie neue Metadaten erstellen können.</span><span class="sxs-lookup"><span data-stu-id="8de28-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="8de28-109">OpenScope-Methode</span><span class="sxs-lookup"><span data-stu-id="8de28-109">OpenScope Method</span></span>](imetadatadispenser-openscope-method.md)|<span data-ttu-id="8de28-110">Öffnet eine vorhandene Datei auf dem Datenträger und ordnet Ihre Metadaten dem Arbeitsspeicher zu.</span><span class="sxs-lookup"><span data-stu-id="8de28-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="8de28-111">OpenScopeOnMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="8de28-111">OpenScopeOnMemory Method</span></span>](imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="8de28-112">Öffnet einen Arbeitsspeicher Bereich, der vorhandene Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="8de28-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="8de28-113">Das heißt, diese Methode öffnet einen angegebenen Bereich des Speichers, in dem die vorhandenen Daten als Metadaten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="8de28-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8de28-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8de28-114">Requirements</span></span>  

 <span data-ttu-id="8de28-115">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8de28-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8de28-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8de28-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8de28-117">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="8de28-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8de28-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8de28-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de28-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8de28-119">See also</span></span>

- [<span data-ttu-id="8de28-120">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8de28-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="8de28-121">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8de28-121">Metadata Interfaces</span></span>](metadata-interfaces.md)
