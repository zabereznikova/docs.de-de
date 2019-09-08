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
ms.openlocfilehash: 7421e0d0e1a1f0e1a5fbe0d0eb7d5a0ab2a48b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796424"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="b1253-102">IIdentityAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1253-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="b1253-103">Verwaltet Identitätsschlüssel für Code Objekte.</span><span class="sxs-lookup"><span data-stu-id="b1253-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="b1253-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b1253-104">Methods</span></span>

|<span data-ttu-id="b1253-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b1253-105">Method</span></span>|<span data-ttu-id="b1253-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1253-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="b1253-107">Ruft einen Wert ab, der angibt, ob die beiden angegebenen [IDefinitionIdentity](idefinitionidentity-interface.md) -Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="b1253-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="b1253-108">Ruft einen Wert ab, der angibt, ob die beiden angegebenen [IReferenceIdentity](ireferenceidentity-interface.md) -Instanzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="b1253-108">Gets a value that indicates whether the two specified [IReferenceIdentity](ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="b1253-109">Ruft einen Wert ab, der angibt, ob die zwei angegebenen Identitäts Darstellungen der Zeichen folgen Definitionen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="b1253-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="b1253-110">Ruft einen Wert ab, der angibt, ob die zwei angegebenen Zeichen folgen Verweis-Identitäts Darstellungen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="b1253-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="b1253-111">Ruft einen Zeiger auf eine neue `IDefinitionIdentity` -Instanz ab, die das Code Objekt im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="b1253-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="b1253-112">Ruft einen Zeiger auf eine neue `IReferenceIdentity` -Instanz ab, die das Code Objekt im aktuellen Bereich darstellt.</span><span class="sxs-lookup"><span data-stu-id="b1253-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="b1253-113">Ruft eine formatierte Zeichen folgen Version des `IDefinitionIdentity`angegebenen ab.</span><span class="sxs-lookup"><span data-stu-id="b1253-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="b1253-114">Füllt den angegebenen breit Zeichen Puffer mit einer Zeichen folgen Version des angegebenen `IDefinitionIdentity`aus.</span><span class="sxs-lookup"><span data-stu-id="b1253-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="b1253-115">Ruft einen Wert ab, der angibt, `IDefinitionIdentity` ob `IReferenceIdentity` die angegebene-Instanz und die-Instanz auf dasselbe Code Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="b1253-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="b1253-116">Ruft einen Wert ab, der angibt, ob die angegebenen Zeichen folgen auf dasselbe Code Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="b1253-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="b1253-117">Ruft einen Zeiger auf einen neu erstellten Zeichen folgen Schlüssel für den `IDefinitionIdentity`angegebenen ab.</span><span class="sxs-lookup"><span data-stu-id="b1253-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="b1253-118">Ruft einen Zeiger auf einen neu erstellten Zeichen folgen Schlüssel für den `IReferenceIdentity`angegebenen ab.</span><span class="sxs-lookup"><span data-stu-id="b1253-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="b1253-119">Ruft einen Hashwert für den angegebenen `IDefinitionIdentity`ab.</span><span class="sxs-lookup"><span data-stu-id="b1253-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="b1253-120">Ruft einen Hashwert für den angegebenen `IReferenceIdentity`ab.</span><span class="sxs-lookup"><span data-stu-id="b1253-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="b1253-121">Ruft eine formatierte Zeichen folgen Version des `IReferenceIdentity`angegebenen ab.</span><span class="sxs-lookup"><span data-stu-id="b1253-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="b1253-122">Füllt den angegebenen breit Zeichen Puffer mit einer Zeichen folgen Version des angegebenen `IReferenceIdentity`aus.</span><span class="sxs-lookup"><span data-stu-id="b1253-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="b1253-123">Ruft einen Schnittstellen Zeiger auf eine `IDefinitionIdentity` Instanz ab, die aus der angegebenen formatierten Zeichenfolge generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b1253-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="b1253-124">Ruft einen Schnittstellen Zeiger auf eine `IReferenceIdentity` Instanz ab, die aus der angegebenen formatierten Zeichenfolge generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b1253-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="b1253-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b1253-125">Requirements</span></span>

<span data-ttu-id="b1253-126">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1253-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b1253-127">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="b1253-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="b1253-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1253-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b1253-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1253-129">See also</span></span>

- [<span data-ttu-id="b1253-130">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b1253-130">Fusion Interfaces</span></span>](fusion-interfaces.md)
