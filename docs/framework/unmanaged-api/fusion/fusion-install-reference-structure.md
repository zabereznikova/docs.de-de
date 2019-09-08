---
title: FUSION_INSTALL_REFERENCE-Struktur
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e81fb7c99b9fd03a69456a84f2191770f40121d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795348"
---
# <a name="fusion_install_reference-structure"></a><span data-ttu-id="3eea2-102">FUSION_INSTALL_REFERENCE-Struktur</span><span class="sxs-lookup"><span data-stu-id="3eea2-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="3eea2-103">Stellt einen Verweis auf eine Assembly dar, die von der Anwendung im globalen Assemblycache installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3eea2-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eea2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3eea2-104">Syntax</span></span>  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="3eea2-105">Member</span><span class="sxs-lookup"><span data-stu-id="3eea2-105">Members</span></span>  
  
|<span data-ttu-id="3eea2-106">Member</span><span class="sxs-lookup"><span data-stu-id="3eea2-106">Member</span></span>|<span data-ttu-id="3eea2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3eea2-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="3eea2-108">Die Größe der Struktur in Bytes.</span><span class="sxs-lookup"><span data-stu-id="3eea2-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="3eea2-109">Reserviert für zukünftige Erweiterbarkeit.</span><span class="sxs-lookup"><span data-stu-id="3eea2-109">Reserved for future extensibility.</span></span> <span data-ttu-id="3eea2-110">Dieser Wert muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="3eea2-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="3eea2-111">Die Entität, die den Verweis hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="3eea2-111">The entity that adds the reference.</span></span> <span data-ttu-id="3eea2-112">Dieses Feld kann einen der folgenden Werte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="3eea2-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="3eea2-113">- FUSION_REFCOUNT_MSI_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die mithilfe des-Microsoft Windows Installer installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3eea2-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="3eea2-114">Das `szIdentifier` Feld wird auf `MSI`festgelegt, und `szNonCanonicalData` das Feld wird auf `Windows Installer`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3eea2-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="3eea2-115">Dieses Schema wird für parallele Assemblys von Windows verwendet.</span><span class="sxs-lookup"><span data-stu-id="3eea2-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="3eea2-116">- FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die in der Schnittstelle " **Programme hinzufügen/entfernen** " angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3eea2-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="3eea2-117">Das `szIdentifier` -Feld stellt das Token bereit, das die Anwendung bei der Schnittstelle zum **Hinzufügen/Entfernen von Programmen** registriert.</span><span class="sxs-lookup"><span data-stu-id="3eea2-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="3eea2-118">- FUSION_REFCOUNT_FILEPATH_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die durch eine Datei im Dateisystem dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3eea2-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="3eea2-119">Das `szIdentifier` Feld enthält den Pfad zu dieser Datei.</span><span class="sxs-lookup"><span data-stu-id="3eea2-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="3eea2-120">- FUSION_REFCOUNT_OPAQUE_STRING_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die nur durch eine nicht transparente Zeichenfolge dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3eea2-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="3eea2-121">Das `szIdentifier` -Feld stellt diese nicht transparente Zeichenfolge bereit.</span><span class="sxs-lookup"><span data-stu-id="3eea2-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="3eea2-122">Der globale Assemblycache prüft nicht, ob nicht transparente Verweise vorhanden sind, wenn Sie diesen Wert entfernen.</span><span class="sxs-lookup"><span data-stu-id="3eea2-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="3eea2-123">- FUSION_REFCOUNT_OSINSTALL_GUID: Dieser Wert ist reserviert.</span><span class="sxs-lookup"><span data-stu-id="3eea2-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="3eea2-124">Eine eindeutige Zeichenfolge, die die Anwendung identifiziert, die die Assembly im globalen Assemblycache installiert hat.</span><span class="sxs-lookup"><span data-stu-id="3eea2-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="3eea2-125">Der Wert hängt vom Wert des `guidScheme` Felds ab.</span><span class="sxs-lookup"><span data-stu-id="3eea2-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="3eea2-126">Eine Zeichenfolge, die nur von der Entität verstanden wird, die den Verweis hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="3eea2-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="3eea2-127">Der globale Assemblycache speichert diese Zeichenfolge, verwendet Sie jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="3eea2-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3eea2-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3eea2-128">Requirements</span></span>  
 <span data-ttu-id="3eea2-129">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eea2-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eea2-130">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3eea2-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3eea2-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eea2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eea2-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3eea2-132">See also</span></span>

- [<span data-ttu-id="3eea2-133">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="3eea2-133">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="3eea2-134">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="3eea2-134">Global Assembly Cache</span></span>](../../app-domains/gac.md)
