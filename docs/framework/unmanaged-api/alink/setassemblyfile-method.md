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
ms.openlocfilehash: 006360203518f74adb964634af52505a71d51473
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587098"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="8312e-102">SetAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="8312e-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="8312e-103">Weist den Namen der Assembly, die erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8312e-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="8312e-104">Nicht für die Verwendung bei der Produktion ungebundener Modules.</span><span class="sxs-lookup"><span data-stu-id="8312e-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8312e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8312e-105">Syntax</span></span>  
  
```  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8312e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8312e-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="8312e-107">Voll gekennzeichnete Name der Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="8312e-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="8312e-108">Zeiger auf [IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="8312e-108">Pointer to [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="8312e-109">Flags gemäß [AssemblyFlags-Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="8312e-109">Flags as defined in [AssemblyFlags Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="8312e-110">Zeiger auf die ID der resultierenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="8312e-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8312e-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8312e-111">Return Value</span></span>  
 <span data-ttu-id="8312e-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="8312e-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8312e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8312e-113">Requirements</span></span>  
 <span data-ttu-id="8312e-114">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="8312e-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8312e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8312e-115">See also</span></span>
- [<span data-ttu-id="8312e-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8312e-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="8312e-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8312e-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="8312e-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="8312e-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
