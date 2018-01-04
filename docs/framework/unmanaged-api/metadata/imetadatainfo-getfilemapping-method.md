---
title: IMetaDataInfo::GetFileMapping-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataInfo.GetFileMapping
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f974230dc5ddf2a663f05fc06850f49f1de6e773
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="d2206-102">IMetaDataInfo::GetFileMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="d2206-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="d2206-103">Ruft den Speicherbereich, der die zugeordnete Datei und den Typ der Zuordnung ab.</span><span class="sxs-lookup"><span data-stu-id="d2206-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2206-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2206-104">Syntax</span></span>  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2206-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2206-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="d2206-106">[out] Ein Zeiger auf den Anfang der zugeordneten Datei.</span><span class="sxs-lookup"><span data-stu-id="d2206-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="d2206-107">[out] Die Größe des zugeordneten Bereichs.</span><span class="sxs-lookup"><span data-stu-id="d2206-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="d2206-108">Wenn `pdwMappingType` ist `fmFlat`, dies ist die Größe der Datei.</span><span class="sxs-lookup"><span data-stu-id="d2206-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="d2206-109">[out] Ein [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) Wert, der den Typ der Zuordnung angibt.</span><span class="sxs-lookup"><span data-stu-id="d2206-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="d2206-110">Gibt immer die aktuelle Implementierung der common Language Runtime (CLR) `fmFlat`.</span><span class="sxs-lookup"><span data-stu-id="d2206-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="d2206-111">Andere Werte sind für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="d2206-111">Other values are reserved for future use.</span></span> <span data-ttu-id="d2206-112">Allerdings sollten Sie immer den zurückgegebenen Wert überprüfen, da andere Werte möglicherweise in zukünftigen Versionen aktiviert oder service Releases.</span><span class="sxs-lookup"><span data-stu-id="d2206-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2206-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d2206-113">Return Value</span></span>  
  
|<span data-ttu-id="d2206-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d2206-114">HRESULT</span></span>|<span data-ttu-id="d2206-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2206-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d2206-116">Alle Ausgaben werden aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="d2206-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="d2206-117">NULL wurde als ein Wert des Arguments übergeben.</span><span class="sxs-lookup"><span data-stu-id="d2206-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="d2206-118">Die CLR-Implementierung kann keine Informationen zu den Speicherbereich bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d2206-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="d2206-119">Dies kann folgenden Ursachen haben:</span><span class="sxs-lookup"><span data-stu-id="d2206-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="d2206-120">-Die Metadatenbereich geöffnet wurde, mit der `ofWrite` oder `ofCopyMemory` Flag.</span><span class="sxs-lookup"><span data-stu-id="d2206-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="d2206-121">-Die Metadatenbereich geöffnet wurde, ohne die `ofReadOnly` Flag.</span><span class="sxs-lookup"><span data-stu-id="d2206-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="d2206-122">– Der [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) Methode wurde verwendet, um nur den Metadatenteil der Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d2206-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="d2206-123">-Die Datei ist keine Datei PE (portable Executable).</span><span class="sxs-lookup"><span data-stu-id="d2206-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="d2206-124">**Hinweis:** diese Bedingungen hängen von der CLR-Implementierung und sind wahrscheinlich abgeschwächt in zukünftigen Versionen der CLR.</span><span class="sxs-lookup"><span data-stu-id="d2206-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2206-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2206-125">Remarks</span></span>  
 <span data-ttu-id="d2206-126">Der Arbeitsspeicher, `ppvData` verweist, ist gültig, nur so lange im zugrunde liegenden Metadatenbereich geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="d2206-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="d2206-127">In der Reihenfolge für diese Methode funktioniert, wenn Sie durch Aufrufen der Metadaten einer Datei auf dem Datenträger in den Arbeitsspeicher zuordnen die [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) -Methode, die Sie angeben müssen die `ofReadOnly` Flag und Sie müssen nicht angeben der `ofWrite` oder `ofCopyMemory` Flag.</span><span class="sxs-lookup"><span data-stu-id="d2206-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="d2206-128">Die Auswahl der Zuordnung der Dateityp für die einzelnen Bereiche bezieht sich auf eine bestimmte Implementierung der CLR.</span><span class="sxs-lookup"><span data-stu-id="d2206-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="d2206-129">Er kann nicht vom Benutzer festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d2206-129">It cannot be set by the user.</span></span> <span data-ttu-id="d2206-130">Gibt die aktuelle Implementierung der CLR immer `fmFlat` in `pdwMappingType`, aber dies kann sich in zukünftigen Versionen der CLR oder zukünftigen Dienstversionen einer bestimmten Version ändern.</span><span class="sxs-lookup"><span data-stu-id="d2206-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="d2206-131">Überprüfen Sie den zurückgegebenen Wert immer `pdwMappingType`, da verschiedene Typen unterschiedliche Layouts und Offsets haben.</span><span class="sxs-lookup"><span data-stu-id="d2206-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="d2206-132">Übergeben NULL für einen der drei Parameter wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d2206-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="d2206-133">Gibt die Methode `E_INVALIDARG`, und dass keines der Ausgaben aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="d2206-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="d2206-134">Ignorieren von Zuordnungstyp oder die Größe des Bereichs kann dazu führen, dass nicht normale programmbeendigung.</span><span class="sxs-lookup"><span data-stu-id="d2206-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2206-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2206-135">Requirements</span></span>  
 <span data-ttu-id="d2206-136">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2206-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2206-137">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d2206-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2206-138">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d2206-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2206-139">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2206-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2206-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2206-140">See Also</span></span>  
 [<span data-ttu-id="d2206-141">IMetaDataInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2206-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 [<span data-ttu-id="d2206-142">CorFileMapping-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d2206-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
