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
ms.openlocfilehash: 4f710ef9741869a2b4fd8473ed3ecf379cfcc56d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445587"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="8373f-102">SetAssemblyFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="8373f-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="8373f-103">Legt den Namen der Optionen und für eine neue Assembly fest.</span><span class="sxs-lookup"><span data-stu-id="8373f-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="8373f-104">Rufen Sie diese Methode nicht auf, wenn Sie ungebundene Module entwickeln.</span><span class="sxs-lookup"><span data-stu-id="8373f-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8373f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8373f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="8373f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8373f-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="8373f-107">Der Name der Manifest-Datei.</span><span class="sxs-lookup"><span data-stu-id="8373f-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="8373f-108">[IMetaDataEmit2 Schnittstellen](../metadata/imetadataemit2-interface.md) Schnittstelle für diese Datei.</span><span class="sxs-lookup"><span data-stu-id="8373f-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="8373f-109">Optionen, die durch die [AssemblyFlags-Enumeration](../metadata/assemblyflags-enumeration.md)dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8373f-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="8373f-110">Empfängt eine eindeutige ID für die Assembly, die erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="8373f-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8373f-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8373f-111">Return Value</span></span>  
 <span data-ttu-id="8373f-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="8373f-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8373f-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8373f-113">Requirements</span></span>  
 <span data-ttu-id="8373f-114">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="8373f-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8373f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8373f-115">See also</span></span>

- [<span data-ttu-id="8373f-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8373f-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="8373f-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8373f-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="8373f-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="8373f-118">ALink API</span></span>](index.md)
