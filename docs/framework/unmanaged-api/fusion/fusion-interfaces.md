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
ms.openlocfilehash: 1605605f8510f7ccf5f0bbf2f3f6b09050a16025
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795303"
---
# <a name="fusion-interfaces"></a><span data-ttu-id="84db4-102">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="84db4-102">Fusion Interfaces</span></span>
<span data-ttu-id="84db4-103">In diesem Abschnitt werden die nicht verwalteten Schnittstellen beschrieben, die die Fusion-API verwendet, um auf die Eigenschaften der Ressourcen einer Anwendung zuzugreifen und die richtigen Versionen dieser Ressourcen für die Anwendung zu finden.</span><span class="sxs-lookup"><span data-stu-id="84db4-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84db4-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="84db4-104">In This Section</span></span>  
 [<span data-ttu-id="84db4-105">IAppIdAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-105">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)  
 <span data-ttu-id="84db4-106">Stellt Methoden bereit, die Schlüssel für Anwendungs Identitäten und-Verweise generieren und vergleichen.</span><span class="sxs-lookup"><span data-stu-id="84db4-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="84db4-107">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-107">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)  
 <span data-ttu-id="84db4-108">Stellt eine Darstellung des globalen Assemblycaches bereit.</span><span class="sxs-lookup"><span data-stu-id="84db4-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="84db4-109">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-109">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)  
 <span data-ttu-id="84db4-110">Stellt eine einzelne Assembly im globalen Assemblycache dar.</span><span class="sxs-lookup"><span data-stu-id="84db4-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="84db4-111">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-111">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)  
 <span data-ttu-id="84db4-112">Stellt einen Enumerator für ein Array von `IAssemblyName` -Objekten dar.</span><span class="sxs-lookup"><span data-stu-id="84db4-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="84db4-113">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)  
 <span data-ttu-id="84db4-114">Stellt Methoden zum beschreiben und arbeiten mit der eindeutigen Identität einer Assembly bereit.</span><span class="sxs-lookup"><span data-stu-id="84db4-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="84db4-115">IDefinitionAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-115">IDefinitionAppId Interface</span></span>](idefinitionappid-interface.md)  
 <span data-ttu-id="84db4-116">Stellt einen eindeutigen Bezeichner für den Code dar, der die Anwendung im aktuellen Gültigkeitsbereich definiert.</span><span class="sxs-lookup"><span data-stu-id="84db4-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="84db4-117">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-117">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)  
 <span data-ttu-id="84db4-118">Stellt die eindeutige Signatur des Codes dar, der die Anwendung im aktuellen Gültigkeitsbereich definiert.</span><span class="sxs-lookup"><span data-stu-id="84db4-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="84db4-119">IEnumDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-119">IEnumDefinitionIdentity Interface</span></span>](ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="84db4-120">Dient als Enumerator für eine Auflistung von `IDefinitionIdentity` -Objekten.</span><span class="sxs-lookup"><span data-stu-id="84db4-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="84db4-121">IEnumIDENTITY_ATTRIBUTE-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)  
 <span data-ttu-id="84db4-122">Dient als Enumerator für die Attribute des Code-Objekts im aktuellen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="84db4-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="84db4-123">IEnumReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-123">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)  
 <span data-ttu-id="84db4-124">Dient als Enumerator für eine Auflistung von `IReferenceIdentity` -Objekten.</span><span class="sxs-lookup"><span data-stu-id="84db4-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="84db4-125">IIdentityAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-125">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)  
 <span data-ttu-id="84db4-126">Verwaltet Identitätsschlüssel für Code Objekte.</span><span class="sxs-lookup"><span data-stu-id="84db4-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="84db4-127">IInstallReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-127">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)  
 <span data-ttu-id="84db4-128">Stellt einen Enumerator für die Assemblys dar, auf die im globalen Assemblycache installiert ist.</span><span class="sxs-lookup"><span data-stu-id="84db4-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="84db4-129">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-129">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)  
 <span data-ttu-id="84db4-130">Stellt ein Element dar, das im globalen Assemblycache installiert ist.</span><span class="sxs-lookup"><span data-stu-id="84db4-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="84db4-131">IReferenceAppId-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-131">IReferenceAppId Interface</span></span>](ireferenceappid-interface.md)  
 <span data-ttu-id="84db4-132">Stellt einen Verweis auf den eindeutigen Bezeichner für die Anwendung im aktuellen Gültigkeitsbereich dar.</span><span class="sxs-lookup"><span data-stu-id="84db4-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="84db4-133">IReferenceIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84db4-133">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)  
 <span data-ttu-id="84db4-134">Stellt einen Verweis auf die eindeutige Signatur eines Code Objekts dar.</span><span class="sxs-lookup"><span data-stu-id="84db4-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="84db4-135">Referenz</span><span class="sxs-lookup"><span data-stu-id="84db4-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="84db4-136">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="84db4-136">Related Sections</span></span>  
 [<span data-ttu-id="84db4-137">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="84db4-137">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)  
  
 [<span data-ttu-id="84db4-138">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="84db4-138">Fusion Enumerations</span></span>](fusion-enumerations.md)  
  
 [<span data-ttu-id="84db4-139">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="84db4-139">Fusion Structures</span></span>](fusion-structures.md)
