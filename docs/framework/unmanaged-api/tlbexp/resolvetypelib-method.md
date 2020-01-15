---
title: ResolveTypeLib-Methode
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
ms.openlocfilehash: f0f6fe321f4d38129b6d70ce94a7ea8de8fff6c8
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935672"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="97af5-102">ResolveTypeLib-Methode</span><span class="sxs-lookup"><span data-stu-id="97af5-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="97af5-103">Löst den einfachen Namen einer Typbibliothek auf, indem der voll qualifizierte Pfad zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="97af5-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97af5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97af5-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97af5-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="97af5-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="97af5-106">in Ein [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , das den einfachen Namen der Typbibliothek enthält.</span><span class="sxs-lookup"><span data-stu-id="97af5-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="97af5-107">in Die GUID, die der Typbibliothek in der Registrierung zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="97af5-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="97af5-108">in Die Lokalisierungs-ID der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="97af5-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="97af5-109">in Die Hauptversionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="97af5-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="97af5-110">Bei Version *x. y*lautet die Hauptversionsnummer z. b. *x*.</span><span class="sxs-lookup"><span data-stu-id="97af5-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="97af5-111">in Die neben Versionsnummer der Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="97af5-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="97af5-112">Beispielsweise ist für Version *x. y*die neben Versionsnummer *y*.</span><span class="sxs-lookup"><span data-stu-id="97af5-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="97af5-113">in Ein [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) -Flag, das die Betriebsumgebung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="97af5-113">[in] A [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="97af5-114">Allgemeine Werte sind SYS_WIN32 und SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="97af5-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="97af5-115">vorgenommen Ein Zeiger auf einen [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) -Wert, der den vollständigen Pfad der Typbibliothek mit dem Namen im `bstrSimpleName`-Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="97af5-115">[out] A pointer to a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97af5-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97af5-116">Remarks</span></span>  
 <span data-ttu-id="97af5-117">Die `ResolveTypeLib`-Methode wird von der [LoadTypeLibWithResolver-Funktion](loadtypelibwithresolver-function.md) während der Verarbeitung von [Tlbexp. exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="97af5-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="97af5-118">Benutzerdefinierte Implementierungen dieser Schnittstelle müssen einen [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) -Wert zurückgeben, der den vollständigen Pfad der Typbibliothek mit dem Namen im `bstrSimpleName`-Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="97af5-118">Custom implementations of this interface must return a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97af5-119">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97af5-119">Requirements</span></span>  
 <span data-ttu-id="97af5-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97af5-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97af5-121">**Header:** TlbRef. idl, TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="97af5-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="97af5-122">**Bibliothek:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="97af5-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="97af5-123">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97af5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97af5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97af5-124">See also</span></span>

- [<span data-ttu-id="97af5-125">Tlbexp-Hilfsfunktionen</span><span class="sxs-lookup"><span data-stu-id="97af5-125">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="97af5-126">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="97af5-126">LoadTypeLibEx</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
