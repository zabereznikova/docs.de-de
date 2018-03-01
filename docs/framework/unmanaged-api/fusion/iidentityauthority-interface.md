---
title: IIdentityAuthority-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 322b15252271472b5bee1dfc6a843079cebbe0b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="b49e8-102">IIdentityAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b49e8-102">IIdentityAuthority Interface</span></span>
<span data-ttu-id="b49e8-103">Verwaltet die Identitätsschlüssel für Codeobjekte.</span><span class="sxs-lookup"><span data-stu-id="b49e8-103">Manages identity keys for code objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b49e8-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b49e8-104">Methods</span></span>  
  
|<span data-ttu-id="b49e8-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b49e8-105">Method</span></span>|<span data-ttu-id="b49e8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b49e8-106">Description</span></span>|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="b49e8-107">Ruft einen Wert, der angibt, ob die beiden angegebenen [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="b49e8-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="b49e8-108">Ruft einen Wert, der angibt, ob die beiden angegebenen [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="b49e8-108">Gets a value that indicates whether the two specified [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="b49e8-109">Ruft einen Wert, der angibt, ob die beiden angegebenen Zeichenfolge Definition Identity Darstellungen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="b49e8-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|  
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="b49e8-110">Ruft einen Wert, der angibt, ob die beiden angegebenen Zeichenfolge Verweis Identität Darstellungen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="b49e8-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|  
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="b49e8-111">Ruft einen Zeiger auf ein neues `IDefinitionIdentity` Instanz, die das Codeobjekt im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="b49e8-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="b49e8-112">Ruft einen Zeiger auf ein neues `IReferenceIdentity` Instanz, die das Codeobjekt im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="b49e8-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="b49e8-113">Ruft eine formatierte Zeichenfolge-Version des angegebenen `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b49e8-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="b49e8-114">Füllt den angegebenen Breitzeichenpuffer mit eine Zeichenfolgenversion des angegebenen `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b49e8-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="b49e8-115">Ruft einen Wert, der angibt, ob das angegebene `IDefinitionIdentity` und `IReferenceIdentity` Instanzen auf demselben Codeobjekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="b49e8-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="b49e8-116">Ruft einen Wert, der angibt, ob die angegebenen Zeichenfolgen auf dasselbe Codeobjekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="b49e8-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|  
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="b49e8-117">Ruft einen Zeiger auf einen neu erstellten Zeichenfolgenschlüssel für die angegebene `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b49e8-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="b49e8-118">Ruft einen Zeiger auf einen neu erstellten Zeichenfolgenschlüssel für die angegebene `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b49e8-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="b49e8-119">Ruft einen Hashwert für den angegebenen `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b49e8-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::HashReference`|<span data-ttu-id="b49e8-120">Ruft einen Hashwert für den angegebenen `IreferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b49e8-120">Gets a hash value for the specified `IreferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="b49e8-121">Ruft eine formatierte Zeichenfolge-Version des angegebenen `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b49e8-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="b49e8-122">Füllt den angegebenen Breitzeichenpuffer mit eine Zeichenfolgenversion des angegebenen `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="b49e8-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="b49e8-123">Ruft einen Schnittstellenzeiger auf eine `IDefinitionIdentity` generiert aus der angegebenen Instanz formatierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b49e8-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|  
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="b49e8-124">Ruft einen Schnittstellenzeiger auf eine `IReferenceIdentity` generiert aus der angegebenen Instanz formatierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b49e8-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b49e8-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b49e8-125">Requirements</span></span>  
 <span data-ttu-id="b49e8-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b49e8-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b49e8-127">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="b49e8-127">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="b49e8-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b49e8-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b49e8-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b49e8-129">See Also</span></span>  
 [<span data-ttu-id="b49e8-130">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b49e8-130">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
