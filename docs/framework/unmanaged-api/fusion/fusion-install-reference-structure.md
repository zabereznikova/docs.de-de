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
ms.openlocfilehash: 611b4a543a1de7c6163ec45ff7f17d07726569ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936486"
---
# <a name="fusioninstallreference-structure"></a><span data-ttu-id="daf61-102">FUSION_INSTALL_REFERENCE-Struktur</span><span class="sxs-lookup"><span data-stu-id="daf61-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="daf61-103">Stellt einen Verweis, den eine Anwendung in einer Assembly zu können, die die Anwendung im globalen Assemblycache installiert ist.</span><span class="sxs-lookup"><span data-stu-id="daf61-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daf61-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="daf61-104">Syntax</span></span>  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="daf61-105">Member</span><span class="sxs-lookup"><span data-stu-id="daf61-105">Members</span></span>  
  
|<span data-ttu-id="daf61-106">Member</span><span class="sxs-lookup"><span data-stu-id="daf61-106">Member</span></span>|<span data-ttu-id="daf61-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="daf61-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="daf61-108">Die Größe der Struktur in Bytes.</span><span class="sxs-lookup"><span data-stu-id="daf61-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="daf61-109">Reserviert für zukünftige Erweiterbarkeit.</span><span class="sxs-lookup"><span data-stu-id="daf61-109">Reserved for future extensibility.</span></span> <span data-ttu-id="daf61-110">Dieser Wert muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="daf61-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="daf61-111">Die Entität, die den Verweis hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="daf61-111">The entity that adds the reference.</span></span> <span data-ttu-id="daf61-112">Dieses Feld kann einen der folgenden Werte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="daf61-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="daf61-113">-   FUSION_REFCOUNT_MSI_GUID: Die Assembly wird von einer Anwendung auf die verwiesen wird, die mit dem Microsoft Windows Installer installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="daf61-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="daf61-114">Die `szIdentifier` Feld nastaven NA hodnotu `MSI`, und die `szNonCanonicalData` Feld nastaven NA hodnotu `Windows Installer`.</span><span class="sxs-lookup"><span data-stu-id="daf61-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="daf61-115">Dieses Schema wird für Windows-Seite-an-Seite-Assemblys verwendet.</span><span class="sxs-lookup"><span data-stu-id="daf61-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="daf61-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: Die Assembly verwiesen wird, von einer Anwendung, die in angezeigt wird. die **Programme hinzufügen/entfernen** Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="daf61-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="daf61-117">Die `szIdentifier` Feld enthält das Token, das die Anwendung mit registriert die **Programme hinzufügen/entfernen** Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="daf61-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="daf61-118">-   FUSION_REFCOUNT_FILEPATH_GUID: Die Assembly wird von einer Anwendung auf die verwiesen wird, die von einer Datei im Dateisystem dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="daf61-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="daf61-119">Die `szIdentifier` Feld enthält den Pfad zu dieser Datei.</span><span class="sxs-lookup"><span data-stu-id="daf61-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="daf61-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: Die Assembly wird von einer Anwendung auf die verwiesen wird, die nur durch eine nicht transparente Zeichenfolge dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="daf61-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="daf61-121">Die `szIdentifier` Feld enthält, diese nicht transparente Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="daf61-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="daf61-122">Im globalen Assemblycache überprüft nicht das Vorhandensein von nicht transparenten verweisen, wenn Sie diesen Wert entfernen.</span><span class="sxs-lookup"><span data-stu-id="daf61-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="daf61-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: Dieser Wert ist reserviert.</span><span class="sxs-lookup"><span data-stu-id="daf61-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="daf61-124">Eine eindeutige Zeichenfolge, die die Anwendung identifiziert, die die Assembly im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="daf61-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="daf61-125">Der Wert hängt von den Wert des der `guidScheme` Feld.</span><span class="sxs-lookup"><span data-stu-id="daf61-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="daf61-126">Eine Zeichenfolge, die nur von der Entität verstanden wird, die den Verweis hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="daf61-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="daf61-127">Im globalen Assemblycache speichert diese Zeichenfolge ist, aber nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="daf61-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="daf61-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="daf61-128">Requirements</span></span>  
 <span data-ttu-id="daf61-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daf61-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daf61-130">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="daf61-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="daf61-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daf61-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf61-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daf61-132">See also</span></span>

- [<span data-ttu-id="daf61-133">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="daf61-133">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [<span data-ttu-id="daf61-134">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="daf61-134">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
