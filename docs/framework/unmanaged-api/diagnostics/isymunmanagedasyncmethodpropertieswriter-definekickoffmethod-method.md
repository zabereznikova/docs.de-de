---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce3c135e031d0c8425e990811fedc40f4ec45243
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59226611"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="c3b54-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="c3b54-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="c3b54-103">Legt die Start-Methode, die den asynchronen Vorgang initiiert.</span><span class="sxs-lookup"><span data-stu-id="c3b54-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b54-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3b54-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3b54-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c3b54-105">Parameters</span></span>  
  
|<span data-ttu-id="c3b54-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c3b54-106">Parameter</span></span>|<span data-ttu-id="c3b54-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3b54-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="c3b54-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c3b54-108">Return Value</span></span>  
 <span data-ttu-id="c3b54-109">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="c3b54-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3b54-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c3b54-110">Requirements</span></span>  
 <span data-ttu-id="c3b54-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c3b54-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b54-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3b54-112">See also</span></span>

- [<span data-ttu-id="c3b54-113">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c3b54-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
