---
title: ICeeGen-Schnittstelle
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
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 73af58ac55fd22e5b4f19f715cb0b1a137a640a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iceegen-interface"></a><span data-ttu-id="f722d-102">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f722d-102">ICeeGen Interface</span></span>
<span data-ttu-id="f722d-103">Stellt Methoden zur dynamischen Codekompilierung bereit.</span><span class="sxs-lookup"><span data-stu-id="f722d-103">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="f722d-104">Diese Schnittstelle ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f722d-104">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f722d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f722d-105">Methods</span></span>  
  
|<span data-ttu-id="f722d-106">Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-106">Method</span></span>|<span data-ttu-id="f722d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f722d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f722d-108">AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-108">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|<span data-ttu-id="f722d-109">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-109">Obsolete.</span></span> <span data-ttu-id="f722d-110">Die CodeBase hinzugefügt eine .reloc-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f722d-110">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="f722d-111">AllocateMethodBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-111">AllocateMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="f722d-112">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-112">Obsolete.</span></span> <span data-ttu-id="f722d-113">Erstellt einen Puffer der angegebenen Größe für eine Methode und ruft die relative virtuelle Adresse der Methode ab.</span><span class="sxs-lookup"><span data-stu-id="f722d-113">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="f722d-114">ComputePointer-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-114">ComputePointer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|<span data-ttu-id="f722d-115">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-115">Obsolete.</span></span> <span data-ttu-id="f722d-116">Bestimmt den Puffer für den angegebenen Codeabschnitt.</span><span class="sxs-lookup"><span data-stu-id="f722d-116">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="f722d-117">EmitString-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-117">EmitString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|<span data-ttu-id="f722d-118">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-118">Obsolete.</span></span> <span data-ttu-id="f722d-119">Gibt die angegebene Zeichenfolge in die CodeBase aus.</span><span class="sxs-lookup"><span data-stu-id="f722d-119">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="f722d-120">GenerateCeeFile-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-120">GenerateCeeFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|<span data-ttu-id="f722d-121">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-121">Obsolete.</span></span> <span data-ttu-id="f722d-122">Generiert eine Codebasis Datei, die gegenwärtig in diese geladenen Codebasis enthält `ICeeGen`.</span><span class="sxs-lookup"><span data-stu-id="f722d-122">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="f722d-123">GenerateCeeMemoryImage-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-123">GenerateCeeMemoryImage Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|<span data-ttu-id="f722d-124">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-124">Obsolete.</span></span> <span data-ttu-id="f722d-125">Generiert ein Image im Arbeitsspeicher für die CodeBase.</span><span class="sxs-lookup"><span data-stu-id="f722d-125">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="f722d-126">GetIlSection-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-126">GetIlSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|<span data-ttu-id="f722d-127">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-127">Obsolete.</span></span> <span data-ttu-id="f722d-128">Ruft den Abschnitt der Codebasis intermediate Language auf dem angegebenen Handle verweist.</span><span class="sxs-lookup"><span data-stu-id="f722d-128">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="f722d-129">GetIMapTokenIface-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-129">GetIMapTokenIface Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|<span data-ttu-id="f722d-130">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-130">Obsolete.</span></span> <span data-ttu-id="f722d-131">Ruft die Schnittstelle, die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f722d-131">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="f722d-132">GetMethodBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-132">GetMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|<span data-ttu-id="f722d-133">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-133">Obsolete.</span></span> <span data-ttu-id="f722d-134">Ruft einen Puffer, der die geeignete Größe für die Methode an der angegebenen relativen virtuellen Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="f722d-134">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="f722d-135">GetSectionBlock-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-135">GetSectionBlock Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|<span data-ttu-id="f722d-136">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-136">Obsolete.</span></span> <span data-ttu-id="f722d-137">Ruft einen Abschnittsblock der CodeBase ab.</span><span class="sxs-lookup"><span data-stu-id="f722d-137">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="f722d-138">GetSectionCreate-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-138">GetSectionCreate Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|<span data-ttu-id="f722d-139">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-139">Obsolete.</span></span> <span data-ttu-id="f722d-140">Wird generiert, und ruft einen Codeabschnitt, der mit dem angegebenen Namen und Flagwerte.</span><span class="sxs-lookup"><span data-stu-id="f722d-140">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="f722d-141">GetSectionDataLen-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-141">GetSectionDataLen Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|<span data-ttu-id="f722d-142">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-142">Obsolete.</span></span> <span data-ttu-id="f722d-143">Ruft die Länge des angegebenen Abschnitts ab.</span><span class="sxs-lookup"><span data-stu-id="f722d-143">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="f722d-144">GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-144">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|<span data-ttu-id="f722d-145">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-145">Obsolete.</span></span> <span data-ttu-id="f722d-146">Ruft die Zeichenfolge, die an der angegebenen relativen virtuellen Adresse gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f722d-146">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="f722d-147">GetStringSection-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-147">GetStringSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|<span data-ttu-id="f722d-148">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-148">Obsolete.</span></span> <span data-ttu-id="f722d-149">Ruft eine Zeichenfolgendarstellung der Codeabschnitt, der dem angegebenen Handle verweist.</span><span class="sxs-lookup"><span data-stu-id="f722d-149">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="f722d-150">TruncateSection-Methode</span><span class="sxs-lookup"><span data-stu-id="f722d-150">TruncateSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|<span data-ttu-id="f722d-151">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f722d-151">Obsolete.</span></span> <span data-ttu-id="f722d-152">Schneidet die im Abschnitt angegebenen Code anhand der angegebenen Länge ab.</span><span class="sxs-lookup"><span data-stu-id="f722d-152">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f722d-153">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f722d-153">Requirements</span></span>  
 <span data-ttu-id="f722d-154">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f722d-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f722d-155">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f722d-155">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f722d-156">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f722d-156">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f722d-157">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f722d-157">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f722d-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f722d-158">See Also</span></span>  
 [<span data-ttu-id="f722d-159">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f722d-159">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
