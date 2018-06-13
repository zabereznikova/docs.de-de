---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a703c7c8adf5d770ea74f8ed869568978f3b42f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428624"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="58370-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode</span><span class="sxs-lookup"><span data-stu-id="58370-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="58370-103">Funktioniert genauso wie [GetDebugInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) mit dem Unterschied, dass die Pfadzeichenfolge mit Nullen nach dem das abschließende Nullzeichen, den Zeichenfolgendaten eine feste Größe von Stellen aufgefüllt wird `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="58370-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="58370-104">Auffüllung wird nur ausgegeben, wenn die Zeichenfolge Pfadlänge selbst ist kleiner als `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="58370-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="58370-105">Dies erleichtert es, Tools, Unterschied PE-Dateien zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="58370-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58370-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="58370-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58370-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="58370-107">Parameters</span></span>  
  
|<span data-ttu-id="58370-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="58370-108">Parameter</span></span>|<span data-ttu-id="58370-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58370-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="58370-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="58370-110">Return Value</span></span>  
 <span data-ttu-id="58370-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="58370-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58370-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58370-112">Requirements</span></span>  
 <span data-ttu-id="58370-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="58370-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58370-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58370-114">See Also</span></span>  
 [<span data-ttu-id="58370-115">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58370-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
