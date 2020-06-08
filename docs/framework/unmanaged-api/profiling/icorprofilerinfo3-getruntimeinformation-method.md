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
ms.openlocfilehash: b8e503af11fa1d02aac2ec83edde0ffbd562d8e5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496398"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="5bf45-102">ICorProfilerInfo3::GetRuntimeInformation-Methode</span><span class="sxs-lookup"><span data-stu-id="5bf45-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="5bf45-103">Stellt Versionsinformationen über die Common Language Runtime (CLR) bereit, für die ein Profil erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5bf45-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bf45-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5bf45-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="5bf45-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5bf45-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="5bf45-106">vorgenommen Die repräsentative ID einer laufenden CLR-Instanz in einem Prozess.</span><span class="sxs-lookup"><span data-stu-id="5bf45-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="5bf45-107">Dies entspricht dem `ClrInstanceID` , das vom Ereignis Ablauf Verfolgungs für Windows (ETW)-Start Ereignis gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="5bf45-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="5bf45-108">vorgenommen Der Lauf Zeittyp.</span><span class="sxs-lookup"><span data-stu-id="5bf45-108">[out] The runtime type.</span></span> <span data-ttu-id="5bf45-109">Dieser Parameter gibt `COR_PRF_DESKTOP_CLR` für die Desktop Version der CLR zurück, oder `COR_PRF_CORE_CLR` für die in Silverlight verwendete Core-Version der CLR.</span><span class="sxs-lookup"><span data-stu-id="5bf45-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="5bf45-110">vorgenommen Die Hauptversionsnummer der CLR.</span><span class="sxs-lookup"><span data-stu-id="5bf45-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="5bf45-111">vorgenommen Die neben Versionsnummer der CLR.</span><span class="sxs-lookup"><span data-stu-id="5bf45-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="5bf45-112">vorgenommen Die Buildversionsnummer der CLR.</span><span class="sxs-lookup"><span data-stu-id="5bf45-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="5bf45-113">vorgenommen Die Versionsnummer der CLR, die einem Software Update zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5bf45-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="5bf45-114">in Die Länge (in Zeichen) des Puffers, `szVersionString` auf den verweist.</span><span class="sxs-lookup"><span data-stu-id="5bf45-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="5bf45-115">vorgenommen Die Länge von in Zeichen `szVersionString` .</span><span class="sxs-lookup"><span data-stu-id="5bf45-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="5bf45-116">vorgenommen Die CLR-Versions Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5bf45-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bf45-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5bf45-117">Remarks</span></span>  
 <span data-ttu-id="5bf45-118">Sie können für jeden Parameter NULL übergeben.</span><span class="sxs-lookup"><span data-stu-id="5bf45-118">You may pass null for any parameter.</span></span> <span data-ttu-id="5bf45-119">Kann jedoch `pcchVersionString` nicht NULL sein, es sei denn, `szVersionString` ist ebenfalls NULL.</span><span class="sxs-lookup"><span data-stu-id="5bf45-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bf45-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5bf45-120">Requirements</span></span>  
 <span data-ttu-id="5bf45-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bf45-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bf45-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5bf45-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5bf45-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bf45-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bf45-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bf45-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf45-125">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="5bf45-125">See also</span></span>

- [<span data-ttu-id="5bf45-126">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5bf45-126">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="5bf45-127">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5bf45-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="5bf45-128">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="5bf45-128">Profiling</span></span>](index.md)
