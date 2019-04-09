---
title: METAHOST_POLICY_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31ff93b6935c2237a5935c4b40cc30b4129edcd0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230602"
---
# <a name="metahostpolicyflags-enumeration"></a><span data-ttu-id="8fb68-102">METAHOST_POLICY_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8fb68-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="8fb68-103">Enthält Bindungsrichtlinien für die, die für die meisten Laufzeithosts gelten.</span><span class="sxs-lookup"><span data-stu-id="8fb68-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="8fb68-104">Diese Enumeration wird verwendet, durch die [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="8fb68-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fb68-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8fb68-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="8fb68-106">Member</span><span class="sxs-lookup"><span data-stu-id="8fb68-106">Members</span></span>  
  
|<span data-ttu-id="8fb68-107">Member</span><span class="sxs-lookup"><span data-stu-id="8fb68-107">Member</span></span>|<span data-ttu-id="8fb68-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fb68-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="8fb68-109">Definiert die hohe Kompatibilität-Richtlinie, die keine common Language Runtime (CLR) halten, die in den aktuellen Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="8fb68-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="8fb68-110">Stattdessen betrachtet sie als nur die installierten CLRs und die Einstellungen der Komponente, wie von der Assemblydatei selbst, die deklarierten integriert-mit-Version oder die Konfigurationsdatei abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="8fb68-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="8fb68-111">Das Ergebnis der Version Bind Upgraderichtlinie gilt, wenn eine genaue Übereinstimmung basierend auf den Inhalt der HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft nicht gefunden wird,\\. NETFramework\Policy\Upgrades.</span><span class="sxs-lookup"><span data-stu-id="8fb68-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="8fb68-112">Dies hat dieselbe Wirkung wie das [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="8fb68-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="8fb68-113">Bindungsergebnisse werden zurückgegeben, als ob das Abbild bereitgestellt, um den Aufruf in einen neuen Prozess gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="8fb68-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="8fb68-114">Derzeit `GetRequestedRuntime` ignoriert den Satz von ladbare Laufzeiten und für die Festlegung installierter Runtimes bindet.</span><span class="sxs-lookup"><span data-stu-id="8fb68-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="8fb68-115">Dieses Flag ermöglicht, einen Host aus, um zu bestimmen, welche Laufzeit eine EXE-Datei gebunden wird, wenn er gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="8fb68-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="8fb68-116">Ein Fehlerdialogfeld wird angezeigt, wenn `GetRequestedRuntime` kann eine Runtime ermitteln, die mit den Eingabeparametern kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="8fb68-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="8fb68-117">Beginnend mit der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], das Dialogfeld "Fehler" dauert des Formulars eines Dialogfelds Windows-Funktion mit der Frage, ob der Benutzer das entsprechende Feature aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="8fb68-117">Beginning with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime` <span data-ttu-id="8fb68-118">wird das Bild (und alle entsprechenden Konfigurationsdatei) als zusätzliche Eingabe an den Bindungsprozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="8fb68-118">uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="8fb68-119">In der Standardeinstellung `GetRequestedRuntime` kein Fallback auf den Prozess-Image-Pfad (in der Regel die EXE-Datei, die zum Starten des Prozesses verwendet wurde) beim Bestimmen der Laufzeit zum Binden an.</span><span class="sxs-lookup"><span data-stu-id="8fb68-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` <span data-ttu-id="8fb68-120">müssen überprüfen, ob die entsprechende SKU installiert wird, wenn keine Informationen verfügbar, in der Konfigurationsdatei sind.</span><span class="sxs-lookup"><span data-stu-id="8fb68-120">must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="8fb68-121">Dadurch können Anwendungen, die keine Konfigurationsdateien, um auf kleineren SKUs als die standardmäßige Installation von .NET Framework ordnungsgemäß abgebrochen haben.</span><span class="sxs-lookup"><span data-stu-id="8fb68-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="8fb68-122">In der Standardeinstellung `GetRequestedRuntime` überprüft nicht, ob die entsprechende SKU installiert ist, es sei denn, das SKU-Attribut in der Konfigurationsdatei angegeben ist `<supportedRuntime />` Element.</span><span class="sxs-lookup"><span data-stu-id="8fb68-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` <span data-ttu-id="8fb68-123">müssen überprüfen, ob die entsprechende SKU installiert wird, wenn keine Informationen verfügbar, in der Konfigurationsdatei sind.</span><span class="sxs-lookup"><span data-stu-id="8fb68-123">must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="8fb68-124">Dadurch können Anwendungen, die keine Konfigurationsdateien, um auf kleineren SKUs als die standardmäßige Installation von .NET Framework ordnungsgemäß abgebrochen haben.</span><span class="sxs-lookup"><span data-stu-id="8fb68-124">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="8fb68-125">In der Standardeinstellung `GetRequestedRuntime` überprüft nicht, ob die entsprechende SKU installiert ist, es sei denn, das SKU-Attribut in der Konfigurationsdatei angegeben ist `<supportedRuntime />` Element.</span><span class="sxs-lookup"><span data-stu-id="8fb68-125">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime` <span data-ttu-id="8fb68-126">SEM_FAILCRITICALERRORS ignorieren soll (das wird festgelegt, durch den Aufruf der [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) Funktion), und zeigen Sie im Dialogfeld "Fehler".</span><span class="sxs-lookup"><span data-stu-id="8fb68-126">should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) function), and show the error dialog box.</span></span> <span data-ttu-id="8fb68-127">Standardmäßig unterdrückt SEM_FAILCRITICALERRORS das Fehlerdialogfeld.</span><span class="sxs-lookup"><span data-stu-id="8fb68-127">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="8fb68-128">Es wurde von einem anderen Prozess geerbt, und der automatische Fehler ist möglicherweise in Ihrem Szenario nicht erwünscht.</span><span class="sxs-lookup"><span data-stu-id="8fb68-128">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fb68-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8fb68-129">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fb68-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8fb68-130">Requirements</span></span>  
 <span data-ttu-id="8fb68-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fb68-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fb68-132">**Header:** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="8fb68-132">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="8fb68-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8fb68-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8fb68-134">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8fb68-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8fb68-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fb68-135">See also</span></span>

- [<span data-ttu-id="8fb68-136">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="8fb68-136">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="8fb68-137">GetRequestedRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="8fb68-137">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
