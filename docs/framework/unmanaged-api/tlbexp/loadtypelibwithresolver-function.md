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
ms.openlocfilehash: 6497dd3e720874e47de9dfda74e483a642cbb181
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708230"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="490e9-102">LoadTypeLibWithResolver-Funktion</span><span class="sxs-lookup"><span data-stu-id="490e9-102">LoadTypeLibWithResolver Function</span></span>

<span data-ttu-id="490e9-103">Lädt eine Typbibliothek und verwendet die angegebene [ITypeLibResolver-Schnittstelle](itypelibresolver-interface.md) , um alle intern referenzierten Typbibliotheken aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="490e9-103">Loads a type library and uses the supplied [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="490e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="490e9-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="490e9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="490e9-105">Parameters</span></span>  

 `szFile`  
 <span data-ttu-id="490e9-106">in Der Dateipfad der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="490e9-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="490e9-107">in Ein [REGKIND](/windows/win32/api/oleauto/ne-oleauto-regkind) -Enumerationsflag, das steuert, wie die Typbibliothek registriert wird.</span><span class="sxs-lookup"><span data-stu-id="490e9-107">[in] A [REGKIND enumeration](/windows/win32/api/oleauto/ne-oleauto-regkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="490e9-108">Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="490e9-108">Its possible values are:</span></span>  
  
- <span data-ttu-id="490e9-109">`REGKIND_DEFAULT`: Verwenden Sie das Standard Registrierungs Verhalten.</span><span class="sxs-lookup"><span data-stu-id="490e9-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
- <span data-ttu-id="490e9-110">`REGKIND_REGISTER`: Registrieren Sie diese Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="490e9-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
- <span data-ttu-id="490e9-111">`REGKIND_NONE`: Registrieren Sie diese Typbibliothek nicht.</span><span class="sxs-lookup"><span data-stu-id="490e9-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="490e9-112">in Ein Zeiger auf die Implementierung der [ITypeLibResolver-Schnittstelle](itypelibresolver-interface.md).</span><span class="sxs-lookup"><span data-stu-id="490e9-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="490e9-113">vorgenommen Ein Verweis auf die Typbibliothek, die geladen wird.</span><span class="sxs-lookup"><span data-stu-id="490e9-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="490e9-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="490e9-114">Return Value</span></span>  

 <span data-ttu-id="490e9-115">Einer der HRESULT-Werte, der in der folgenden Tabelle aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="490e9-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="490e9-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="490e9-116">Return value</span></span>|<span data-ttu-id="490e9-117">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="490e9-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="490e9-118">Erfolg.</span><span class="sxs-lookup"><span data-stu-id="490e9-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="490e9-119">Nicht genügend Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="490e9-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="490e9-120">Mindestens ein Zeiger ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="490e9-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="490e9-121">Mindestens ein Argument ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="490e9-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="490e9-122">Die Funktion konnte nicht in die Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="490e9-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="490e9-123">Die System Registrierungsdatenbank konnte nicht geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="490e9-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="490e9-124">Die Typbibliothek konnte nicht geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="490e9-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="490e9-125">Die Typbibliothek oder dll konnte nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="490e9-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="490e9-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="490e9-126">Remarks</span></span>  

 <span data-ttu-id="490e9-127">Der [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) Ruft die- `LoadTypeLibWithResolver` Funktion während des Konvertierungsprozesses der Assembly in die Typbibliothek auf.</span><span class="sxs-lookup"><span data-stu-id="490e9-127">The [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="490e9-128">Diese Funktion lädt die angegebene Typbibliothek mit minimalem Zugriff auf die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="490e9-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="490e9-129">Die-Funktion untersucht dann die Typbibliothek für intern referenzierte Typbibliotheken, die jeweils geladen und der übergeordneten Typbibliothek hinzugefügt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="490e9-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="490e9-130">Bevor eine Typbibliothek, auf die verwiesen wird, geladen werden kann, muss der Verweis Datei Pfad in einen vollständigen Dateipfad aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="490e9-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="490e9-131">Dies erfolgt über die [ResolveTypeLib-Methode](resolvetypelib-method.md) , die von der [ITypeLibResolver-Schnittstelle](itypelibresolver-interface.md)bereitgestellt wird, die im-Parameter übergeben wird `pTlbResolver` .</span><span class="sxs-lookup"><span data-stu-id="490e9-131">This is accomplished through the [ResolveTypeLib method](resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="490e9-132">Wenn der vollständige Dateipfad der Typbibliothek, auf die verwiesen wird, bekannt ist, `LoadTypeLibWithResolver` lädt die Funktion die Typbibliothek, auf die verwiesen wird, und fügt Sie der übergeordneten Typbibliothek hinzu</span><span class="sxs-lookup"><span data-stu-id="490e9-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="490e9-133">Nachdem die Funktion alle intern referenzierten Typbibliotheken aufgelöst und geladen hat, gibt Sie einen Verweis auf die vom Master aufgelöste Typbibliothek im- `pptlib` Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="490e9-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="490e9-134">Die- `LoadTypeLibWithResolver` Funktion wird in der Regel von der [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md)aufgerufen, die im-Parameter eine eigene interne [ITypeLibResolver-Schnittstellen](itypelibresolver-interface.md) Implementierung bereitstellt `pTlbResolver` .</span><span class="sxs-lookup"><span data-stu-id="490e9-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="490e9-135">Wenn Sie `LoadTypeLibWithResolver` direkt aufrufen, müssen Sie eine eigene [ITypeLibResolver-Schnittstellen](itypelibresolver-interface.md) Implementierung angeben.</span><span class="sxs-lookup"><span data-stu-id="490e9-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="490e9-136">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="490e9-136">Requirements</span></span>  

 <span data-ttu-id="490e9-137">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="490e9-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="490e9-138">**Header:** TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="490e9-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="490e9-139">**Bibliothek:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="490e9-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="490e9-140">**.NET Framework Version:** 3,5, 3,0, 2,0</span><span class="sxs-lookup"><span data-stu-id="490e9-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="490e9-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="490e9-141">See also</span></span>

- [<span data-ttu-id="490e9-142">Tlbexp-Hilfsfunktionen</span><span class="sxs-lookup"><span data-stu-id="490e9-142">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="490e9-143">LoadTypeLibEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="490e9-143">LoadTypeLibEx Function</span></span>](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
