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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aba11ccd61b65d2a779b39db8e0e082cf4d4015b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787217"
---
# <a name="setassemblyfile2-method"></a><span data-ttu-id="86cb5-102">SetAssemblyFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="86cb5-102">SetAssemblyFile2 Method</span></span>
<span data-ttu-id="86cb5-103">Legt den Namen der Optionen und für eine neue Assembly fest.</span><span class="sxs-lookup"><span data-stu-id="86cb5-103">Sets the name of and options for a new assembly.</span></span> <span data-ttu-id="86cb5-104">Rufen Sie diese Methode nicht auf, wenn Sie ungebundene Module entwickeln.</span><span class="sxs-lookup"><span data-stu-id="86cb5-104">Do not call this method when you produce unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86cb5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="86cb5-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile2(  
    LPCWSTR pszFilename,  
    IMetaDataEmit2* pEmitter,  
    AssemblyFlags   afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="86cb5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="86cb5-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="86cb5-107">Der Name der Manifest-Datei.</span><span class="sxs-lookup"><span data-stu-id="86cb5-107">Name of manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="86cb5-108">[IMetaDataEmit2 Schnittstellen](../metadata/imetadataemit2-interface.md) Schnittstelle für diese Datei.</span><span class="sxs-lookup"><span data-stu-id="86cb5-108">[IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface for this file.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="86cb5-109">Optionen, die durch die [AssemblyFlags-Enumeration](../metadata/assemblyflags-enumeration.md)dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="86cb5-109">Options represented by [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="86cb5-110">Empfängt eine eindeutige ID für die Assembly, die erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="86cb5-110">Receives unique ID for the assembly being constructed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86cb5-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="86cb5-111">Return Value</span></span>  
 <span data-ttu-id="86cb5-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="86cb5-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86cb5-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="86cb5-113">Requirements</span></span>  
 <span data-ttu-id="86cb5-114">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="86cb5-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86cb5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86cb5-115">See also</span></span>

- [<span data-ttu-id="86cb5-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="86cb5-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="86cb5-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="86cb5-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="86cb5-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="86cb5-118">ALink API</span></span>](index.md)
