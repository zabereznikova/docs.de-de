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
ms.openlocfilehash: 4b0de5f9759491f1303edc978b1548e91214daf8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733749"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="5f140-102">SetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="5f140-102">SetAssemblyProps Method</span></span>

<span data-ttu-id="5f140-103">Weist Eigenschaften auf Assemblyebene zu.</span><span class="sxs-lookup"><span data-stu-id="5f140-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f140-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f140-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f140-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f140-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="5f140-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="5f140-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="5f140-107">Eine Datei, die die Eigenschaft definiert.</span><span class="sxs-lookup"><span data-stu-id="5f140-107">File that defines the property.</span></span> <span data-ttu-id="5f140-108">Kann NULL sein, wenn `AssemblyID` kein ungebundenes NetModule angibt.</span><span class="sxs-lookup"><span data-stu-id="5f140-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="5f140-109">Gibt die Option an, die geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5f140-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="5f140-110">Neuer Wert der Option.</span><span class="sxs-lookup"><span data-stu-id="5f140-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f140-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5f140-111">Return Value</span></span>  

 <span data-ttu-id="5f140-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="5f140-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f140-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5f140-113">Requirements</span></span>  

 <span data-ttu-id="5f140-114">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="5f140-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f140-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f140-115">See also</span></span>

- [<span data-ttu-id="5f140-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f140-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5f140-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f140-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5f140-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="5f140-118">ALink API</span></span>](index.md)
