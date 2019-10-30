---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: 274bf79175bda9e880b1ef3cf8f125a017ad0734
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121661"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="c190a-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode</span><span class="sxs-lookup"><span data-stu-id="c190a-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="c190a-103">Funktioniert genauso wie die [GetDebugInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) , mit der Ausnahme, dass die Pfad Zeichenfolge nach dem abschließenden NULL-Zeichen mit Nullen aufgefüllt wird, damit die Zeichen folgen Daten eine festgelegte Größe von `MAX_PATH`werden.</span><span class="sxs-lookup"><span data-stu-id="c190a-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="c190a-104">Padding wird nur angegeben, wenn die Länge der Pfad Zeichenfolge selbst kleiner als `MAX_PATH`ist.</span><span class="sxs-lookup"><span data-stu-id="c190a-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="c190a-105">Dadurch wird das Schreiben von Tools erleichtert, die PE-Dateien unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c190a-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c190a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c190a-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c190a-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="c190a-107">Parameters</span></span>  
  
|<span data-ttu-id="c190a-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="c190a-108">Parameter</span></span>|<span data-ttu-id="c190a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c190a-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="c190a-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c190a-110">Return Value</span></span>  
 <span data-ttu-id="c190a-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="c190a-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c190a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c190a-112">Requirements</span></span>  
 <span data-ttu-id="c190a-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="c190a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c190a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c190a-114">See also</span></span>

- [<span data-ttu-id="c190a-115">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c190a-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
