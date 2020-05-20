---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: c35455fc679d79d56814a9c2f026ec395e944f24
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441720"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="2b4c5-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="2b4c5-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="2b4c5-103">Legt die Anfangs Methode fest, die den asynchronen Vorgang initiiert.</span><span class="sxs-lookup"><span data-stu-id="2b4c5-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b4c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b4c5-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b4c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b4c5-105">Parameters</span></span>  
  
|<span data-ttu-id="2b4c5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b4c5-106">Parameter</span></span>|<span data-ttu-id="2b4c5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2b4c5-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="2b4c5-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2b4c5-108">Return Value</span></span>  
 <span data-ttu-id="2b4c5-109">Gibt `HRESULT` zurück.</span><span class="sxs-lookup"><span data-stu-id="2b4c5-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b4c5-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b4c5-110">Requirements</span></span>  
 <span data-ttu-id="2b4c5-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="2b4c5-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b4c5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b4c5-112">See also</span></span>

- [<span data-ttu-id="2b4c5-113">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b4c5-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
