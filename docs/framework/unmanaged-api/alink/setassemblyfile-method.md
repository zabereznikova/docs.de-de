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
ms.openlocfilehash: 1e557cc0da7bc684843ae3969242ffb84d811c44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405345"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="b3766-102">SetAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="b3766-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="b3766-103">Weist den Namen der Assembly erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b3766-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="b3766-104">Nicht zur Verwendung beim Erstellen von ungebundener Modules.</span><span class="sxs-lookup"><span data-stu-id="b3766-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3766-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3766-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3766-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b3766-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="b3766-107">Vollständig qualifizierte Name der Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="b3766-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="b3766-108">Zeiger auf [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b3766-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="b3766-109">Flags gemäß [AssemblyFlags-Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="b3766-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="b3766-110">Ein Zeiger auf die ID des sich ergebenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="b3766-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3766-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b3766-111">Return Value</span></span>  
 <span data-ttu-id="b3766-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b3766-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3766-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3766-113">Requirements</span></span>  
 <span data-ttu-id="b3766-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="b3766-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3766-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3766-115">See Also</span></span>  
 [<span data-ttu-id="b3766-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3766-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b3766-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3766-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b3766-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="b3766-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
