---
title: PreCloseAssembly-Methode
ms.date: 03/30/2017
api_name:
- IALink.PreCloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- PreCloseAssembly
helpviewer_keywords:
- PreCloseAssembly method
ms.assetid: 6d23ac54-15ea-4027-a172-9ebef43e8f56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d4cf862ae3676b85a7fc3f09a4f5794e01284737
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787231"
---
# <a name="precloseassembly-method"></a><span data-ttu-id="68fe5-102">PreCloseAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="68fe5-102">PreCloseAssembly Method</span></span>
<span data-ttu-id="68fe5-103">Schließt die Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="68fe5-103">Closes the assembly file.</span></span> <span data-ttu-id="68fe5-104">Ruft diese Methode auf, nachdem alle anderen Dateien, jedoch vor dem Schließen der Assemblydatei geschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="68fe5-104">Call this method after closing all other files, but before closing the assembly file.</span></span> <span data-ttu-id="68fe5-105">Diese Methode darf nicht für ungebundene Module aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="68fe5-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68fe5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="68fe5-106">Syntax</span></span>  
  
```cpp  
HRESULT PreCloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="68fe5-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="68fe5-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="68fe5-108">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="68fe5-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68fe5-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="68fe5-109">Return Value</span></span>  
 <span data-ttu-id="68fe5-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="68fe5-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68fe5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68fe5-111">Requirements</span></span>  
 <span data-ttu-id="68fe5-112">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="68fe5-112">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68fe5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68fe5-113">See also</span></span>

- [<span data-ttu-id="68fe5-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68fe5-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="68fe5-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68fe5-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="68fe5-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="68fe5-116">ALink API</span></span>](index.md)
