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
ms.openlocfilehash: d0acb322fa3348f0bb2d819529a370110580343c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178060"
---
# <a name="corbindtocurrentruntime-function"></a><span data-ttu-id="9147f-102">CorBindToCurrentRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="9147f-102">CorBindToCurrentRuntime Function</span></span>
<span data-ttu-id="9147f-103">Lädt die Common Language Runtime (CLR) in einen Prozess, indem in einer XML-Datei gespeicherte Versionsinformationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9147f-103">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span> <span data-ttu-id="9147f-104">Das Format der XML-Datei ist der standard-Anwendungskonfigurationsdatei nachgebildet.</span><span class="sxs-lookup"><span data-stu-id="9147f-104">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="9147f-105">Weitere Informationen zu Konfigurationsdateien finden Sie unter [Konfigurationsdateienschema](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="9147f-105">For more information about configuration files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="9147f-106">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="9147f-106">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="9147f-107">Finden Sie unter [laden die Common Language Runtime in einen Prozess](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9147f-107">See [Loading the Common Language Runtime into a Process](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9147f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9147f-108">Syntax</span></span>  
  
```  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9147f-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="9147f-109">Parameters</span></span>  
 `pwszFileName`  
 <span data-ttu-id="9147f-110">[in] Der Name der Konfigurationsdatei einer Anwendung, die angibt, die Version der CLR geladen.</span><span class="sxs-lookup"><span data-stu-id="9147f-110">[in] The name of an application configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="9147f-111">Wenn der Dateiname nicht vollqualifiziert ist, wird davon ausgegangen, im gleichen Verzeichnis wie die ausführbare Datei, die den Aufruf sein.</span><span class="sxs-lookup"><span data-stu-id="9147f-111">If the file name is not fully qualified, it is assumed to be in the same directory as the executable making the call.</span></span>  
  
 <span data-ttu-id="9147f-112">Die Version der Laufzeit zu ladenden wird beschrieben, durch das Versionsattribut in der [ \<RequiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) Element der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="9147f-112">The version of the runtime to be loaded is described by the version attribute in the [\<requiredRuntime>](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element of the configuration file.</span></span>  
  
 <span data-ttu-id="9147f-113">Wenn keine Version angegeben wird, oder wenn die `<requiredRuntime>` Element kann nicht gefunden werden, die neueste Version der CLR, die auf dem Computer installiert ist, wird geladen.</span><span class="sxs-lookup"><span data-stu-id="9147f-113">If no version is specified, or if the `<requiredRuntime>` element cannot be found, the latest version of the CLR that is installed on the machine is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="9147f-114">[in] Die `CLSID` der Co-Klasse, die entweder implementiert die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) oder [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9147f-114">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="9147f-115">Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="9147f-115">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="9147f-116">[in] Die `IID` der angeforderten Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9147f-116">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="9147f-117">Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="9147f-117">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="9147f-118">[out] Der zurückgegebene Schnittstellenzeiger.</span><span class="sxs-lookup"><span data-stu-id="9147f-118">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9147f-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9147f-119">Requirements</span></span>  
 <span data-ttu-id="9147f-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9147f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9147f-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9147f-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9147f-122">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9147f-122">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9147f-123">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="9147f-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9147f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9147f-124">See also</span></span>

- [<span data-ttu-id="9147f-125">CorBindToRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="9147f-125">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="9147f-126">CorBindToRuntimeByCfg-Funktion</span><span class="sxs-lookup"><span data-stu-id="9147f-126">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="9147f-127">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="9147f-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="9147f-128">CorBindToRuntimeHost-Funktion</span><span class="sxs-lookup"><span data-stu-id="9147f-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="9147f-129">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9147f-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="9147f-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="9147f-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
