---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f85486370d567ceb1506c41f6aa7c4f3a1929941
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="3be00-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode</span><span class="sxs-lookup"><span data-stu-id="3be00-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="3be00-103">Funktioniert genauso wie [GetDebugInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) mit dem Unterschied, dass die Pfadzeichenfolge mit Nullen nach dem das abschließende Nullzeichen, den Zeichenfolgendaten eine feste Größe von Stellen aufgefüllt wird `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="3be00-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="3be00-104">Auffüllung wird nur ausgegeben, wenn die Zeichenfolge Pfadlänge selbst ist kleiner als `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="3be00-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="3be00-105">Dies erleichtert es, Tools, Unterschied PE-Dateien zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="3be00-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3be00-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3be00-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3be00-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="3be00-107">Parameters</span></span>  
  
|<span data-ttu-id="3be00-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="3be00-108">Parameter</span></span>|<span data-ttu-id="3be00-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3be00-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="3be00-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3be00-110">Return Value</span></span>  
 <span data-ttu-id="3be00-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="3be00-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3be00-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3be00-112">Requirements</span></span>  
 <span data-ttu-id="3be00-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3be00-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3be00-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3be00-114">See Also</span></span>  
 [<span data-ttu-id="3be00-115">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3be00-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
