---
title: IAssemblyName-Schnittstelle
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
ms.openlocfilehash: de49d66667033dfc6918b139f90cd5523661597f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134314"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="044a0-102">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="044a0-102">IAssemblyName Interface</span></span>
<span data-ttu-id="044a0-103">Stellt Methoden zum beschreiben und arbeiten mit der eindeutigen Identität einer Assembly bereit.</span><span class="sxs-lookup"><span data-stu-id="044a0-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="044a0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="044a0-104">Methods</span></span>  
  
|<span data-ttu-id="044a0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="044a0-105">Method</span></span>|<span data-ttu-id="044a0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="044a0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="044a0-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="044a0-107">Clone Method</span></span>](iassemblyname-clone-method.md)|<span data-ttu-id="044a0-108">Erstellt eine flache Kopie dieses `IAssemblyName` Objekts.</span><span class="sxs-lookup"><span data-stu-id="044a0-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="044a0-109">Finalize-Methode</span><span class="sxs-lookup"><span data-stu-id="044a0-109">Finalize Method</span></span>](iassemblyname-finalize-method.md)|<span data-ttu-id="044a0-110">Ermöglicht es diesem `IAssemblyName` Objekt, Ressourcen freizugeben und andere Bereinigungs Vorgänge durchzuführen, bevor der Dekonstruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="044a0-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="044a0-111">GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="044a0-111">GetDisplayName Method</span></span>](iassemblyname-getdisplayname-method.md)|<span data-ttu-id="044a0-112">Ruft den lesbaren Namen der Assembly ab, auf die von diesem `IAssemblyName` Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="044a0-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="044a0-113">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="044a0-113">GetName Method</span></span>](iassemblyname-getname-method.md)|<span data-ttu-id="044a0-114">Ruft den einfachen, unverschlüsselten Namen der Assembly ab, auf die von diesem `IAssemblyName` Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="044a0-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="044a0-115">GetProperty-Methode</span><span class="sxs-lookup"><span data-stu-id="044a0-115">GetProperty Method</span></span>](iassemblyname-getproperty-method.md)|<span data-ttu-id="044a0-116">Ruft einen Zeiger auf die Eigenschaft ab, auf die vom angegebenen `PropertyId`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="044a0-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="044a0-117">GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="044a0-117">GetVersion Method</span></span>](iassemblyname-getversion-method.md)|<span data-ttu-id="044a0-118">Ruft die Versionsinformationen für die Assembly ab, auf die von diesem `IAssemblyName` Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="044a0-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="044a0-119">IsEqual-Methode</span><span class="sxs-lookup"><span data-stu-id="044a0-119">IsEqual Method</span></span>](iassemblyname-isequal-method.md)|<span data-ttu-id="044a0-120">Bestimmt basierend auf den angegebenen Vergleichsflags, ob ein angegebenes `IAssemblyName` Objekt gleich diesem `IAssemblyName`ist.</span><span class="sxs-lookup"><span data-stu-id="044a0-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="044a0-121">SetProperty-Methode</span><span class="sxs-lookup"><span data-stu-id="044a0-121">SetProperty Method</span></span>](iassemblyname-setproperty-method.md)|<span data-ttu-id="044a0-122">Legt den Wert der Eigenschaft fest, auf die vom angegebenen `PropertyId`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="044a0-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="044a0-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="044a0-123">Requirements</span></span>  
 <span data-ttu-id="044a0-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="044a0-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="044a0-125">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="044a0-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="044a0-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="044a0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="044a0-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="044a0-127">See also</span></span>

- [<span data-ttu-id="044a0-128">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="044a0-128">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="044a0-129">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="044a0-129">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
