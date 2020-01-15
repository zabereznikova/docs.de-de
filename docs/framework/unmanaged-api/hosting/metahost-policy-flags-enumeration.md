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
ms.openlocfilehash: 048286fb9e1af34cd964fb5b21892778f9575d2c
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938193"
---
# <a name="metahost_policy_flags-enumeration"></a><span data-ttu-id="139a2-102">METAHOST_POLICY_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="139a2-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="139a2-103">Stellt Bindungs Richtlinien bereit, die den meisten Lauf Zeit Hosts gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="139a2-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="139a2-104">Diese Enumeration wird von der [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="139a2-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="139a2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="139a2-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="139a2-106">Member</span><span class="sxs-lookup"><span data-stu-id="139a2-106">Members</span></span>  
  
|<span data-ttu-id="139a2-107">Member</span><span class="sxs-lookup"><span data-stu-id="139a2-107">Member</span></span>|<span data-ttu-id="139a2-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="139a2-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="139a2-109">Definiert die Richtlinie für hohe Kompatibilität, bei der keine Common Language Runtime (CLR) berücksichtigt werden, die in den aktuellen Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="139a2-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="139a2-110">Stattdessen werden nur die installierten clrs und die Einstellungen der Komponente, die von der Assemblydatei selbst abgeleitet sind, die deklarierte integrierte Version oder die Konfigurationsdatei berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="139a2-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="139a2-111">Wendet die Upgraderichtlinie auf das Versions Bindungs Ergebnis an, wenn keine genaue Entsprechung gefunden wurde, basierend auf dem Inhalt HKEY_LOCAL_MACHINE \Software\Microsoft\\. Netframework\policy\upgrades.</span><span class="sxs-lookup"><span data-stu-id="139a2-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="139a2-112">Dies hat die gleiche Wirkung wie [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="139a2-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="139a2-113">Bindungs Ergebnisse werden zurückgegeben, als ob das Bild, das für den-Rückruf bereitgestellt wird, in einem neuen Prozess gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="139a2-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="139a2-114">Zurzeit ignoriert `GetRequestedRuntime` den Satz von Lade baren Laufzeiten und bindet Sie an den Satz installierter Laufzeiten.</span><span class="sxs-lookup"><span data-stu-id="139a2-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="139a2-115">Mit diesem Flag kann ein Host ermitteln, an welche Laufzeit eine exe-Datei beim Start gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="139a2-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="139a2-116">Wenn `GetRequestedRuntime` keine Laufzeit finden kann, die mit den Eingabe Parametern kompatibel ist, wird ein Fehler Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="139a2-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="139a2-117">Beginnend mit dem .NET Framework 4,5 kann dieses Dialogfeld "Fehler" in Form eines Windows-Features angezeigt werden, in dem Sie gefragt werden, ob der Benutzer die entsprechende Funktion aktivieren möchte.</span><span class="sxs-lookup"><span data-stu-id="139a2-117">Beginning with the .NET Framework 4.5, this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="139a2-118">`GetRequestedRuntime` verwendet das Prozess Image (und die entsprechende Konfigurationsdatei) als zusätzliche Eingabe für den Bindungsprozess.</span><span class="sxs-lookup"><span data-stu-id="139a2-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="139a2-119">Standardmäßig wird `GetRequestedRuntime` nicht auf den Prozess Image Pfad (in der Regel die exe-Datei, die zum Starten des Prozesses verwendet wurde) zurückgreifen, wenn die Laufzeit bestimmt wird, an die die Bindung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="139a2-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="139a2-120">`GetRequestedRuntime` müssen prüfen, ob die entsprechende SKU installiert ist, wenn in der Konfigurationsdatei keine Informationen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="139a2-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="139a2-121">Dadurch können Anwendungen, die keine Konfigurationsdateien aufweisen, auf kleineren SKUs ordnungsgemäß fehlschlagen als die Standardinstallation der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="139a2-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="139a2-122">Standardmäßig überprüft `GetRequestedRuntime` nicht, ob die entsprechende SKU installiert ist, es sei denn, das SKU-Attribut ist in der Konfigurationsdatei `<supportedRuntime />` Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="139a2-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="139a2-123">`GetRequestedRuntime` sollte SEM_FAILCRITICALERRORS ignorieren (durch Aufrufen der [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) -Funktion festgelegt) und das Fehler Dialogfeld anzeigen.</span><span class="sxs-lookup"><span data-stu-id="139a2-123">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function), and show the error dialog box.</span></span> <span data-ttu-id="139a2-124">Standardmäßig SEM_FAILCRITICALERRORS unterdrückt das Fehler Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="139a2-124">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="139a2-125">Möglicherweise wurde sie von einem anderen Prozess geerbt, und der automatische Fehler ist in Ihrem Szenario nicht erwünscht.</span><span class="sxs-lookup"><span data-stu-id="139a2-125">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="139a2-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="139a2-126">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="139a2-127">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="139a2-127">Requirements</span></span>  
 <span data-ttu-id="139a2-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="139a2-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="139a2-129">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="139a2-129">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="139a2-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="139a2-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="139a2-131">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="139a2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="139a2-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="139a2-132">See also</span></span>

- [<span data-ttu-id="139a2-133">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="139a2-133">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="139a2-134">GetRequestedRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="139a2-134">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
