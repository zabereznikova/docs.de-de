---
title: FUSION_INSTALL_REFERENCE-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FUSION_INSTALL_REFERENCE
api_location: fusion.dll
api_type: COM
f1_keywords: FUSION_INSTALL_REFERENCE
helpviewer_keywords: FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 244ea215b6668685920a454c1bd9da065076f38b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="fusioninstallreference-structure"></a><span data-ttu-id="fa50a-102">FUSION_INSTALL_REFERENCE-Struktur</span><span class="sxs-lookup"><span data-stu-id="fa50a-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="fa50a-103">Stellt einen Verweis, den eine Anwendung eine Assembly ändert, der die Anwendung im globalen Assemblycache installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fa50a-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa50a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa50a-104">Syntax</span></span>  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="fa50a-105">Member</span><span class="sxs-lookup"><span data-stu-id="fa50a-105">Members</span></span>  
  
|<span data-ttu-id="fa50a-106">Member</span><span class="sxs-lookup"><span data-stu-id="fa50a-106">Member</span></span>|<span data-ttu-id="fa50a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa50a-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="fa50a-108">Die Größe der Struktur in Bytes.</span><span class="sxs-lookup"><span data-stu-id="fa50a-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="fa50a-109">Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="fa50a-109">Reserved for future extensibility.</span></span> <span data-ttu-id="fa50a-110">Dieser Wert muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="fa50a-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="fa50a-111">Die Entität, die den Verweis hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="fa50a-111">The entity that adds the reference.</span></span> <span data-ttu-id="fa50a-112">Dieses Feld kann einen der folgenden Werte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="fa50a-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="fa50a-113">-FUSION_REFCOUNT_MSI_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die mit Microsoft Windows Installer installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fa50a-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="fa50a-114">Die `szIdentifier` Feld `MSI`, und die `szNonCanonicalData` Feld `Windows Installer`.</span><span class="sxs-lookup"><span data-stu-id="fa50a-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="fa50a-115">Dieses Schema wird für Windows-Seite-an-Seite-Assemblys verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa50a-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="fa50a-116">-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: Die Assembly von einer Anwendung, die in angezeigt verweist die **Programme hinzufügen/entfernen** Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fa50a-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="fa50a-117">Die `szIdentifier` Feld gibt das Token, das die Anwendung mit registriert die **Programme hinzufügen/entfernen** Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fa50a-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="fa50a-118">-FUSION_REFCOUNT_FILEPATH_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die durch eine Datei im Dateisystem dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fa50a-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="fa50a-119">Die `szIdentifier` Feld gibt den Pfad zu dieser Datei.</span><span class="sxs-lookup"><span data-stu-id="fa50a-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="fa50a-120">-FUSION_REFCOUNT_OPAQUE_STRING_GUID: Auf die Assembly wird von einer Anwendung verwiesen, die nur durch eine nicht transparente Zeichenfolge dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fa50a-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="fa50a-121">Die `szIdentifier` Feld bietet diese nicht transparente Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fa50a-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="fa50a-122">Im globalen Assemblycache überprüft nicht das Vorhandensein von nicht transparenten verweisen, wenn Sie diesen Wert entfernen.</span><span class="sxs-lookup"><span data-stu-id="fa50a-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="fa50a-123">-FUSION_REFCOUNT_OSINSTALL_GUID: Dieser Wert ist reserviert.</span><span class="sxs-lookup"><span data-stu-id="fa50a-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="fa50a-124">Eine eindeutige Zeichenfolge, die die Anwendung identifiziert, die die Assembly im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="fa50a-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="fa50a-125">Der Wert hängt vom Wert von der `guidScheme` Feld.</span><span class="sxs-lookup"><span data-stu-id="fa50a-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="fa50a-126">Eine Zeichenfolge, die nur von der Entität verstanden wird, die den Verweis hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="fa50a-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="fa50a-127">Der globale Assemblycache speichert diese Zeichenfolge, aber nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa50a-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fa50a-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa50a-128">Requirements</span></span>  
 <span data-ttu-id="fa50a-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa50a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa50a-130">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="fa50a-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fa50a-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa50a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa50a-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa50a-132">See Also</span></span>  
 [<span data-ttu-id="fa50a-133">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="fa50a-133">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="fa50a-134">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="fa50a-134">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
