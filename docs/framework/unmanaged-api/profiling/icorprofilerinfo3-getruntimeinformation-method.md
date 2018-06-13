---
title: ICorProfilerInfo3::GetRuntimeInformation-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 67e1d20f7faf38fa37083f1a5b1cc0c1060b7a32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461567"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="d0965-102">ICorProfilerInfo3::GetRuntimeInformation-Methode</span><span class="sxs-lookup"><span data-stu-id="d0965-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="d0965-103">Bietet Informationen über die common Language Runtime (CLR), die ein Profil erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d0965-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0965-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0965-104">Syntax</span></span>  
  
```  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0965-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d0965-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="d0965-106">[out] Die Mitarbeiter-ID einer laufenden Instanz von CLR in einem Prozess.</span><span class="sxs-lookup"><span data-stu-id="d0965-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="d0965-107">Dies ist identisch mit der `ClrInstanceID` von Event Tracing for Windows (ETW) Startup-Ereignis gemeldet.</span><span class="sxs-lookup"><span data-stu-id="d0965-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="d0965-108">[out] Die Common Language Runtime-Typ.</span><span class="sxs-lookup"><span data-stu-id="d0965-108">[out] The runtime type.</span></span> <span data-ttu-id="d0965-109">Dieser Parameter gibt `COR_PRF_DESKTOP_CLR` für die Desktopversion von CLR oder `COR_PRF_CORE_CLR` für die Core-Version der CLR, die in Silverlight verwendet.</span><span class="sxs-lookup"><span data-stu-id="d0965-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="d0965-110">[out] Die Hauptversionsnummer der CLR.</span><span class="sxs-lookup"><span data-stu-id="d0965-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="d0965-111">[out] Die Nebenversionsnummer der CLR.</span><span class="sxs-lookup"><span data-stu-id="d0965-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="d0965-112">[out] Die Buildversionsnummer der CLR.</span><span class="sxs-lookup"><span data-stu-id="d0965-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="d0965-113">[out] Die Versionsnummer der CLR, die einem Softwareupdate zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d0965-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="d0965-114">[in] Die Länge des Puffers in Zeichen, die `szVersionString` verweist auf.</span><span class="sxs-lookup"><span data-stu-id="d0965-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="d0965-115">[out] Die Länge in Zeichen, d. h. der `szVersionString`.</span><span class="sxs-lookup"><span data-stu-id="d0965-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="d0965-116">[out] Die CLR-Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d0965-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0965-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d0965-117">Remarks</span></span>  
 <span data-ttu-id="d0965-118">Sie können null für die einzelnen Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="d0965-118">You may pass null for any parameter.</span></span> <span data-ttu-id="d0965-119">Allerdings `pcchVersionString` darf nicht null sein, wenn `szVersionString` ist ebenfalls null.</span><span class="sxs-lookup"><span data-stu-id="d0965-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0965-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0965-120">Requirements</span></span>  
 <span data-ttu-id="d0965-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0965-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0965-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d0965-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d0965-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0965-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0965-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0965-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0965-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0965-125">See Also</span></span>  
 [<span data-ttu-id="d0965-126">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0965-126">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="d0965-127">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d0965-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="d0965-128">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="d0965-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
