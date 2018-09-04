---
title: LoadTypeLibWithResolver-Funktion
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6a217e2212bb900d7ba83ccdd9cb00d30454baf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43542861"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="f8f3d-102">LoadTypeLibWithResolver-Funktion</span><span class="sxs-lookup"><span data-stu-id="f8f3d-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="f8f3d-103">Lädt eine Typbibliothek und verwendet die angegebene [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) intern referenzierte Typbibliotheken aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-103">Loads a type library and uses the supplied [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8f3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8f3d-104">Syntax</span></span>  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8f3d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8f3d-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="f8f3d-106">[in] Der Dateipfad der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="f8f3d-107">[in] Ein [REGKIND Enumeration](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) Flag, das steuert, wie die Typbibliothek registriert wird.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-107">[in] A [REGKIND enumeration](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="f8f3d-108">Die Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="f8f3d-108">Its possible values are:</span></span>  
  
-   <span data-ttu-id="f8f3d-109">`REGKIND_DEFAULT`: Verwenden Sie Standardverhalten für die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
-   <span data-ttu-id="f8f3d-110">`REGKIND_REGISTER`: Diese Typbibliothek zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
-   <span data-ttu-id="f8f3d-111">`REGKIND_NONE`: Sie diese Typbibliothek nicht registriert.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="f8f3d-112">[in] Ein Zeiger auf die Implementierung der [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f8f3d-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="f8f3d-113">[out] Ein Verweis auf die Typbibliothek, die geladen wird.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8f3d-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f8f3d-114">Return Value</span></span>  
 <span data-ttu-id="f8f3d-115">Einer der in der folgenden Tabelle aufgeführten HRESULT-Werte.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="f8f3d-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f8f3d-116">Return value</span></span>|<span data-ttu-id="f8f3d-117">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="f8f3d-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="f8f3d-118">Erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="f8f3d-119">Nicht genügend Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="f8f3d-120">Eine oder mehrere der Zeiger sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="f8f3d-121">Eine oder mehrere der Argumente sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="f8f3d-122">Die Funktion konnte nicht in die Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="f8f3d-123">Die Systemdatenbank für die Registrierung konnte nicht geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="f8f3d-124">Die Typbibliothek konnte nicht geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="f8f3d-125">Die Typbibliothek oder einer DLL konnte nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8f3d-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8f3d-126">Remarks</span></span>  
 <span data-ttu-id="f8f3d-127">Die [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) Aufrufe der `LoadTypeLibWithResolver` Funktion während der Konvertierung der Assembly in den Typ in der Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-127">The [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="f8f3d-128">Diese Funktion lädt die angegebene Typbibliothek mit minimalen Zugriff auf die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="f8f3d-129">Die Funktion überprüft dann die Typbibliothek für Typbibliotheken intern auf die verwiesen wird, von die jede geladen und der übergeordnete Typ-Bibliothek hinzugefügt werden muss.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="f8f3d-130">Bevor eine referenzierte Typbibliothek geladen werden kann, muss die Verweis-Dateipfad in einen vollständigen Dateipfad aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="f8f3d-131">Dies erfolgt über die [ResolveTypeLib-Methode](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) , erfolgt über die [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), im übergeben wird die `pTlbResolver` Parameter.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-131">This is accomplished through the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="f8f3d-132">Wenn Sie der vollständigen Pfad der Typbibliothek, auf die verwiesen wird, bekannt ist, die `LoadTypeLibWithResolver` Funktion lädt und die Bibliothek mit übergeordneten, erstellen eine kombinierte master Typbibliothek die referenzierte Bibliothek hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="f8f3d-133">Nachdem die Funktion aufgelöst und alle intern Typbibliotheken lädt, gibt es einen Verweis auf master aufgelöst Typbibliothek in der `pptlib` Parameter.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="f8f3d-134">Die `LoadTypeLibWithResolver` Funktion ist in der Regel aufgerufen, indem die [Tlbexp.exe (Type Library Exporter-Tool)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), die stellt eine eigene, interne [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) -Implementierung in der `pTlbResolver` der Parameter.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="f8f3d-135">Wenn Sie aufrufen `LoadTypeLibWithResolver` direkt, geben Sie an Ihre eigenen [ITypeLibResolver-Schnittstelle](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) Implementierung.</span><span class="sxs-lookup"><span data-stu-id="f8f3d-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8f3d-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8f3d-136">Requirements</span></span>  
 <span data-ttu-id="f8f3d-137">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8f3d-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8f3d-138">**Header:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="f8f3d-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="f8f3d-139">**Bibliothek:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="f8f3d-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="f8f3d-140">**.NET Framework-Version:** 3.5, 3.0 und 2.0</span><span class="sxs-lookup"><span data-stu-id="f8f3d-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f3d-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8f3d-141">See Also</span></span>  
 [<span data-ttu-id="f8f3d-142">Tlbexp-Hilfsfunktionen</span><span class="sxs-lookup"><span data-stu-id="f8f3d-142">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [<span data-ttu-id="f8f3d-143">LoadTypeLibEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="f8f3d-143">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
