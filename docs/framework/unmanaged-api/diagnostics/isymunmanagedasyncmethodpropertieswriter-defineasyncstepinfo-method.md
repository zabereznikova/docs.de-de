---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo-Methode
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: 59e3a95a4d2573263600da60b4f852caa361138e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129198"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="e89f8-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="e89f8-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="e89f8-103">Definieren Sie eine Gruppe von asynchronen warte Vorgängen in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="e89f8-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="e89f8-104">Jeder yield-Offset entspricht der Return-Anweisung, die eine mögliche Rendite identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e89f8-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="e89f8-105">Jede `breakpointMethod`/`breakpointOffset` paar teilt uns mit, wo der asynchrone Vorgang fortgesetzt wird, der sich in einer anderen Methode befinden könnte.</span><span class="sxs-lookup"><span data-stu-id="e89f8-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e89f8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e89f8-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e89f8-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="e89f8-107">Parameters</span></span>  
  
|<span data-ttu-id="e89f8-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="e89f8-108">Parameter</span></span>|<span data-ttu-id="e89f8-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e89f8-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="e89f8-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e89f8-110">Return Value</span></span>  
 <span data-ttu-id="e89f8-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="e89f8-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e89f8-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e89f8-112">Requirements</span></span>  
 <span data-ttu-id="e89f8-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="e89f8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e89f8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e89f8-114">See also</span></span>

- [<span data-ttu-id="e89f8-115">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e89f8-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
