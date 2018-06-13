---
title: SetAssemblyProps-Methode
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aed553a3a8d54b5229a122e76b61e3e58d4af3c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401965"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="45726-102">SetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="45726-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="45726-103">Weist Eigenschaften auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="45726-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45726-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45726-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45726-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45726-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="45726-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="45726-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="45726-107">Datei, die die Eigenschaft definiert.</span><span class="sxs-lookup"><span data-stu-id="45726-107">File that defines the property.</span></span> <span data-ttu-id="45726-108">Kann NULL sein, wenn `AssemblyID` einen ungebundenen NETMODULE-Datei nicht an.</span><span class="sxs-lookup"><span data-stu-id="45726-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="45726-109">Gibt an, die Möglichkeit zum Ändern.</span><span class="sxs-lookup"><span data-stu-id="45726-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="45726-110">Neuer Wert der Option.</span><span class="sxs-lookup"><span data-stu-id="45726-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45726-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="45726-111">Return Value</span></span>  
 <span data-ttu-id="45726-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="45726-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45726-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45726-113">Requirements</span></span>  
 <span data-ttu-id="45726-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="45726-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45726-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45726-115">See Also</span></span>  
 [<span data-ttu-id="45726-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45726-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="45726-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45726-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="45726-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="45726-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
