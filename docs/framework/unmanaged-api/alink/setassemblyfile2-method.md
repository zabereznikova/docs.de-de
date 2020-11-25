---
title: SetAssemblyFile2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.SetAssemblyFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile2
helpviewer_keywords:
- SetAssemblyFile2 method
ms.assetid: eedb9125-1ef1-4000-abfc-7de86e5a1f17
topic_type:
- apiref
ms.openlocfilehash: 131f5d951e524ef48f2cfe1e3e88ef80ac21c452
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703680"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="be251-102">SetAssemblyFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="be251-102">SetAssemblyFile2 Method</span></span>

<span data-ttu-id="be251-103">Legt den Namen der Optionen und für eine neue Assembly fest.</span><span class="sxs-lookup"><span data-stu-id="be251-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="be251-104">Rufen Sie diese Methode nicht auf, wenn Sie ungebundene Module entwickeln.</span><span class="sxs-lookup"><span data-stu-id="be251-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be251-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="be251-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="be251-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="be251-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="be251-107">Der Name der Manifest-Datei.</span><span class="sxs-lookup"><span data-stu-id="be251-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="be251-108">[IMetaDataEmit2 Schnittstellen](../metadata/imetadataemit2-interface.md) Schnittstelle für diese Datei.</span><span class="sxs-lookup"><span data-stu-id="be251-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="be251-109">Optionen, die durch die [AssemblyFlags-Enumeration](../metadata/assemblyflags-enumeration.md)dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="be251-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="be251-110">Empfängt eine eindeutige ID für die Assembly, die erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="be251-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be251-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="be251-111">Return Value</span></span>  

 <span data-ttu-id="be251-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="be251-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be251-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="be251-113">Requirements</span></span>  

 <span data-ttu-id="be251-114">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="be251-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be251-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be251-115">See also</span></span>

- [<span data-ttu-id="be251-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be251-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="be251-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be251-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="be251-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="be251-118">ALink API</span></span>](index.md)
