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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a19762cbec91871d7af617957896e4ee34944fba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132709"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="3256c-102">SetAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="3256c-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="3256c-103">Weist den Namen der Assembly, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3256c-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="3256c-104">Nicht für die Verwendung bei der Produktion ungebundener Modules.</span><span class="sxs-lookup"><span data-stu-id="3256c-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3256c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3256c-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3256c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3256c-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="3256c-107">Voll gekennzeichnete Name der Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="3256c-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="3256c-108">Zeiger auf [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3256c-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="3256c-109">Flags gemäß [AssemblyFlags-Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="3256c-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="3256c-110">Zeiger auf die ID der resultierenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="3256c-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3256c-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3256c-111">Return Value</span></span>  
 <span data-ttu-id="3256c-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="3256c-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3256c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3256c-113">Requirements</span></span>  
 <span data-ttu-id="3256c-114">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="3256c-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3256c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3256c-115">See also</span></span>

- [<span data-ttu-id="3256c-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3256c-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3256c-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3256c-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3256c-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="3256c-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
