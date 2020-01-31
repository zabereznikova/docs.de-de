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
ms.openlocfilehash: e3d167be9a4091ae57a3283424186142e90ca7a1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868550"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a><span data-ttu-id="c53f0-102">ICorProfilerInfo3::GetRuntimeInformation-Methode</span><span class="sxs-lookup"><span data-stu-id="c53f0-102">ICorProfilerInfo3::GetRuntimeInformation Method</span></span>
<span data-ttu-id="c53f0-103">Stellt Versionsinformationen über die Common Language Runtime (CLR) bereit, für die ein Profil erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c53f0-103">Provides version information about the common language runtime (CLR) that is being profiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c53f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c53f0-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c53f0-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c53f0-105">Parameters</span></span>  
 `pClrInstanceId`  
 <span data-ttu-id="c53f0-106">vorgenommen Die repräsentative ID einer laufenden CLR-Instanz in einem Prozess.</span><span class="sxs-lookup"><span data-stu-id="c53f0-106">[out] The representative ID of a running CLR instance in a process.</span></span> <span data-ttu-id="c53f0-107">Dies ist das gleiche wie das `ClrInstanceID`, das vom Ereignis Ablauf Verfolgung für Windows (ETW)-Start Ereignis gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="c53f0-107">This is the same as the `ClrInstanceID` that the event tracing for Windows (ETW) startup event reports.</span></span>  
  
 `pRuntimeType`  
 <span data-ttu-id="c53f0-108">vorgenommen Der Lauf Zeittyp.</span><span class="sxs-lookup"><span data-stu-id="c53f0-108">[out] The runtime type.</span></span> <span data-ttu-id="c53f0-109">Dieser Parameter gibt `COR_PRF_DESKTOP_CLR` für die Desktop Version der CLR zurück, oder `COR_PRF_CORE_CLR` für die in Silverlight verwendete Core-Version der CLR.</span><span class="sxs-lookup"><span data-stu-id="c53f0-109">This parameter returns `COR_PRF_DESKTOP_CLR` for the desktop version of the CLR, or `COR_PRF_CORE_CLR` for the core version of the CLR used in Silverlight.</span></span>  
  
 `pMajorVersion`  
 <span data-ttu-id="c53f0-110">vorgenommen Die Hauptversionsnummer der CLR.</span><span class="sxs-lookup"><span data-stu-id="c53f0-110">[out] The major version number of the CLR.</span></span>  
  
 `pMinorVersion`  
 <span data-ttu-id="c53f0-111">vorgenommen Die neben Versionsnummer der CLR.</span><span class="sxs-lookup"><span data-stu-id="c53f0-111">[out] The minor version number of the CLR.</span></span>  
  
 `pBuildVersion`  
 <span data-ttu-id="c53f0-112">vorgenommen Die Buildversionsnummer der CLR.</span><span class="sxs-lookup"><span data-stu-id="c53f0-112">[out] The build version number of the CLR.</span></span>  
  
 `pQFEVersion`  
 <span data-ttu-id="c53f0-113">vorgenommen Die Versionsnummer der CLR, die einem Software Update zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c53f0-113">[out] The version number of the CLR that is associated with a software update.</span></span>  
  
 `cchVersionString`  
 <span data-ttu-id="c53f0-114">in Die Länge (in Zeichen) des Puffers, auf den `szVersionString` zeigt.</span><span class="sxs-lookup"><span data-stu-id="c53f0-114">[in] The length, in characters, of the buffer that `szVersionString` points to.</span></span>  
  
 `pcchVersionString`  
 <span data-ttu-id="c53f0-115">vorgenommen Die Länge `szVersionString`in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c53f0-115">[out] The length, in characters, of `szVersionString`.</span></span>  
  
 `szVersionString`  
 <span data-ttu-id="c53f0-116">vorgenommen Die CLR-Versions Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c53f0-116">[out] The CLR version string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c53f0-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c53f0-117">Remarks</span></span>  
 <span data-ttu-id="c53f0-118">Sie können für jeden Parameter NULL übergeben.</span><span class="sxs-lookup"><span data-stu-id="c53f0-118">You may pass null for any parameter.</span></span> <span data-ttu-id="c53f0-119">`pcchVersionString` kann jedoch nur dann NULL sein, wenn `szVersionString` ebenfalls NULL ist.</span><span class="sxs-lookup"><span data-stu-id="c53f0-119">However, `pcchVersionString` cannot be null unless `szVersionString` is also null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c53f0-120">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c53f0-120">Requirements</span></span>  
 <span data-ttu-id="c53f0-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c53f0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c53f0-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c53f0-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c53f0-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c53f0-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c53f0-124">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c53f0-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c53f0-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c53f0-125">See also</span></span>

- [<span data-ttu-id="c53f0-126">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c53f0-126">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="c53f0-127">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c53f0-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="c53f0-128">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="c53f0-128">Profiling</span></span>](index.md)
