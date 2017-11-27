---
title: IMetaDataEmit2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2
helpviewer_keywords: IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 235134c66395f04a87ed4f3325f5cc4cd9fecfc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="4a8bd-102">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a8bd-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="4a8bd-103">Erweitert die [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) Schnittstelle in erster Linie und die Arbeit mit generischen Typen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="4a8bd-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4a8bd-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4a8bd-104">Methods</span></span>  
  
|<span data-ttu-id="4a8bd-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4a8bd-105">Method</span></span>|<span data-ttu-id="4a8bd-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a8bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a8bd-107">DefineGenericParam-Methode</span><span class="sxs-lookup"><span data-stu-id="4a8bd-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="4a8bd-108">Erstellt eine Definition für einen generischen Typparameter, und ruft ein Token an den generischen Typparameter ab.</span><span class="sxs-lookup"><span data-stu-id="4a8bd-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="4a8bd-109">DefineMethodSpec-Methode</span><span class="sxs-lookup"><span data-stu-id="4a8bd-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="4a8bd-110">Erstellt eine generische Instanz einer Methode und ruft ein Token für die Definition.</span><span class="sxs-lookup"><span data-stu-id="4a8bd-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="4a8bd-111">GetDeltaSaveSize-Methode</span><span class="sxs-lookup"><span data-stu-id="4a8bd-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="4a8bd-112">Ruft einen Wert, der angibt, des Unterschied in der Größe der Daten, die erforderlich sind, um die Änderungen für die aktuelle Sitzung mit bearbeiten und Fortfahren auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="4a8bd-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="4a8bd-113">ResetENCLog-Methode</span><span class="sxs-lookup"><span data-stu-id="4a8bd-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="4a8bd-114">Setzt das Bearbeiten und Fortfahren-Protokoll zurück und startet eine neue Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4a8bd-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="4a8bd-115">SaveDelta-Methode</span><span class="sxs-lookup"><span data-stu-id="4a8bd-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="4a8bd-116">Speichert Änderungen aus der aktuellen Sitzung mit bearbeiten und fortfahren, in der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="4a8bd-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="4a8bd-117">SaveDeltaToMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="4a8bd-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="4a8bd-118">Speichert Änderungen am Speicher aus der aktuellen Sitzung mit bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="4a8bd-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="4a8bd-119">SaveDeltaToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="4a8bd-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="4a8bd-120">Speichert Änderungen aus der aktuellen Sitzung mit bearbeiten und Fortfahren im angegebenen Stream.</span><span class="sxs-lookup"><span data-stu-id="4a8bd-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="4a8bd-121">SetGenericParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="4a8bd-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="4a8bd-122">Legt Eigenschaftswerte für die Definition der generischen Parameter durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4a8bd-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a8bd-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4a8bd-123">Requirements</span></span>  
 <span data-ttu-id="4a8bd-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a8bd-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a8bd-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4a8bd-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a8bd-126">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4a8bd-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a8bd-127">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a8bd-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a8bd-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a8bd-128">See Also</span></span>  
 [<span data-ttu-id="4a8bd-129">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4a8bd-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="4a8bd-130">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a8bd-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
