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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3667ac5a19664507b767ee6c5421a5e93f6cdfe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433255"
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="c0e86-102">CorBindToCurrentRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="c0e86-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="c0e86-103">Lädt die Common Language Runtime (CLR) in einen Prozess, indem in einer XML-Datei gespeicherte Versionsinformationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0e86-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="c0e86-104">Das Format der XML-Datei ist der standard-Anwendungskonfigurationsdatei nachgebildet.</span><span class="sxs-lookup"><span data-stu-id="c0e86-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="c0e86-105">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="c0e86-105">For more information about configuration files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="c0e86-106">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="c0e86-106">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="c0e86-107">Finden Sie unter [Laden der Common Language Runtime in einen Prozess](http://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).</span><span class="sxs-lookup"><span data-stu-id="c0e86-107">See [Loading the Common Language Runtime into a Process](http://msdn.microsoft.com/library/1e2d6dc1-6aab-43e2-bbc0-aae40756d24f).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0e86-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0e86-108">Syntax</span></span>  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0e86-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0e86-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="c0e86-110">[in] Der Name von einer Anwendungskonfigurationsdatei, die angibt, die Version der CLR geladen.</span><span class="sxs-lookup"><span data-stu-id="c0e86-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="c0e86-111">Wenn der Dateiname nicht vollständig qualifiziert ist, wird davon ausgegangen werden im gleichen Verzeichnis wie die ausführbare Datei, die den Aufruf.</span><span class="sxs-lookup"><span data-stu-id="c0e86-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="c0e86-112">Die Version der Laufzeit geladen werden, wird durch das Versionsattribut in beschrieben die [ \<RequiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) Element der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c0e86-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="c0e86-113">Wenn keine Version angegeben ist, oder wenn die `<requiredRuntime>` Element kann nicht gefunden werden, die neueste Version der CLR, die auf dem Computer installiert ist, wird geladen.</span><span class="sxs-lookup"><span data-stu-id="c0e86-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="c0e86-114">[in] Die `CLSID` der Co-Klasse, die entweder implementiert die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) oder [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c0e86-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="c0e86-115">Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="c0e86-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="c0e86-116">[in] Die `IID` der angeforderten Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c0e86-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="c0e86-117">Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="c0e86-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="c0e86-118">[out] Der zurückgegebene Schnittstellenzeiger.</span><span class="sxs-lookup"><span data-stu-id="c0e86-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0e86-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0e86-119">Requirements</span></span>  
 <span data-ttu-id="c0e86-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0e86-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0e86-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c0e86-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0e86-122">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="c0e86-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0e86-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0e86-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0e86-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0e86-124">See Also</span></span>  
 [<span data-ttu-id="c0e86-125">CorBindToRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="c0e86-125">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="c0e86-126">CorBindToRuntimeByCfg-Funktion</span><span class="sxs-lookup"><span data-stu-id="c0e86-126">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="c0e86-127">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="c0e86-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="c0e86-128">CorBindToRuntimeHost-Funktion</span><span class="sxs-lookup"><span data-stu-id="c0e86-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="c0e86-129">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0e86-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="c0e86-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="c0e86-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
