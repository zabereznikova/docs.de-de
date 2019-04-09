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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d8d59ef282818dd9852d0ff8d2ec2abd40986d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097134"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="f397b-102">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f397b-102">IAssemblyName Interface</span></span>
<span data-ttu-id="f397b-103">Stellt Methoden zum Beschreiben von und Arbeiten mit der Identität einer Assembly eindeutig.</span><span class="sxs-lookup"><span data-stu-id="f397b-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f397b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f397b-104">Methods</span></span>  
  
|<span data-ttu-id="f397b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f397b-105">Method</span></span>|<span data-ttu-id="f397b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f397b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f397b-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="f397b-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|<span data-ttu-id="f397b-108">Erstellt eine flache Kopie dieses `IAssemblyName` Objekt.</span><span class="sxs-lookup"><span data-stu-id="f397b-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="f397b-109">Finalize-Methode</span><span class="sxs-lookup"><span data-stu-id="f397b-109">Finalize Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|<span data-ttu-id="f397b-110">Dadurch können `IAssemblyName` Objekt, das Freigeben von Ressourcen und andere Bereinigungen durchzuführen, bevor der Destruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f397b-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="f397b-111">GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="f397b-111">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|<span data-ttu-id="f397b-112">Ruft den lesbaren Namen der Assembly verwiesen wird, von diesem `IAssemblyName` Objekt.</span><span class="sxs-lookup"><span data-stu-id="f397b-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="f397b-113">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="f397b-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|<span data-ttu-id="f397b-114">Ruft ab, die einfache nicht verschlüsselte Name der Assembly verwiesen wird, von diesem `IAssemblyName` Objekt.</span><span class="sxs-lookup"><span data-stu-id="f397b-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="f397b-115">GetProperty-Methode</span><span class="sxs-lookup"><span data-stu-id="f397b-115">GetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|<span data-ttu-id="f397b-116">Ruft einen Zeiger auf die verwiesen wird, mit der angegebenen Eigenschaft `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="f397b-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="f397b-117">GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="f397b-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|<span data-ttu-id="f397b-118">Ruft die Versionsinformationen für die Assembly verwiesen wird, von diesem `IAssemblyName` Objekt.</span><span class="sxs-lookup"><span data-stu-id="f397b-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="f397b-119">IsEqual-Methode</span><span class="sxs-lookup"><span data-stu-id="f397b-119">IsEqual Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|<span data-ttu-id="f397b-120">Bestimmt, ob ein angegebener `IAssemblyName` Objekt gleich diesem ist `IAssemblyName`basierend auf den angegebenen Vergleichsflags.</span><span class="sxs-lookup"><span data-stu-id="f397b-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="f397b-121">SetProperty-Methode</span><span class="sxs-lookup"><span data-stu-id="f397b-121">SetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|<span data-ttu-id="f397b-122">Legt den Wert der Eigenschaft verwiesen wird, mit dem angegebenen `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="f397b-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f397b-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f397b-123">Requirements</span></span>  
 <span data-ttu-id="f397b-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f397b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f397b-125">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f397b-125">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="f397b-126">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f397b-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f397b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f397b-127">See also</span></span>

- [<span data-ttu-id="f397b-128">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f397b-128">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="f397b-129">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f397b-129">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
