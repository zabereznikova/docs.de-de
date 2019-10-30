---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: ccf1287a1b0218e7f2560e1afbb0930c93b43263
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129176"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="1183f-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="1183f-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="1183f-103">Legt die Anfangs Methode fest, die den asynchronen Vorgang initiiert.</span><span class="sxs-lookup"><span data-stu-id="1183f-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1183f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1183f-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1183f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1183f-105">Parameters</span></span>  
  
|<span data-ttu-id="1183f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1183f-106">Parameter</span></span>|<span data-ttu-id="1183f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1183f-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="1183f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1183f-108">Return Value</span></span>  
 <span data-ttu-id="1183f-109">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="1183f-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1183f-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1183f-110">Requirements</span></span>  
 <span data-ttu-id="1183f-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="1183f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1183f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1183f-112">See also</span></span>

- [<span data-ttu-id="1183f-113">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1183f-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
