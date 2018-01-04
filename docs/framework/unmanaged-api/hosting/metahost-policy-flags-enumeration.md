---
title: METAHOST_POLICY_FLAGS-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: METAHOST_POLICY_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: METAHOST_POLICY_FLAGS
helpviewer_keywords: METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80abed08cc7659d4218dce445be81481bb5a665b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="metahostpolicyflags-enumeration"></a><span data-ttu-id="c1906-102">METAHOST_POLICY_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c1906-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="c1906-103">Stellt Bindungsrichtlinien für die, die für die meisten Laufzeithosts gelten.</span><span class="sxs-lookup"><span data-stu-id="c1906-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="c1906-104">Diese Enumeration wird verwendet, durch die [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="c1906-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1906-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1906-105">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="c1906-106">Member</span><span class="sxs-lookup"><span data-stu-id="c1906-106">Members</span></span>  
  
|<span data-ttu-id="c1906-107">Member</span><span class="sxs-lookup"><span data-stu-id="c1906-107">Member</span></span>|<span data-ttu-id="c1906-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1906-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="c1906-109">Definiert die hohe Kompatibilität-Richtlinie, die nicht common Language Runtime (CLR) betrachtet wird, die in den aktuellen Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c1906-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="c1906-110">Stattdessen, betrachtet er nur die installierten CLRs und die Einstellungen der Komponente, wie die Assemblydatei selbst, die deklarierten erstellt für Version oder die Konfigurationsdatei abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="c1906-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="c1906-111">Das Ergebnis der Version Bind Upgraderichtlinie betrifft, wenn eine genaue Übereinstimmung nicht gefunden wird, basierend auf den Inhalt der HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\Policy\Upgrades.</span><span class="sxs-lookup"><span data-stu-id="c1906-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="c1906-112">Dies hat dieselbe Wirkung wie das [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="c1906-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="c1906-113">Bindungsergebnisse werden zurückgegeben, als ob das Abbild bereitgestellt, um den Aufruf in einen neuen Prozess gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="c1906-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="c1906-114">Derzeit `GetRequestedRuntime` ignoriert den Satz von ladbaren Laufzeiten und mit der Menge der installierten Laufzeiten bindet.</span><span class="sxs-lookup"><span data-stu-id="c1906-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="c1906-115">Dieses Flag ermöglicht es einen Host, um zu bestimmen, welcher Laufzeitversion eine EXE-Datei gebunden wird, wenn er gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c1906-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="c1906-116">Ein Fehlerdialogfeld wird angezeigt, wenn `GetRequestedRuntime` wurde eine Laufzeit gefunden, die mit den Eingabeparametern kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="c1906-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="c1906-117">Beginnend mit der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], diesem Fehlerdialogfeld dauert das Formular eines Dialogfelds Windows-Funktion mit der Frage, ob der Benutzer für das entsprechende Feature aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c1906-117">Beginning with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="c1906-118">`GetRequestedRuntime`verwendet die Prozess-Image (und alle entsprechenden Konfigurationsdatei) als zusätzliche Eingabe, um des Bindungsvorgangs.</span><span class="sxs-lookup"><span data-stu-id="c1906-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="c1906-119">Standardmäßig `GetRequestedRuntime` liegt nicht zurück auf den Prozess-Image-Pfad (in der Regel die EXE-Datei, die zum Starten des Prozesses verwendet wurde) beim Bestimmen der Laufzeit zum Binden an.</span><span class="sxs-lookup"><span data-stu-id="c1906-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="c1906-120">`GetRequestedRuntime`muss überprüfen, ob die entsprechende SKU installiert wird, wenn keine Informationen in der Konfigurationsdatei verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c1906-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="c1906-121">Dadurch können Anwendungen, die keine Konfigurationsdateien ordnungsgemäß auf kleinere SKUs als die standardmäßige Installation von .NET Framework ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="c1906-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="c1906-122">Standardmäßig `GetRequestedRuntime` überprüft nicht, ob die entsprechende SKU installiert ist, es sei denn, das SKU-Attribut in der Konfigurationsdatei angegeben wird `<supportedRuntime />` Element.</span><span class="sxs-lookup"><span data-stu-id="c1906-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="c1906-123">`GetRequestedRuntime`muss überprüfen, ob die entsprechende SKU installiert wird, wenn keine Informationen in der Konfigurationsdatei verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c1906-123">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="c1906-124">Dadurch können Anwendungen, die keine Konfigurationsdateien ordnungsgemäß auf kleinere SKUs als die standardmäßige Installation von .NET Framework ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="c1906-124">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="c1906-125">Standardmäßig `GetRequestedRuntime` überprüft nicht, ob die entsprechende SKU installiert ist, es sei denn, das SKU-Attribut in der Konfigurationsdatei angegeben wird `<supportedRuntime />` Element.</span><span class="sxs-lookup"><span data-stu-id="c1906-125">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="c1906-126">`GetRequestedRuntime`SEM_FAILCRITICALERRORS zu ignorieren (die festgelegt wird, durch Aufrufen der [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) Funktion), und zeigen Sie im Dialogfeld "Fehler".</span><span class="sxs-lookup"><span data-stu-id="c1906-126">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) function), and show the error dialog box.</span></span> <span data-ttu-id="c1906-127">Standardmäßig wird die SEM_FAILCRITICALERRORS das Fehlerdialogfeld unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="c1906-127">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="c1906-128">Es wurde von einem anderen Prozess geerbt, und die automatische Fehler ist möglicherweise nicht erwünscht, in Ihrem Szenario.</span><span class="sxs-lookup"><span data-stu-id="c1906-128">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1906-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1906-129">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1906-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c1906-130">Requirements</span></span>  
 <span data-ttu-id="c1906-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1906-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1906-132">**Header:** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="c1906-132">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="c1906-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c1906-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1906-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1906-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1906-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1906-135">See Also</span></span>  
 [<span data-ttu-id="c1906-136">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="c1906-136">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="c1906-137">GetRequestedRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="c1906-137">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
