---
title: IMetaDataInfo::GetFileMapping-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4c6a9473a698e4635c8b5cc9fb58963334dfd65e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992276"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="390fc-102">IMetaDataInfo::GetFileMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="390fc-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="390fc-103">Ruft den Arbeitsspeicherbereich von der zugeordneten Datei und den Typ der Zuordnung ab.</span><span class="sxs-lookup"><span data-stu-id="390fc-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="390fc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="390fc-104">Syntax</span></span>  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="390fc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="390fc-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="390fc-106">[out] Ein Zeiger auf den Anfang der zugeordneten Datei.</span><span class="sxs-lookup"><span data-stu-id="390fc-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="390fc-107">[out] Die Größe des zugeordneten Bereichs.</span><span class="sxs-lookup"><span data-stu-id="390fc-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="390fc-108">Wenn `pdwMappingType` ist `fmFlat`, dies ist die Größe der Datei.</span><span class="sxs-lookup"><span data-stu-id="390fc-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="390fc-109">[out] Ein [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) Wert, der den Typ der Zuordnung angibt.</span><span class="sxs-lookup"><span data-stu-id="390fc-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="390fc-110">Die aktuelle Implementierung der common Language Runtime (CLR) gibt immer `fmFlat`.</span><span class="sxs-lookup"><span data-stu-id="390fc-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="390fc-111">Andere Werte sind für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="390fc-111">Other values are reserved for future use.</span></span> <span data-ttu-id="390fc-112">Allerdings sollten Sie den zurückgegebenen Wert, immer überprüfen, da andere Werte werden, in zukünftigen Versionen aktiviert können oder service Releases.</span><span class="sxs-lookup"><span data-stu-id="390fc-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="390fc-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="390fc-113">Return Value</span></span>  
  
|<span data-ttu-id="390fc-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="390fc-114">HRESULT</span></span>|<span data-ttu-id="390fc-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="390fc-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="390fc-116">Alle Ausgaben werden aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="390fc-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="390fc-117">NULL wurde als Argumentwert übergeben.</span><span class="sxs-lookup"><span data-stu-id="390fc-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="390fc-118">Die CLR-Implementierung kann keine Informationen zu den Arbeitsspeicherbereich bieten.</span><span class="sxs-lookup"><span data-stu-id="390fc-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="390fc-119">Dies kann aus den folgenden Gründen geschehen:</span><span class="sxs-lookup"><span data-stu-id="390fc-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="390fc-120">– Der Metadatenbereich wurde geöffnet, mit der `ofWrite` oder `ofCopyMemory` Flag.</span><span class="sxs-lookup"><span data-stu-id="390fc-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="390fc-121">-Der Metadatenbereich geöffnet wurde, ohne die `ofReadOnly` Flag.</span><span class="sxs-lookup"><span data-stu-id="390fc-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="390fc-122">– Die [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) Methode wurde verwendet, um nur die Metadatenteil der Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="390fc-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="390fc-123">-Die Datei ist keiner PE (portable Executable)-Datei.</span><span class="sxs-lookup"><span data-stu-id="390fc-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="390fc-124">**Hinweis**:  Diese Bedingungen hängen von der CLR-Implementierung, und Sie werden wahrscheinlich in zukünftigen Versionen der CLR herabgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="390fc-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="390fc-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="390fc-125">Remarks</span></span>  
 <span data-ttu-id="390fc-126">Der Arbeitsspeicher, `ppvData` verweist, ist gültig, nur so lange im zugrunde liegenden Metadatenbereich geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="390fc-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="390fc-127">In der Reihenfolge für diese Methode funktioniert, wenn Sie die Metadaten einer Datei auf dem Datenträger durch den Aufruf in den Arbeitsspeicher zuordnen die [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) -Methode, die Sie angeben müssen die `ofReadOnly` Flag und Sie müssen nicht angeben. die `ofWrite` oder `ofCopyMemory` Flag.</span><span class="sxs-lookup"><span data-stu-id="390fc-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="390fc-128">Die Auswahl der Zuordnung der Dateityp für jeden Bereich bezieht sich auf eine Implementierung der CLR.</span><span class="sxs-lookup"><span data-stu-id="390fc-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="390fc-129">Es kann nicht vom Benutzer festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="390fc-129">It cannot be set by the user.</span></span> <span data-ttu-id="390fc-130">Gibt die aktuelle Implementierung der CLR immer `fmFlat` in `pdwMappingType`, aber dies kann sich in zukünftigen Versionen der CLR oder in Zukunft Service Releases von einer bestimmten Version ändern.</span><span class="sxs-lookup"><span data-stu-id="390fc-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="390fc-131">Sie sollten immer den zurückgegebenen Wert überprüfen, `pdwMappingType`, da verschiedene Typen unterschiedliche Layouts und Offsets haben.</span><span class="sxs-lookup"><span data-stu-id="390fc-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="390fc-132">Übergeben NULL für eine beliebige der drei Parameter wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="390fc-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="390fc-133">Gibt die Methode zurück `E_INVALIDARG`, und keine Ausgabe wird ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="390fc-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="390fc-134">Ignorieren den Zuordnungstyp oder die Größe des Bereichs kann dazu führen, dass nicht normale programmbeendigung.</span><span class="sxs-lookup"><span data-stu-id="390fc-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="390fc-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="390fc-135">Requirements</span></span>  
 <span data-ttu-id="390fc-136">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="390fc-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="390fc-137">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="390fc-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="390fc-138">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="390fc-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="390fc-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="390fc-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="390fc-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="390fc-140">See also</span></span>

- [<span data-ttu-id="390fc-141">IMetaDataInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="390fc-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="390fc-142">CorFileMapping-Enumeration</span><span class="sxs-lookup"><span data-stu-id="390fc-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
