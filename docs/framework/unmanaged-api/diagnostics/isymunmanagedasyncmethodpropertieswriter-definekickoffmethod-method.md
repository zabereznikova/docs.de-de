---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a476d92486d7f2523dfbcc8b25e9c11e26c55f2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425614"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="9eec2-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="9eec2-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="9eec2-103">Legt die Start-Methode, die den asynchronen Vorgang initiiert.</span><span class="sxs-lookup"><span data-stu-id="9eec2-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eec2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9eec2-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9eec2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9eec2-105">Parameters</span></span>  
  
|<span data-ttu-id="9eec2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9eec2-106">Parameter</span></span>|<span data-ttu-id="9eec2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9eec2-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="9eec2-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9eec2-108">Return Value</span></span>  
 <span data-ttu-id="9eec2-109">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="9eec2-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9eec2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9eec2-110">Requirements</span></span>  
 <span data-ttu-id="9eec2-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9eec2-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eec2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9eec2-112">See Also</span></span>  
 [<span data-ttu-id="9eec2-113">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9eec2-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
