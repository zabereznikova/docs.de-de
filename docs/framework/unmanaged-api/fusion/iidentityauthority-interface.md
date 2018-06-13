---
title: IIdentityAuthority-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 692ac4ef4fe8ea64c6a63dc2f02cc04244a842c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432525"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="3810a-102">IIdentityAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3810a-102">IIdentityAuthority Interface</span></span>
<span data-ttu-id="3810a-103">Verwaltet die Identitätsschlüssel für Codeobjekte.</span><span class="sxs-lookup"><span data-stu-id="3810a-103">Manages identity keys for code objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3810a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3810a-104">Methods</span></span>  
  
|<span data-ttu-id="3810a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3810a-105">Method</span></span>|<span data-ttu-id="3810a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3810a-106">Description</span></span>|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="3810a-107">Ruft einen Wert, der angibt, ob die beiden angegebenen [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="3810a-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="3810a-108">Ruft einen Wert, der angibt, ob die beiden angegebenen [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="3810a-108">Gets a value that indicates whether the two specified [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instances are equal.</span></span>|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="3810a-109">Ruft einen Wert, der angibt, ob die beiden angegebenen Zeichenfolge Definition Identity Darstellungen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="3810a-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|  
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="3810a-110">Ruft einen Wert, der angibt, ob die beiden angegebenen Zeichenfolge Verweis Identität Darstellungen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="3810a-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|  
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="3810a-111">Ruft einen Zeiger auf ein neues `IDefinitionIdentity` Instanz, die das Codeobjekt im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="3810a-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="3810a-112">Ruft einen Zeiger auf ein neues `IReferenceIdentity` Instanz, die das Codeobjekt im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="3810a-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|  
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="3810a-113">Ruft eine formatierte Zeichenfolge-Version des angegebenen `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="3810a-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="3810a-114">Füllt den angegebenen Breitzeichenpuffer mit eine Zeichenfolgenversion des angegebenen `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="3810a-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="3810a-115">Ruft einen Wert, der angibt, ob das angegebene `IDefinitionIdentity` und `IReferenceIdentity` Instanzen auf demselben Codeobjekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="3810a-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="3810a-116">Ruft einen Wert, der angibt, ob die angegebenen Zeichenfolgen auf dasselbe Codeobjekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="3810a-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|  
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="3810a-117">Ruft einen Zeiger auf einen neu erstellten Zeichenfolgenschlüssel für die angegebene `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="3810a-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="3810a-118">Ruft einen Zeiger auf einen neu erstellten Zeichenfolgenschlüssel für die angegebene `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="3810a-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="3810a-119">Ruft einen Hashwert für den angegebenen `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="3810a-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|  
|`IIdentityAuthority::HashReference`|<span data-ttu-id="3810a-120">Ruft einen Hashwert für den angegebenen `IreferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="3810a-120">Gets a hash value for the specified `IreferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="3810a-121">Ruft eine formatierte Zeichenfolge-Version des angegebenen `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="3810a-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="3810a-122">Füllt den angegebenen Breitzeichenpuffer mit eine Zeichenfolgenversion des angegebenen `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="3810a-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|  
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="3810a-123">Ruft einen Schnittstellenzeiger auf eine `IDefinitionIdentity` generiert aus der angegebenen Instanz formatierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3810a-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|  
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="3810a-124">Ruft einen Schnittstellenzeiger auf eine `IReferenceIdentity` generiert aus der angegebenen Instanz formatierte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3810a-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3810a-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3810a-125">Requirements</span></span>  
 <span data-ttu-id="3810a-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3810a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3810a-127">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="3810a-127">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="3810a-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3810a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3810a-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3810a-129">See Also</span></span>  
 [<span data-ttu-id="3810a-130">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3810a-130">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
