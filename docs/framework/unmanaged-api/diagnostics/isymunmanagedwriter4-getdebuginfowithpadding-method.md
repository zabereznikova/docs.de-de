---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: cfc6c22558cee780823c8cca0c36b883147e9496
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614642"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="10c93-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode</span><span class="sxs-lookup"><span data-stu-id="10c93-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="10c93-103">Funktioniert genauso wie die [GetDebugInfo-Methode](isymunmanagedwriter-getdebuginfo-method.md) , mit der Ausnahme, dass die Pfad Zeichenfolge nach dem abschließenden NULL-Zeichen mit Nullen aufgefüllt wird, damit die Zeichen folgen Daten eine festgelegte Größe von haben `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="10c93-103">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="10c93-104">Padding wird nur angegeben, wenn die Länge der Pfad Zeichenfolge selbst kleiner als ist `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="10c93-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="10c93-105">Dadurch wird das Schreiben von Tools erleichtert, die PE-Dateien unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="10c93-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10c93-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="10c93-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10c93-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="10c93-107">Parameters</span></span>  
  
|<span data-ttu-id="10c93-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="10c93-108">Parameter</span></span>|<span data-ttu-id="10c93-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="10c93-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="10c93-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="10c93-110">Return Value</span></span>  
 <span data-ttu-id="10c93-111">Gibt `HRESULT` zurück.</span><span class="sxs-lookup"><span data-stu-id="10c93-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10c93-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10c93-112">Requirements</span></span>  
 <span data-ttu-id="10c93-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="10c93-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10c93-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10c93-114">See also</span></span>

- [<span data-ttu-id="10c93-115">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10c93-115">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)
