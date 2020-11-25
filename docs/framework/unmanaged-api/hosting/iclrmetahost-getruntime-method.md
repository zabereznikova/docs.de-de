---
title: ICLRMetaHost::GetRuntime-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
ms.openlocfilehash: 093fa64a7d51e0c2fdc304d2bb4f1c9f7b03e2ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730408"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="77b2b-102">ICLRMetaHost::GetRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="77b2b-102">ICLRMetaHost::GetRuntime Method</span></span>

<span data-ttu-id="77b2b-103">Ruft die [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle ab, die einer bestimmten Version des Common Language Runtime (CLR) entspricht.</span><span class="sxs-lookup"><span data-stu-id="77b2b-103">Gets the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="77b2b-104">Diese Methode ersetzt die [CorBindToRuntimeEx](corbindtoruntimeex-function.md) -Funktion, die mit dem [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) -Flag verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="77b2b-104">This method supersedes the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77b2b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="77b2b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77b2b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="77b2b-106">Parameters</span></span>  

 `pwzVersion`  
 <span data-ttu-id="77b2b-107">in Die in den Metadaten gespeicherte .NET Framework Kompilierungs Version im Format "v *A*. *B*[.*X*] ".</span><span class="sxs-lookup"><span data-stu-id="77b2b-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v *A*.*B*[.*X*]".</span></span> <span data-ttu-id="77b2b-108">*A*, *B* und *X* sind Dezimalzahlen, die der Hauptversion, der neben Version und der Buildnummer entsprechen.</span><span class="sxs-lookup"><span data-stu-id="77b2b-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77b2b-109">Dieser Parameter muss dem Verzeichnisnamen für die .NET Framework Version entsprechen, wie er unter "c:\WINDOWS\Microsoft.NET\Framework" oder "c:\WINDOWS\Microsoft.NET\Framework64." angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="77b2b-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="77b2b-110">Beispiel Werte sind "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" und "v 4.0". *X*", wobei *x* von der installierten Buildnummer abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="77b2b-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="77b2b-111">Das Präfix "v" ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="77b2b-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="77b2b-112">in Der Bezeichner für die gewünschte Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="77b2b-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="77b2b-113">Derzeit ist der einzige gültige Wert für diesen Parameter IID_ICLRRuntimeInfo.</span><span class="sxs-lookup"><span data-stu-id="77b2b-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="77b2b-114">vorgenommen Ein Zeiger auf die [iclrruntimeingefo](iclrruntimeinfo-interface.md) -Schnittstelle, die der angeforderten Laufzeit entspricht.</span><span class="sxs-lookup"><span data-stu-id="77b2b-114">[out] A pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77b2b-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="77b2b-115">Return Value</span></span>  

 <span data-ttu-id="77b2b-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="77b2b-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="77b2b-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77b2b-117">HRESULT</span></span>|<span data-ttu-id="77b2b-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="77b2b-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="77b2b-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="77b2b-119">S_OK</span></span>|<span data-ttu-id="77b2b-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="77b2b-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="77b2b-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="77b2b-121">E_POINTER</span></span>|<span data-ttu-id="77b2b-122">`pwzVersion` oder `ppRuntime` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="77b2b-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77b2b-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77b2b-123">Remarks</span></span>  

 <span data-ttu-id="77b2b-124">Diese Methode interagiert konsistent mit Legacy Schnittstellen, wie z. b. der [ICorRuntimeHost](icorruntimehost-interface.md) -Schnittstelle, und Legacy Funktionen wie den veralteten `CorBindTo*` Funktionen (siehe [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md) in der .NET Framework 2,0-Hosting-API).</span><span class="sxs-lookup"><span data-stu-id="77b2b-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="77b2b-125">Das heißt, Laufzeiten, die mit der Legacy-API geladen werden, sind für die neue API sichtbar, und Laufzeiten, die mit der neuen API geladen werden, sind für die Legacy-API sichtbar.</span><span class="sxs-lookup"><span data-stu-id="77b2b-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77b2b-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="77b2b-126">Requirements</span></span>  

 <span data-ttu-id="77b2b-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77b2b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77b2b-128">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="77b2b-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="77b2b-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="77b2b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77b2b-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77b2b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77b2b-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77b2b-131">See also</span></span>

- [<span data-ttu-id="77b2b-132">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77b2b-132">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="77b2b-133">Veraltete CLR-Hostingschnittstellen und Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="77b2b-133">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)
- [<span data-ttu-id="77b2b-134">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="77b2b-134">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="77b2b-135">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="77b2b-135">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="77b2b-136">Hosting</span><span class="sxs-lookup"><span data-stu-id="77b2b-136">Hosting</span></span>](index.md)
