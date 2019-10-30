---
title: Fusion-Schnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
ms.openlocfilehash: 81c66825e69d9526abddfe06133426a2274ad08f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108193"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="4d574-102">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4d574-102">Fusion Interfaces</span></span>
<span data-ttu-id="4d574-103">In diesem Abschnitt werden die nicht verwalteten Schnittstellen beschrieben, die die Fusion-API verwendet, um auf die Eigenschaften der Ressourcen einer Anwendung zuzugreifen und die richtigen Versionen dieser Ressourcen für die Anwendung zu finden.</span><span class="sxs-lookup"><span data-stu-id="4d574-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d574-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="4d574-104">In This Section</span></span>  
 [<span data-ttu-id="4d574-105">IAppIdAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-105">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)  
 <span data-ttu-id="4d574-106">Stellt Methoden bereit, die Schlüssel für Anwendungs Identitäten und-Verweise generieren und vergleichen.</span><span class="sxs-lookup"><span data-stu-id="4d574-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="4d574-107">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-107">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)  
 <span data-ttu-id="4d574-108">Stellt eine Darstellung des globalen Assemblycaches bereit.</span><span class="sxs-lookup"><span data-stu-id="4d574-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="4d574-109">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-109">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)  
 <span data-ttu-id="4d574-110">Stellt eine einzelne Assembly im globalen Assemblycache dar.</span><span class="sxs-lookup"><span data-stu-id="4d574-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="4d574-111">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-111">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)  
 <span data-ttu-id="4d574-112">Stellt einen Enumerator für ein Array von `IAssemblyName`-Objekten dar.</span><span class="sxs-lookup"><span data-stu-id="4d574-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="4d574-113">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)  
 <span data-ttu-id="4d574-114">Stellt Methoden zum beschreiben und arbeiten mit der eindeutigen Identität einer Assembly bereit.</span><span class="sxs-lookup"><span data-stu-id="4d574-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="4d574-115">IDefinitionAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-115">IDefinitionAppId Interface</span></span>](idefinitionappid-interface.md)  
 <span data-ttu-id="4d574-116">Stellt einen eindeutigen Bezeichner für den Code dar, der die Anwendung im aktuellen Gültigkeitsbereich definiert.</span><span class="sxs-lookup"><span data-stu-id="4d574-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="4d574-117">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-117">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)  
 <span data-ttu-id="4d574-118">Stellt die eindeutige Signatur des Codes dar, der die Anwendung im aktuellen Gültigkeitsbereich definiert.</span><span class="sxs-lookup"><span data-stu-id="4d574-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="4d574-119">IEnumDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-119">IEnumDefinitionIdentity Interface</span></span>](ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="4d574-120">Dient als Enumerator für eine Auflistung von `IDefinitionIdentity`-Objekten.</span><span class="sxs-lookup"><span data-stu-id="4d574-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="4d574-121">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)  
 <span data-ttu-id="4d574-122">Dient als Enumerator für die Attribute des Code-Objekts im aktuellen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="4d574-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="4d574-123">IEnumReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-123">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)  
 <span data-ttu-id="4d574-124">Dient als Enumerator für eine Auflistung von `IReferenceIdentity`-Objekten.</span><span class="sxs-lookup"><span data-stu-id="4d574-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="4d574-125">IIdentityAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-125">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)  
 <span data-ttu-id="4d574-126">Verwaltet Identitätsschlüssel für Code Objekte.</span><span class="sxs-lookup"><span data-stu-id="4d574-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="4d574-127">IInstallReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-127">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)  
 <span data-ttu-id="4d574-128">Stellt einen Enumerator für die Assemblys dar, auf die im globalen Assemblycache installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4d574-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="4d574-129">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-129">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)  
 <span data-ttu-id="4d574-130">Stellt ein Element dar, das im globalen Assemblycache installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4d574-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="4d574-131">IReferenceAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-131">IReferenceAppId Interface</span></span>](ireferenceappid-interface.md)  
 <span data-ttu-id="4d574-132">Stellt einen Verweis auf den eindeutigen Bezeichner für die Anwendung im aktuellen Gültigkeitsbereich dar.</span><span class="sxs-lookup"><span data-stu-id="4d574-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="4d574-133">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d574-133">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)  
 <span data-ttu-id="4d574-134">Stellt einen Verweis auf die eindeutige Signatur eines Code Objekts dar.</span><span class="sxs-lookup"><span data-stu-id="4d574-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4d574-135">Referenz</span><span class="sxs-lookup"><span data-stu-id="4d574-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="4d574-136">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="4d574-136">Related Sections</span></span>  
 [<span data-ttu-id="4d574-137">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="4d574-137">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)  
  
 [<span data-ttu-id="4d574-138">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="4d574-138">Fusion Enumerations</span></span>](fusion-enumerations.md)  
  
 [<span data-ttu-id="4d574-139">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="4d574-139">Fusion Structures</span></span>](fusion-structures.md)
