---
title: IMetaDataEmit2-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
ms.openlocfilehash: 7ceae6f7713ab0eb1feff550838325df0ea52de2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447919"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="e1b8a-102">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e1b8a-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="e1b8a-103">Erweitert die [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) -Schnittstelle hauptsächlich, um die Möglichkeit zu bieten, mit generischen Typen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e1b8a-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1b8a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e1b8a-104">Methods</span></span>  
  
|<span data-ttu-id="e1b8a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e1b8a-105">Method</span></span>|<span data-ttu-id="e1b8a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1b8a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1b8a-107">DefineGenericParam-Methode</span><span class="sxs-lookup"><span data-stu-id="e1b8a-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="e1b8a-108">Erstellt eine Definition für einen generischen Typparameter und ruft ein Token für diesen generischen Typparameter ab.</span><span class="sxs-lookup"><span data-stu-id="e1b8a-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="e1b8a-109">DefineMethodSpec-Methode</span><span class="sxs-lookup"><span data-stu-id="e1b8a-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="e1b8a-110">Erstellt eine generische Instanz einer Methode und ruft ein Token für die Definition ab.</span><span class="sxs-lookup"><span data-stu-id="e1b8a-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="e1b8a-111">GetDeltaSaveSize-Methode</span><span class="sxs-lookup"><span data-stu-id="e1b8a-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="e1b8a-112">Ruft einen Wert ab, der den Unterschied in der Größe der Daten angibt, die zum Ausdrücken der Änderungen für die aktuelle Edit-and-Continue-Sitzung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e1b8a-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="e1b8a-113">ResetENCLog-Methode</span><span class="sxs-lookup"><span data-stu-id="e1b8a-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="e1b8a-114">Setzt das Edit-and-Continue-Protokoll zurück und startet eine neue Sitzung.</span><span class="sxs-lookup"><span data-stu-id="e1b8a-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="e1b8a-115">SaveDelta-Methode</span><span class="sxs-lookup"><span data-stu-id="e1b8a-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="e1b8a-116">Speichert Änderungen aus der aktuellen Bearbeitungs-und fortsetzungssitzung in der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="e1b8a-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="e1b8a-117">SaveDeltaToMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="e1b8a-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="e1b8a-118">Speichert Änderungen aus der aktuellen Bearbeitungs-und fortsetzungssitzung in den Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="e1b8a-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="e1b8a-119">SaveDeltaToStream-Methode</span><span class="sxs-lookup"><span data-stu-id="e1b8a-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="e1b8a-120">Speichert Änderungen aus der aktuellen Edit-and-Continue-Sitzung in den angegebenen Stream.</span><span class="sxs-lookup"><span data-stu-id="e1b8a-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="e1b8a-121">SetGenericParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="e1b8a-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="e1b8a-122">Legt Eigenschaftswerte für die generische Parameterdefinition fest, auf die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e1b8a-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1b8a-123">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e1b8a-123">Requirements</span></span>  
 <span data-ttu-id="e1b8a-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1b8a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1b8a-125">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e1b8a-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e1b8a-126">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1b8a-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e1b8a-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1b8a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1b8a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1b8a-128">See also</span></span>

- [<span data-ttu-id="e1b8a-129">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e1b8a-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="e1b8a-130">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e1b8a-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
