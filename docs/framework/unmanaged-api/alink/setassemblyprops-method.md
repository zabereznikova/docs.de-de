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
ms.openlocfilehash: 180eb1a3129cfcd96668ecfee11947c15c5e0915
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70776913"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="c1f79-102">SetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="c1f79-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="c1f79-103">Weist Eigenschaften auf Assemblyebene zu.</span><span class="sxs-lookup"><span data-stu-id="c1f79-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1f79-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1f79-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1f79-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c1f79-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c1f79-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="c1f79-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="c1f79-107">Eine Datei, die die Eigenschaft definiert.</span><span class="sxs-lookup"><span data-stu-id="c1f79-107">File that defines the property.</span></span> <span data-ttu-id="c1f79-108">Kann NULL sein, `AssemblyID` wenn kein ungebundenes NetModule angibt.</span><span class="sxs-lookup"><span data-stu-id="c1f79-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="c1f79-109">Gibt die Option an, die geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c1f79-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="c1f79-110">Neuer Wert der Option.</span><span class="sxs-lookup"><span data-stu-id="c1f79-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1f79-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c1f79-111">Return Value</span></span>  
 <span data-ttu-id="c1f79-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="c1f79-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1f79-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c1f79-113">Requirements</span></span>  
 <span data-ttu-id="c1f79-114">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="c1f79-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1f79-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1f79-115">See also</span></span>

- [<span data-ttu-id="c1f79-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1f79-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c1f79-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1f79-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c1f79-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="c1f79-118">ALink API</span></span>](index.md)
