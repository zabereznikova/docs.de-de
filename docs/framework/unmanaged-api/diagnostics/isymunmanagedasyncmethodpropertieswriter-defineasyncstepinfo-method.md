---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo-Methode
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8305d0a562fd90e3fae32e372b663ca3942d2a4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080851"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="70d8d-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="70d8d-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="70d8d-103">Definieren Sie eine Gruppe von Async "await" Vorgänge in der aktuellen Methode.</span><span class="sxs-lookup"><span data-stu-id="70d8d-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="70d8d-104">Jede Offset "yield" entspricht einem "await" return-Anweisung, Identifizieren einer potenziellen "yield".</span><span class="sxs-lookup"><span data-stu-id="70d8d-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="70d8d-105">Jede `breakpointMethod` / `breakpointOffset` Paar gibt an, in dem der asynchrone Vorgang fortgesetzt, die in einer anderen Methode sein kann.</span><span class="sxs-lookup"><span data-stu-id="70d8d-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70d8d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="70d8d-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70d8d-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="70d8d-107">Parameters</span></span>  
  
|<span data-ttu-id="70d8d-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="70d8d-108">Parameter</span></span>|<span data-ttu-id="70d8d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70d8d-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="70d8d-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="70d8d-110">Return Value</span></span>  
 <span data-ttu-id="70d8d-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="70d8d-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70d8d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="70d8d-112">Requirements</span></span>  
 <span data-ttu-id="70d8d-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="70d8d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70d8d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70d8d-114">See also</span></span>

- [<span data-ttu-id="70d8d-115">ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70d8d-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
