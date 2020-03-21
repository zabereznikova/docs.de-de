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
ms.openlocfilehash: 0f5bdf97132c05e765cd6fa423a19bb996105d28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175264"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="38268-102">IMetaDataInfo::GetFileMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="38268-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="38268-103">Ruft den Speicherbereich der zugeordneten Datei und den Zuordnungstyp ab.</span><span class="sxs-lookup"><span data-stu-id="38268-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38268-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="38268-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38268-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="38268-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="38268-106">[out] Ein Zeiger auf den Anfang der zugeordneten Datei.</span><span class="sxs-lookup"><span data-stu-id="38268-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="38268-107">[out] Die Größe des zugeordneten Bereichs.</span><span class="sxs-lookup"><span data-stu-id="38268-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="38268-108">Wenn `pdwMappingType` `fmFlat`dies der Falle ist, ist dies die Größe der Datei.</span><span class="sxs-lookup"><span data-stu-id="38268-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="38268-109">[out] Ein [CorFileMapping-Wert,](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) der den Zuordnungstyp angibt.</span><span class="sxs-lookup"><span data-stu-id="38268-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="38268-110">Die aktuelle Implementierung der Common Language Runtime `fmFlat`(CLR) gibt immer zurück.</span><span class="sxs-lookup"><span data-stu-id="38268-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="38268-111">Andere Werte sind für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="38268-111">Other values are reserved for future use.</span></span> <span data-ttu-id="38268-112">Sie sollten jedoch immer den zurückgegebenen Wert überprüfen, da andere Werte in zukünftigen Versionen oder Dienstversionen aktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="38268-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38268-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="38268-113">Return Value</span></span>  
  
|<span data-ttu-id="38268-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="38268-114">HRESULT</span></span>|<span data-ttu-id="38268-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38268-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="38268-116">Alle Ausgänge sind gefüllt.</span><span class="sxs-lookup"><span data-stu-id="38268-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="38268-117">NULL wurde als Argumentwert übergeben.</span><span class="sxs-lookup"><span data-stu-id="38268-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="38268-118">Die CLR-Implementierung kann keine Informationen über den Speicherbereich bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="38268-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="38268-119">Dies kann aus folgenden Gründen geschehen:</span><span class="sxs-lookup"><span data-stu-id="38268-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="38268-120">- Der Metadatenbereich wurde `ofWrite` `ofCopyMemory` mit dem oder-Flag geöffnet.</span><span class="sxs-lookup"><span data-stu-id="38268-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="38268-121">- Der Metadatenbereich wurde `ofReadOnly` ohne das Flag geöffnet.</span><span class="sxs-lookup"><span data-stu-id="38268-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="38268-122">- Die [IMetaDataDispenser::OpenScopeOnMemory-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) wurde verwendet, um nur den Metadatenteil der Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="38268-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="38268-123">- Die Datei ist keine portable ausführbare Datei (PE).</span><span class="sxs-lookup"><span data-stu-id="38268-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="38268-124">**Hinweis:**  Diese Bedingungen hängen von der CLR-Implementierung ab und werden wahrscheinlich in zukünftigen Versionen der CLR geschwächt.</span><span class="sxs-lookup"><span data-stu-id="38268-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38268-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="38268-125">Remarks</span></span>  
 <span data-ttu-id="38268-126">Der Speicher, auf den verweist, `ppvData` ist nur gültig, solange der zugrunde liegende Metadatenbereich geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="38268-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="38268-127">Damit diese Methode funktioniert, müssen Sie beim Zuordnen der Metadaten einer On-Disk-Datei in den Speicher die [IMetaDataDispenser::OpenScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) angeben, `ofReadOnly` und Sie dürfen das `ofWrite` oder-Flag `ofCopyMemory` nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="38268-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="38268-128">Die Auswahl des Dateizuordnungstyps für jeden Bereich ist spezifisch für eine bestimmte Implementierung der CLR.</span><span class="sxs-lookup"><span data-stu-id="38268-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="38268-129">Sie kann vom Benutzer nicht festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="38268-129">It cannot be set by the user.</span></span> <span data-ttu-id="38268-130">Die aktuelle Implementierung der CLR `pdwMappingType`gibt immer in zurück, `fmFlat` dies kann sich jedoch in zukünftigen Versionen der CLR oder in zukünftigen Service-Releases einer bestimmten Version ändern.</span><span class="sxs-lookup"><span data-stu-id="38268-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="38268-131">Sie sollten den zurückgegebenen `pdwMappingType`Wert immer in überprüfen, da verschiedene Typen unterschiedliche Layouts und Offsets aufweisen.</span><span class="sxs-lookup"><span data-stu-id="38268-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="38268-132">Das Übergeben von NULL für einen der drei Parameter wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="38268-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="38268-133">Die Methode `E_INVALIDARG`gibt zurück, und keine ausgabe wird gefüllt.</span><span class="sxs-lookup"><span data-stu-id="38268-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="38268-134">Das Ignorieren des Zuordnungstyps oder der Größe der Region kann zu einer ungewöhnlichen Programmbeendigung führen.</span><span class="sxs-lookup"><span data-stu-id="38268-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38268-135">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="38268-135">Requirements</span></span>  
 <span data-ttu-id="38268-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38268-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38268-137">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="38268-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38268-138">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="38268-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38268-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38268-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38268-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38268-140">See also</span></span>

- [<span data-ttu-id="38268-141">IMetaDataInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="38268-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="38268-142">CorFileMapping-Enumeration</span><span class="sxs-lookup"><span data-stu-id="38268-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
