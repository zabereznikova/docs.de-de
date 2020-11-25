---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo-Methode
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: f8c77e44183fd92704aa91ca1cfd7e3fa68aa27f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719618"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="f6ae4-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="f6ae4-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>

<span data-ttu-id="f6ae4-103">Definieren Sie eine Gruppe von asynchronen warte Vorgängen in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="f6ae4-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="f6ae4-104">Jeder yield-Offset entspricht der Return-Anweisung, die eine mögliche Rendite identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f6ae4-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="f6ae4-105">Jedes `breakpointMethod` / `breakpointOffset` paar teilt uns mit, wo der asynchrone Vorgang fortgesetzt wird, der sich in einer anderen Methode befinden könnte.</span><span class="sxs-lookup"><span data-stu-id="f6ae4-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6ae4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6ae4-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6ae4-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6ae4-107">Parameters</span></span>  
  
|<span data-ttu-id="f6ae4-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6ae4-108">Parameter</span></span>|<span data-ttu-id="f6ae4-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f6ae4-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="f6ae4-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f6ae4-110">Return Value</span></span>  

 <span data-ttu-id="f6ae4-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="f6ae4-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6ae4-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f6ae4-112">Requirements</span></span>  

 <span data-ttu-id="f6ae4-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="f6ae4-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ae4-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6ae4-114">See also</span></span>

- [<span data-ttu-id="f6ae4-115">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6ae4-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
