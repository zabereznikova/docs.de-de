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
ms.openlocfilehash: 0cd2071d4410615a08e774ba30e0e8fe8d1fa7c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436177"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="0d357-102">IMetaDataInfo::GetFileMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="0d357-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="0d357-103">Ruft den Speicherbereich der zugeordneten Datei und den Typ der Zuordnung ab.</span><span class="sxs-lookup"><span data-stu-id="0d357-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d357-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d357-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d357-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0d357-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="0d357-106">vorgenommen Ein Zeiger auf den Anfang der zugeordneten Datei.</span><span class="sxs-lookup"><span data-stu-id="0d357-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="0d357-107">vorgenommen Die Größe des zugeordneten Bereichs.</span><span class="sxs-lookup"><span data-stu-id="0d357-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="0d357-108">Wenn `pdwMappingType` `fmFlat`ist, ist dies die Größe der Datei.</span><span class="sxs-lookup"><span data-stu-id="0d357-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="0d357-109">vorgenommen Ein [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) -Wert, der den Typ der Zuordnung angibt.</span><span class="sxs-lookup"><span data-stu-id="0d357-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="0d357-110">Die aktuelle Implementierung des Common Language Runtime (CLR) gibt immer `fmFlat`zurück.</span><span class="sxs-lookup"><span data-stu-id="0d357-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="0d357-111">Andere Werte sind für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="0d357-111">Other values are reserved for future use.</span></span> <span data-ttu-id="0d357-112">Sie sollten jedoch immer den zurückgegebenen Wert überprüfen, weil andere Werte möglicherweise in zukünftigen Versionen oder Dienst Releases aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="0d357-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d357-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0d357-113">Return Value</span></span>  
  
|<span data-ttu-id="0d357-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d357-114">HRESULT</span></span>|<span data-ttu-id="0d357-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d357-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0d357-116">Alle Ausgaben werden aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="0d357-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="0d357-117">NULL wurde als Argument Wert übermittelt.</span><span class="sxs-lookup"><span data-stu-id="0d357-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="0d357-118">Die CLR-Implementierung kann keine Informationen über die Speicher Region bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0d357-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="0d357-119">Dafür können die folgenden Gründe verantwortlich sein:</span><span class="sxs-lookup"><span data-stu-id="0d357-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="0d357-120">-Der Metadatenbereich wurde mit dem `ofWrite`-oder `ofCopyMemory`-Flag geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0d357-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="0d357-121">-Der Metadatenbereich wurde ohne das `ofReadOnly`-Flag geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0d357-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="0d357-122">-Die [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) -Methode wurde verwendet, um nur den Metadatenteil der Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0d357-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="0d357-123">-Die Datei ist keine portable ausführbare Datei (PE).</span><span class="sxs-lookup"><span data-stu-id="0d357-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="0d357-124">**Hinweis:**  Diese Bedingungen sind von der CLR-Implementierung abhängig und werden wahrscheinlich in zukünftigen Versionen der CLR geschwächt.</span><span class="sxs-lookup"><span data-stu-id="0d357-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d357-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d357-125">Remarks</span></span>  
 <span data-ttu-id="0d357-126">Der Arbeitsspeicher, auf den `ppvData` verweist, ist nur gültig, solange der zugrunde liegende Metadatenbereich geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="0d357-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="0d357-127">Damit diese Methode funktioniert, müssen Sie, wenn Sie die Metadaten einer Datei auf dem Datenträger durch Aufrufen der [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) -Methode in den Arbeitsspeicher zuordnen, das `ofReadOnly`-Flag angeben, und Sie dürfen das `ofWrite` oder `ofCopyMemory`-Flag nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="0d357-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="0d357-128">Die Auswahl des Datei Mapping-Typs für jeden Bereich ist spezifisch für eine bestimmte Implementierung der CLR.</span><span class="sxs-lookup"><span data-stu-id="0d357-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="0d357-129">Er kann nicht vom Benutzer festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0d357-129">It cannot be set by the user.</span></span> <span data-ttu-id="0d357-130">Die aktuelle Implementierung der CLR gibt immer `fmFlat` in `pdwMappingType`zurück. Dies kann sich jedoch in zukünftigen Versionen der CLR oder in zukünftigen Dienst Releases einer bestimmten Version ändern.</span><span class="sxs-lookup"><span data-stu-id="0d357-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="0d357-131">Sie sollten den zurückgegebenen Wert immer in `pdwMappingType`überprüfen, da unterschiedliche Typen verschiedene Layouts und Offsets aufweisen werden.</span><span class="sxs-lookup"><span data-stu-id="0d357-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="0d357-132">Das übergeben von NULL für einen der drei Parameter wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0d357-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="0d357-133">Die Methode gibt `E_INVALIDARG`zurück, und es werden keine Ausgaben aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="0d357-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="0d357-134">Wenn Sie den Mapping-Typ oder die Größe des Bereichs ignorieren, kann dies zu einem ungewöhnlichen Programmabbruch führen.</span><span class="sxs-lookup"><span data-stu-id="0d357-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d357-135">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0d357-135">Requirements</span></span>  
 <span data-ttu-id="0d357-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d357-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d357-137">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0d357-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d357-138">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d357-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d357-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d357-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d357-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d357-140">See also</span></span>

- [<span data-ttu-id="0d357-141">IMetaDataInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d357-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="0d357-142">CorFileMapping-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0d357-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
