---
title: GetResolutionScope-Methode
ms.date: 03/30/2017
api_name:
- IALink.GetResolutionScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetResolutionScope
helpviewer_keywords:
- GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type:
- apiref
ms.openlocfilehash: 6318890dd6f0259d8d6a7675380684a129c14c8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684673"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="fb2e5-102">GetResolutionScope-Methode</span><span class="sxs-lookup"><span data-stu-id="fb2e5-102">GetResolutionScope Method</span></span>

<span data-ttu-id="fb2e5-103">Ruft den Bereich eines angegebenen Typs ab.</span><span class="sxs-lookup"><span data-stu-id="fb2e5-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb2e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb2e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb2e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fb2e5-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="fb2e5-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="fb2e5-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="fb2e5-107">Die Datei, die einen Verweis benötigt.</span><span class="sxs-lookup"><span data-stu-id="fb2e5-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="fb2e5-108">Token der Datei, in der der Typ definiert ist, wird normalerweise mit der [ImportFile-Methode](importfile-method.md)abgerufen.</span><span class="sxs-lookup"><span data-stu-id="fb2e5-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="fb2e5-109">Empfängt die Assembly oder den Modul Verweis.</span><span class="sxs-lookup"><span data-stu-id="fb2e5-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb2e5-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fb2e5-110">Return Value</span></span>  

 <span data-ttu-id="fb2e5-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="fb2e5-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb2e5-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fb2e5-112">Requirements</span></span>  

 <span data-ttu-id="fb2e5-113">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="fb2e5-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2e5-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb2e5-114">See also</span></span>

- [<span data-ttu-id="fb2e5-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb2e5-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="fb2e5-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb2e5-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="fb2e5-117">ALink-API</span><span class="sxs-lookup"><span data-stu-id="fb2e5-117">ALink API</span></span>](index.md)
