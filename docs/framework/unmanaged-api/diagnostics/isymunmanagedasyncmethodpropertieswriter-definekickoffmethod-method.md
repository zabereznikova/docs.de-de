---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24560ed4b0bb7ca04d5859280baa594fbb2e4097
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473465"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="dead5-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="dead5-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="dead5-103">Legt die Start-Methode, die den asynchronen Vorgang initiiert.</span><span class="sxs-lookup"><span data-stu-id="dead5-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dead5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dead5-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dead5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dead5-105">Parameters</span></span>  
  
|<span data-ttu-id="dead5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="dead5-106">Parameter</span></span>|<span data-ttu-id="dead5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dead5-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="dead5-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dead5-108">Return Value</span></span>  
 <span data-ttu-id="dead5-109">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="dead5-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dead5-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dead5-110">Requirements</span></span>  
 <span data-ttu-id="dead5-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dead5-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dead5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dead5-112">See also</span></span>
- [<span data-ttu-id="dead5-113">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dead5-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
