---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: 418a77855d1cb34a07f5957059b5a6f5a106c321
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707086"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="41749-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="41749-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>

<span data-ttu-id="41749-103">Legt die Anfangs Methode fest, die den asynchronen Vorgang initiiert.</span><span class="sxs-lookup"><span data-stu-id="41749-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41749-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41749-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41749-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="41749-105">Parameters</span></span>  
  
|<span data-ttu-id="41749-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="41749-106">Parameter</span></span>|<span data-ttu-id="41749-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="41749-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="41749-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="41749-108">Return Value</span></span>  

 <span data-ttu-id="41749-109">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="41749-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41749-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="41749-110">Requirements</span></span>  

 <span data-ttu-id="41749-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="41749-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41749-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41749-112">See also</span></span>

- [<span data-ttu-id="41749-113">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41749-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
