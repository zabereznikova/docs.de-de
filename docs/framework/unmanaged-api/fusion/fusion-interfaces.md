---
title: Fusion-Schnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec2fd3b309820f2bfb7f6091cc3db720db497408
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697666"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="5e193-102">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5e193-102">Fusion Interfaces</span></span>
<span data-ttu-id="5e193-103">In diesem Abschnitt wird beschrieben, die nicht verwalteten Schnittstellen, die die Fusion-API verwendet, um die Eigenschaften der Ressourcen einer Anwendung zugreifen und die richtigen Versionen dieser Ressourcen für die Anwendung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="5e193-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e193-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5e193-104">In This Section</span></span>  
 [<span data-ttu-id="5e193-105">IAppIdAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-105">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 <span data-ttu-id="5e193-106">Stellt Methoden, die zum Generieren und Vergleichen von Schlüsseln für Anwendungsidentitäten und Verweise bereit.</span><span class="sxs-lookup"><span data-stu-id="5e193-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="5e193-107">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-107">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 <span data-ttu-id="5e193-108">Bietet eine Darstellung der im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="5e193-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="5e193-109">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-109">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 <span data-ttu-id="5e193-110">Stellt eine einzelne Assembly im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="5e193-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="5e193-111">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-111">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 <span data-ttu-id="5e193-112">Stellt einen Enumerator für ein Array von `IAssemblyName` Objekte.</span><span class="sxs-lookup"><span data-stu-id="5e193-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="5e193-113">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 <span data-ttu-id="5e193-114">Stellt Methoden zum Beschreiben von und Arbeiten mit der Identität einer Assembly eindeutig.</span><span class="sxs-lookup"><span data-stu-id="5e193-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="5e193-115">IDefinitionAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-115">IDefinitionAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)  
 <span data-ttu-id="5e193-116">Stellt einen eindeutigen Bezeichner für den Code, der die Anwendung im aktuellen Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="5e193-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="5e193-117">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-117">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 <span data-ttu-id="5e193-118">Stellt die eindeutige Signatur des Codes, der die Anwendung im aktuellen Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="5e193-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="5e193-119">IEnumDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-119">IEnumDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="5e193-120">Dient als Enumerator für eine Auflistung von `IDefinitionIdentity` Objekte.</span><span class="sxs-lookup"><span data-stu-id="5e193-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="5e193-121">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)  
 <span data-ttu-id="5e193-122">Dient als ein Enumerator für die Attribute des Codeobjekts im aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="5e193-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="5e193-123">IEnumReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-123">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 <span data-ttu-id="5e193-124">Dient als Enumerator für eine Auflistung von `IReferenceIdentity` Objekte.</span><span class="sxs-lookup"><span data-stu-id="5e193-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="5e193-125">IIdentityAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-125">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 <span data-ttu-id="5e193-126">Verwaltet die Identitätsschlüssel für Codeobjekte.</span><span class="sxs-lookup"><span data-stu-id="5e193-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="5e193-127">IInstallReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-127">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 <span data-ttu-id="5e193-128">Stellt einen Enumerator für die referenzierten Assemblys im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="5e193-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="5e193-129">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-129">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 <span data-ttu-id="5e193-130">Stellt ein Element im globalen Assemblycache installiert.</span><span class="sxs-lookup"><span data-stu-id="5e193-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="5e193-131">IReferenceAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-131">IReferenceAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)  
 <span data-ttu-id="5e193-132">Stellt einen Verweis auf den eindeutigen Bezeichner für die Anwendung im aktuellen Bereich.</span><span class="sxs-lookup"><span data-stu-id="5e193-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="5e193-133">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e193-133">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)  
 <span data-ttu-id="5e193-134">Stellt einen Verweis auf die eindeutige Signatur ein Codeobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="5e193-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5e193-135">Referenz</span><span class="sxs-lookup"><span data-stu-id="5e193-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="5e193-136">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="5e193-136">Related Sections</span></span>  
 [<span data-ttu-id="5e193-137">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="5e193-137">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
  
 [<span data-ttu-id="5e193-138">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="5e193-138">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [<span data-ttu-id="5e193-139">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="5e193-139">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
