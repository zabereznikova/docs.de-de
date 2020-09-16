---
title: CorBindToCurrentRuntime-Funktion
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
ms.openlocfilehash: 9c5d83b5f2ffb06c9fb14f715a3ea7ff12319086
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547829"
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="331c3-102">CorBindToCurrentRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="331c3-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="331c3-103">Lädt die Common Language Runtime (CLR) in einen Prozess, indem in einer XML-Datei gespeicherte Versionsinformationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="331c3-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="331c3-104">Das Format der XML-Datei wird nach der Standard Anwendungs Konfigurationsdatei modelliert.</span><span class="sxs-lookup"><span data-stu-id="331c3-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="331c3-105">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="331c3-105">For more information about configuration files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="331c3-106">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="331c3-106">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="331c3-107">Weitere Informationen finden Sie [unter Laden der Common Language Runtime in einen Prozess](/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="331c3-107">See [Loading the Common Language Runtime into a Process](/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="331c3-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="331c3-108">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="331c3-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="331c3-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="331c3-110">in Der Name einer Anwendungs Konfigurationsdatei, die die Version der zu ladenden CLR angibt.</span><span class="sxs-lookup"><span data-stu-id="331c3-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="331c3-111">Wenn der Dateiname nicht voll qualifiziert ist, wird davon ausgegangen, dass er sich im gleichen Verzeichnis befindet wie die ausführbare Datei, die den-Vorgang ausführt.</span><span class="sxs-lookup"><span data-stu-id="331c3-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="331c3-112">Die Version der zu ladenden Laufzeit wird durch das Versions Attribut im- [\<requiredRuntime>](../../configure-apps/file-schema/startup/requiredruntime-element.md) Element der Konfigurationsdatei beschrieben.</span><span class="sxs-lookup"><span data-stu-id="331c3-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="331c3-113">Wenn keine Version angegeben ist, oder wenn das `<requiredRuntime>` Element nicht gefunden werden kann, wird die aktuelle Version der CLR geladen, die auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="331c3-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="331c3-114">in Der `CLSID` der Co-Klasse, die entweder die [ICorRuntimeHost](icorruntimehost-interface.md) -oder die [ICLRRuntimeHost](iclrruntimehost-interface.md) -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="331c3-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="331c3-115">Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="331c3-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="331c3-116">[in] Die `IID` der angeforderten Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="331c3-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="331c3-117">Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="331c3-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="331c3-118">vorgenommen Der zurückgegebene Schnittstellen Zeiger.</span><span class="sxs-lookup"><span data-stu-id="331c3-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="331c3-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="331c3-119">Requirements</span></span>  
 <span data-ttu-id="331c3-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="331c3-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="331c3-121">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="331c3-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="331c3-122">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="331c3-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="331c3-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="331c3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="331c3-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="331c3-124">See also</span></span>

- [<span data-ttu-id="331c3-125">CorBindToRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="331c3-125">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="331c3-126">CorBindToRuntimeByCfg-Funktion</span><span class="sxs-lookup"><span data-stu-id="331c3-126">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="331c3-127">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="331c3-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="331c3-128">CorBindToRuntimeHost-Funktion</span><span class="sxs-lookup"><span data-stu-id="331c3-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="331c3-129">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="331c3-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="331c3-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="331c3-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
