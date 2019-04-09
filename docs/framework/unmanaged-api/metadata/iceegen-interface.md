---
title: ICeeGen-Schnittstelle
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fb081c48abf899b44da1c1351efa3f6036f1c8d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176123"
---
# <a name="iceegen-interface"></a><span data-ttu-id="a47f5-102">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47f5-102">ICeeGen Interface</span></span>
<span data-ttu-id="a47f5-103">Stellt Methoden zur dynamischen Codekompilierung bereit.</span><span class="sxs-lookup"><span data-stu-id="a47f5-103">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="a47f5-104">Diese Schnittstelle ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a47f5-104">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a47f5-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a47f5-105">Methods</span></span>  
  
|<span data-ttu-id="a47f5-106">Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-106">Method</span></span>|<span data-ttu-id="a47f5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a47f5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a47f5-108">AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-108">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|<span data-ttu-id="a47f5-109">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-109">Obsolete.</span></span> <span data-ttu-id="a47f5-110">Fügt eine .reloc-Anweisung in die Codebasis.</span><span class="sxs-lookup"><span data-stu-id="a47f5-110">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="a47f5-111">AllocateMethodBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-111">AllocateMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="a47f5-112">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-112">Obsolete.</span></span> <span data-ttu-id="a47f5-113">Erstellt einen Puffer mit der angegebenen Größe für eine Methode und ruft die relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="a47f5-113">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="a47f5-114">ComputePointer-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-114">ComputePointer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|<span data-ttu-id="a47f5-115">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-115">Obsolete.</span></span> <span data-ttu-id="a47f5-116">Bestimmt den Puffer für den angegebenen Codeabschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47f5-116">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="a47f5-117">EmitString-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-117">EmitString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|<span data-ttu-id="a47f5-118">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-118">Obsolete.</span></span> <span data-ttu-id="a47f5-119">Gibt die angegebene Zeichenfolge in die CodeBase.</span><span class="sxs-lookup"><span data-stu-id="a47f5-119">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="a47f5-120">GenerateCeeFile-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-120">GenerateCeeFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|<span data-ttu-id="a47f5-121">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-121">Obsolete.</span></span> <span data-ttu-id="a47f5-122">Generiert eine Codebasis-Datei, die derzeit geladene, in die Codebasis enthält `ICeeGen`.</span><span class="sxs-lookup"><span data-stu-id="a47f5-122">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="a47f5-123">GenerateCeeMemoryImage-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-123">GenerateCeeMemoryImage Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|<span data-ttu-id="a47f5-124">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-124">Obsolete.</span></span> <span data-ttu-id="a47f5-125">Generiert ein Image im Arbeitsspeicher für die Codebasis.</span><span class="sxs-lookup"><span data-stu-id="a47f5-125">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="a47f5-126">GetIlSection-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-126">GetIlSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|<span data-ttu-id="a47f5-127">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-127">Obsolete.</span></span> <span data-ttu-id="a47f5-128">Ruft ab, der Teil der Zwischensprache Codebasis auf das angegebene Handle verweist.</span><span class="sxs-lookup"><span data-stu-id="a47f5-128">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="a47f5-129">GetIMapTokenIface-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-129">GetIMapTokenIface Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|<span data-ttu-id="a47f5-130">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-130">Obsolete.</span></span> <span data-ttu-id="a47f5-131">Ruft die Schnittstelle, die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a47f5-131">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="a47f5-132">GetMethodBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-132">GetMethodBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|<span data-ttu-id="a47f5-133">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-133">Obsolete.</span></span> <span data-ttu-id="a47f5-134">Ruft einen Puffer von geeigneter Größe für die Methode an der angegebenen relativen virtuellen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="a47f5-134">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="a47f5-135">GetSectionBlock-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-135">GetSectionBlock Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|<span data-ttu-id="a47f5-136">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-136">Obsolete.</span></span> <span data-ttu-id="a47f5-137">Ruft einen Abschnittsblock im des Codes ab.</span><span class="sxs-lookup"><span data-stu-id="a47f5-137">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="a47f5-138">GetSectionCreate-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-138">GetSectionCreate Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|<span data-ttu-id="a47f5-139">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-139">Obsolete.</span></span> <span data-ttu-id="a47f5-140">Wird generiert, und ruft einen Codeabschnitt, der mit dem angegebenen Namen und der Flagwerte.</span><span class="sxs-lookup"><span data-stu-id="a47f5-140">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="a47f5-141">GetSectionDataLen-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-141">GetSectionDataLen Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|<span data-ttu-id="a47f5-142">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-142">Obsolete.</span></span> <span data-ttu-id="a47f5-143">Ruft die Länge des angegebenen Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="a47f5-143">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="a47f5-144">GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-144">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|<span data-ttu-id="a47f5-145">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-145">Obsolete.</span></span> <span data-ttu-id="a47f5-146">Ruft die Zeichenfolge, die an der angegebenen relativen virtuellen Adresse gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a47f5-146">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="a47f5-147">GetStringSection-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-147">GetStringSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|<span data-ttu-id="a47f5-148">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-148">Obsolete.</span></span> <span data-ttu-id="a47f5-149">Ruft eine Zeichenfolgendarstellung der Codeabschnitt, der auf die verwiesen wird durch das angegebene Handle ab.</span><span class="sxs-lookup"><span data-stu-id="a47f5-149">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="a47f5-150">TruncateSection-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f5-150">TruncateSection Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|<span data-ttu-id="a47f5-151">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="a47f5-151">Obsolete.</span></span> <span data-ttu-id="a47f5-152">Schneidet den angegebenen Codeabschnitt durch die angegebene Länge ab.</span><span class="sxs-lookup"><span data-stu-id="a47f5-152">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a47f5-153">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a47f5-153">Requirements</span></span>  
 <span data-ttu-id="a47f5-154">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a47f5-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a47f5-155">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a47f5-155">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a47f5-156">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a47f5-156">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="a47f5-157">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a47f5-157">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a47f5-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a47f5-158">See also</span></span>

- [<span data-ttu-id="a47f5-159">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a47f5-159">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
