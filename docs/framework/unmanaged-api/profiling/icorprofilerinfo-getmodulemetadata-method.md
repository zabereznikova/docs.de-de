---
title: ICorProfilerInfo::GetModuleMetaData-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
ms.openlocfilehash: 6e787de6287dc5b3091d3671d3da2f2154b12e88
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869923"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="55ce8-102">ICorProfilerInfo::GetModuleMetaData-Methode</span><span class="sxs-lookup"><span data-stu-id="55ce8-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>
<span data-ttu-id="55ce8-103">Ruft eine Instanz der Metadatenschnittstelle ab, die dem angegebenen Modul zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="55ce8-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55ce8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55ce8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55ce8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="55ce8-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="55ce8-106">in Die ID des Moduls, dem die Schnittstellen Instanz zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="55ce8-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="55ce8-107">in Ein Wert der [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) -Enumeration, der den Modus für das Öffnen von Manifest-Dateien angibt.</span><span class="sxs-lookup"><span data-stu-id="55ce8-107">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="55ce8-108">Nur die `ofRead`, `ofWrite` und `ofNoTransform` Bits sind gültig.</span><span class="sxs-lookup"><span data-stu-id="55ce8-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="55ce8-109">in Die Verweis-ID (GUID) der Metadatenschnittstelle, deren Instanz abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="55ce8-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="55ce8-110">Eine Liste der Schnittstellen finden Sie unter [Metadatenschnittstellen](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) .</span><span class="sxs-lookup"><span data-stu-id="55ce8-110">See [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="55ce8-111">vorgenommen Ein Zeiger auf die Adresse der Metadatenschnittstellen-Instanz.</span><span class="sxs-lookup"><span data-stu-id="55ce8-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55ce8-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55ce8-112">Remarks</span></span>  
 <span data-ttu-id="55ce8-113">Sie werden möglicherweise aufgefordert, die Metadaten im Lese-/Schreibmodus zu öffnen, dies führt jedoch zu einer langsameren metadatenausführung des Programms, da an den Metadaten vorgenommene Änderungen nicht wie vom Compiler optimiert werden können.</span><span class="sxs-lookup"><span data-stu-id="55ce8-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="55ce8-114">Einige Module (z. b. Ressourcen Module) haben keine Metadaten.</span><span class="sxs-lookup"><span data-stu-id="55ce8-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="55ce8-115">In diesen Fällen wird `GetModuleMetaData` den HRESULT-Wert S_FALSE und einen NULL-Wert in \*`ppOut`zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="55ce8-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in \*`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55ce8-116">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="55ce8-116">Requirements</span></span>  
 <span data-ttu-id="55ce8-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55ce8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55ce8-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55ce8-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="55ce8-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55ce8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55ce8-120">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55ce8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55ce8-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55ce8-121">See also</span></span>

- [<span data-ttu-id="55ce8-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55ce8-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
