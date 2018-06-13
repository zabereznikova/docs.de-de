---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo-Methode
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ebd4bb1d674a27785ccbe5460a65fed764638ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435876"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="f3411-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="f3411-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="f3411-103">Definieren Sie eine Gruppe von asynchronen Vorgängen in der aktuellen Methode erwarten.</span><span class="sxs-lookup"><span data-stu-id="f3411-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="f3411-104">Jede Yield-Offset entspricht eine "await" return-Anweisung, einen potenziellen Rendite identifizieren.</span><span class="sxs-lookup"><span data-stu-id="f3411-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="f3411-105">Jede `breakpointMethod` / `breakpointOffset` Paar gibt an, in dem der asynchrone Vorgang fortgesetzt wird (das kann in eine andere Methode sein.</span><span class="sxs-lookup"><span data-stu-id="f3411-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume,(which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3411-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3411-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3411-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3411-107">Parameters</span></span>  
  
|<span data-ttu-id="f3411-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3411-108">Parameter</span></span>|<span data-ttu-id="f3411-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3411-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="f3411-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f3411-110">Return Value</span></span>  
 <span data-ttu-id="f3411-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="f3411-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3411-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3411-112">Requirements</span></span>  
 <span data-ttu-id="f3411-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f3411-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3411-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3411-114">See Also</span></span>  
 [<span data-ttu-id="f3411-115">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3411-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
