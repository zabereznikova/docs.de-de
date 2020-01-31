---
title: ICLRDebuggingLibraryProvider::ProvideLibrary-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
ms.openlocfilehash: d0c283232ff8eca1af9f3ff4448fb7f4c81d554f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789037"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="df6b4-102">ICLRDebuggingLibraryProvider::ProvideLibrary-Methode</span><span class="sxs-lookup"><span data-stu-id="df6b4-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>

<span data-ttu-id="df6b4-103">Ruft eine Bibliotheks Anbieter-Rückruf Schnittstelle ab, die es ermöglicht, Common Language Runtime (CLR) versionsspezifische Debugbibliotheken zu finden und bei Bedarf geladen zu werden.</span><span class="sxs-lookup"><span data-stu-id="df6b4-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>

## <a name="syntax"></a><span data-ttu-id="df6b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df6b4-104">Syntax</span></span>

```cpp
HRESULT ProvideLibrary(
     [in] const WCHAR* pwszFileName,
     [in] DWORD dwTimestamp,
     [in] DWORD dwSizeOfImage,
     [out] HMODULE* hModule);
```

## <a name="parameters"></a><span data-ttu-id="df6b4-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="df6b4-105">Parameters</span></span>

`pwszFilename` \
<span data-ttu-id="df6b4-106">in Der Name des Moduls, das angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="df6b4-106">[in] The name of the module being requested.</span></span>

`dwTimestamp` \
<span data-ttu-id="df6b4-107">in Der Datums-/Uhrzeitstempel, der im COFF-Dateiheader von PE-Dateien gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="df6b4-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>

`pLibraryProvider` \
<span data-ttu-id="df6b4-108">in Das `SizeOfImage` Feld, das in der optionalen COFF-Datei Kopfzeile von PE-Dateien gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="df6b4-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>

`hModule` \
<span data-ttu-id="df6b4-109">vorgenommen Das Handle für das angeforderte Modul.</span><span class="sxs-lookup"><span data-stu-id="df6b4-109">[out] The handle to the requested module.</span></span>

## <a name="return-value"></a><span data-ttu-id="df6b4-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="df6b4-110">Return Value</span></span>

<span data-ttu-id="df6b4-111">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="df6b4-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>

|<span data-ttu-id="df6b4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df6b4-112">HRESULT</span></span>|<span data-ttu-id="df6b4-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df6b4-113">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="df6b4-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="df6b4-114">S_OK</span></span>|<span data-ttu-id="df6b4-115">Die Methode wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="df6b4-115">The method completed successfully.</span></span>|

## <a name="exceptions"></a><span data-ttu-id="df6b4-116">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="df6b4-116">Exceptions</span></span>

## <a name="remarks"></a><span data-ttu-id="df6b4-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df6b4-117">Remarks</span></span>

<span data-ttu-id="df6b4-118">mit `ProvideLibrary` kann der Debugger Module bereitstellen, die zum Debuggen bestimmter CLR-Dateien wie mscordbi. dll und mscordacwert. dll erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="df6b4-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="df6b4-119">Die Modul Handles müssen gültig bleiben, bis ein Aufruf der [ICLRDebugging:: CanUnloadNow](iclrdebugging-canunloadnow-method.md) -Methode anzeigt, dass Sie freigegeben werden können. an diesem Punkt ist es die Aufgabe des Aufrufers, die Handles freizugeben.</span><span class="sxs-lookup"><span data-stu-id="df6b4-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>

<span data-ttu-id="df6b4-120">Der Debugger kann beliebige verfügbare Mittel verwenden, um das Debug-Modul zu suchen oder zu beschaffen.</span><span class="sxs-lookup"><span data-stu-id="df6b4-120">The debugger may use any available means to locate or procure the debugging module.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df6b4-121">Diese Funktion ermöglicht es dem API-Aufrufer, Module bereitzustellen, die ausführbare und möglicherweise bösartigen Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="df6b4-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="df6b4-122">Als Sicherheitsmaßnahme sollte der Aufrufer nicht `ProvideLibrary` verwenden, um Code zu verteilen, der nicht für die Selbstausführung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="df6b4-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>
>
> <span data-ttu-id="df6b4-123">Wenn in einer bereits veröffentlichten Bibliothek, wie z. b. mscordbi. dll oder mscordacwks. dll, ein schwerwiegendes Sicherheitsproblem entdeckt wird, kann das Shim gepatcht werden, um die ungültigen Versionen der Dateien zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="df6b4-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="df6b4-124">Der Shim kann dann Anforderungen für die gepatchten Versionen der Dateien ausgeben und die ungültigen Versionen ablehnen, wenn Sie als Antwort auf eine Anforderung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="df6b4-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="df6b4-125">Dies kann nur auftreten, wenn der Benutzer auf eine neue Version des Shims gepatcht hat.</span><span class="sxs-lookup"><span data-stu-id="df6b4-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="df6b4-126">Nicht gepatchte Versionen bleiben anfällig.</span><span class="sxs-lookup"><span data-stu-id="df6b4-126">Unpatched versions will remain vulnerable.</span></span>

## <a name="requirements"></a><span data-ttu-id="df6b4-127">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="df6b4-127">Requirements</span></span>

<span data-ttu-id="df6b4-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df6b4-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="df6b4-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df6b4-129">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="df6b4-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df6b4-130">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="df6b4-131">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df6b4-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="df6b4-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df6b4-132">See also</span></span>

- [<span data-ttu-id="df6b4-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="df6b4-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="df6b4-134">Debuggen</span><span class="sxs-lookup"><span data-stu-id="df6b4-134">Debugging</span></span>](index.md)
