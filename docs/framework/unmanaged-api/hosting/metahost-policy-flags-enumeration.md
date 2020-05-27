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
ms.openlocfilehash: bb40ed65a2e34f1bf293e4c4c842d7db63d2eaa5
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008442"
---
# <a name="metahost_policy_flags-enumeration"></a><span data-ttu-id="beba0-102">METAHOST_POLICY_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="beba0-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="beba0-103">Stellt Bindungs Richtlinien bereit, die den meisten Lauf Zeit Hosts gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="beba0-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="beba0-104">Diese Enumeration wird von der [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="beba0-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beba0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="beba0-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="beba0-106">Member</span><span class="sxs-lookup"><span data-stu-id="beba0-106">Members</span></span>  
  
|<span data-ttu-id="beba0-107">Member</span><span class="sxs-lookup"><span data-stu-id="beba0-107">Member</span></span>|<span data-ttu-id="beba0-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beba0-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="beba0-109">Definiert die Richtlinie für hohe Kompatibilität, bei der keine Common Language Runtime (CLR) berücksichtigt werden, die in den aktuellen Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="beba0-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="beba0-110">Stattdessen werden nur die installierten clrs und die Einstellungen der Komponente, die von der Assemblydatei selbst abgeleitet sind, die deklarierte integrierte Version oder die Konfigurationsdatei berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="beba0-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="beba0-111">Wendet die Upgraderichtlinie auf das Versions Bindungs Ergebnis an, wenn keine genaue Entsprechung gefunden wurde, basierend auf dem Inhalt von HKEY_LOCAL_MACHINE \Software\Microsoft \\ . Netframework\policy\upgrades.</span><span class="sxs-lookup"><span data-stu-id="beba0-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="beba0-112">Dies hat die gleiche Wirkung wie [RUNTIME_INFO_UPGRADE_VERSION](runtime-info-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="beba0-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="beba0-113">Bindungs Ergebnisse werden zurückgegeben, als ob das Bild, das für den-Rückruf bereitgestellt wird, in einem neuen Prozess gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="beba0-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="beba0-114">Zurzeit `GetRequestedRuntime` ignoriert den Satz von Lade baren Laufzeiten und bindet an den Satz installierter Laufzeiten.</span><span class="sxs-lookup"><span data-stu-id="beba0-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="beba0-115">Mit diesem Flag kann ein Host ermitteln, an welche Laufzeit eine exe-Datei beim Start gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="beba0-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="beba0-116">Ein Fehler Dialogfeld wird angezeigt, wenn keine Laufzeitumgebung `GetRequestedRuntime` finden kann, die mit den Eingabe Parametern kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="beba0-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="beba0-117">Beginnend mit dem .NET Framework 4,5 kann dieses Dialogfeld "Fehler" in Form eines Windows-Features angezeigt werden, in dem Sie gefragt werden, ob der Benutzer die entsprechende Funktion aktivieren möchte.</span><span class="sxs-lookup"><span data-stu-id="beba0-117">Beginning with the .NET Framework 4.5, this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="beba0-118">`GetRequestedRuntime`verwendet das Prozess Image (und jede zugehörige Konfigurationsdatei) als zusätzliche Eingabe für den Bindungsprozess.</span><span class="sxs-lookup"><span data-stu-id="beba0-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="beba0-119">Standardmäßig wird `GetRequestedRuntime` bei der Bestimmung der Laufzeit, an die die Bindung erfolgen soll, nicht auf den Prozess Image Pfad (in der Regel die zum Starten des Prozesses verwendete exe-Datei) zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="beba0-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="beba0-120">`GetRequestedRuntime`Es muss überprüft werden, ob die entsprechende SKU installiert ist, wenn in der Konfigurationsdatei keine Informationen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="beba0-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="beba0-121">Dadurch können Anwendungen, die keine Konfigurationsdateien aufweisen, auf kleineren SKUs ordnungsgemäß fehlschlagen als die Standardinstallation der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="beba0-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="beba0-122">Standardmäßig `GetRequestedRuntime` überprüft nicht, ob die entsprechende SKU installiert ist, es sei denn, das SKU-Attribut ist im Konfigurationsdatei `<supportedRuntime />` Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="beba0-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="beba0-123">`GetRequestedRuntime`sollte SEM_FAILCRITICALERRORS (das durch Aufrufen der [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) -Funktion festgelegt wird) ignorieren und das Fehler Dialogfeld anzeigen.</span><span class="sxs-lookup"><span data-stu-id="beba0-123">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function), and show the error dialog box.</span></span> <span data-ttu-id="beba0-124">Standardmäßig SEM_FAILCRITICALERRORS unterdrückt das Fehler Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="beba0-124">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="beba0-125">Möglicherweise wurde sie von einem anderen Prozess geerbt, und der automatische Fehler ist in Ihrem Szenario nicht erwünscht.</span><span class="sxs-lookup"><span data-stu-id="beba0-125">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="beba0-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="beba0-126">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beba0-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="beba0-127">Requirements</span></span>  
 <span data-ttu-id="beba0-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beba0-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beba0-129">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="beba0-129">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="beba0-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="beba0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="beba0-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beba0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beba0-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="beba0-132">See also</span></span>

- [<span data-ttu-id="beba0-133">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="beba0-133">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="beba0-134">GetRequestedRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="beba0-134">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)
