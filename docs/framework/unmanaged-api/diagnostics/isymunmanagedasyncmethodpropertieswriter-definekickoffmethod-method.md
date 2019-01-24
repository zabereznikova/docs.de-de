---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38b4564aeb3c8ed4674e755e5691bb0a9d417bca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624175"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="2d00b-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="2d00b-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="2d00b-103">Legt die Start-Methode, die den asynchronen Vorgang initiiert.</span><span class="sxs-lookup"><span data-stu-id="2d00b-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d00b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d00b-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d00b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d00b-105">Parameters</span></span>  
  
|<span data-ttu-id="2d00b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d00b-106">Parameter</span></span>|<span data-ttu-id="2d00b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d00b-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="2d00b-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2d00b-108">Return Value</span></span>  
 <span data-ttu-id="2d00b-109">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="2d00b-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d00b-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d00b-110">Requirements</span></span>  
 <span data-ttu-id="2d00b-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2d00b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d00b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d00b-112">See also</span></span>
- [<span data-ttu-id="2d00b-113">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d00b-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
