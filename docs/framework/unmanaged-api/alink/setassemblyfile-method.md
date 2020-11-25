---
title: SetAssemblyFile-Methode
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 45eed17b91f70d4188d1d89fc91a41455f3e845b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732644"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="7be51-102">SetAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="7be51-102">SetAssemblyFile Method</span></span>

<span data-ttu-id="7be51-103">Weist den Namen der Assembly zu, die erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7be51-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="7be51-104">Nicht für die Verwendung beim Erstellen von ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="7be51-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be51-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7be51-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7be51-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7be51-106">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="7be51-107">Der voll qualifizierte Name der Manifest-Datei.</span><span class="sxs-lookup"><span data-stu-id="7be51-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="7be51-108">Zeiger auf die [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7be51-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="7be51-109">Flags, wie in [AssemblyFlags-Enumeration](../metadata/assemblyflags-enumeration.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="7be51-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="7be51-110">Zeiger auf die ID der resultierenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="7be51-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7be51-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7be51-111">Return Value</span></span>  

 <span data-ttu-id="7be51-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="7be51-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7be51-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7be51-113">Requirements</span></span>  

 <span data-ttu-id="7be51-114">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="7be51-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be51-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7be51-115">See also</span></span>

- [<span data-ttu-id="7be51-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7be51-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7be51-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7be51-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7be51-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="7be51-118">ALink API</span></span>](index.md)
