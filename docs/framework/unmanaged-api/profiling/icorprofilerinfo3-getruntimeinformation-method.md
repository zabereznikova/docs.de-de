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
ms.openlocfilehash: a13e3e525c7f019e7dc49111b88ac374345830af
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164930"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="d67ff-102">ICorProfilerInfo3::GetRuntimeInformation-Methode</span><span class="sxs-lookup"><span data-stu-id="d67ff-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="d67ff-103">Bietet Informationen über die common Language Runtime (CLR), die ein Profil erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d67ff-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d67ff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d67ff-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d67ff-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d67ff-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="d67ff-106">[out] Die Mitarbeiter-ID einer laufenden Instanz von CLR in einem Prozess.</span><span class="sxs-lookup"><span data-stu-id="d67ff-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="d67ff-107">Dies ist identisch mit der `ClrInstanceID` , dass die ereignisablaufverfolgung für Windows (ETW)-Startup-Ereignis meldet.</span><span class="sxs-lookup"><span data-stu-id="d67ff-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="d67ff-108">[out] Der Common Language Runtime-Typ.</span><span class="sxs-lookup"><span data-stu-id="d67ff-108">[out] The runtime type.</span></span> <span data-ttu-id="d67ff-109">Dieser Parameter gibt `COR_PRF_DESKTOP_CLR` für die desktop-Version der CLR oder `COR_PRF_CORE_CLR` für die Core-Version der CLR in Silverlight verwendet.</span><span class="sxs-lookup"><span data-stu-id="d67ff-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="d67ff-110">[out] Die Hauptversionsnummer der CLR.</span><span class="sxs-lookup"><span data-stu-id="d67ff-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="d67ff-111">[out] Die Nebenversionsnummer der CLR.</span><span class="sxs-lookup"><span data-stu-id="d67ff-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="d67ff-112">[out] Die Buildversionsnummer der CLR.</span><span class="sxs-lookup"><span data-stu-id="d67ff-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="d67ff-113">[out] Die Versionsnummer der CLR, die einem Softwareupdate zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d67ff-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="d67ff-114">[in] Die Länge des Puffers in Zeichen, die `szVersionString` verweist auf.</span><span class="sxs-lookup"><span data-stu-id="d67ff-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="d67ff-115">[out] Die Länge in Zeichen des `szVersionString`.</span><span class="sxs-lookup"><span data-stu-id="d67ff-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="d67ff-116">[out] Die CLR-Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d67ff-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d67ff-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d67ff-117">Remarks</span></span>  
 <span data-ttu-id="d67ff-118">Sie können für jeden Parameter null übergeben.</span><span class="sxs-lookup"><span data-stu-id="d67ff-118">You may pass null for any parameter.</span></span> <span data-ttu-id="d67ff-119">Allerdings `pcchVersionString` darf nicht null sein, wenn `szVersionString` ist ebenfalls null.</span><span class="sxs-lookup"><span data-stu-id="d67ff-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d67ff-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d67ff-120">Requirements</span></span>  
 <span data-ttu-id="d67ff-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d67ff-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d67ff-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d67ff-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d67ff-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d67ff-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d67ff-124">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="d67ff-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d67ff-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d67ff-125">See also</span></span>

- [<span data-ttu-id="d67ff-126">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d67ff-126">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="d67ff-127">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d67ff-127">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="d67ff-128">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="d67ff-128">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
