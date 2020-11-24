---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: 4ac2cccfb17d82d8c62ad7db89161aa794825ae5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678276"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="b0599-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode</span><span class="sxs-lookup"><span data-stu-id="b0599-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>

<span data-ttu-id="b0599-103">Funktioniert genauso wie die [GetDebugInfo-Methode](isymunmanagedwriter-getdebuginfo-method.md) , mit der Ausnahme, dass die Pfad Zeichenfolge nach dem abschließenden NULL-Zeichen mit Nullen aufgefüllt wird, damit die Zeichen folgen Daten eine festgelegte Größe von haben `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="b0599-103">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="b0599-104">Padding wird nur angegeben, wenn die Länge der Pfad Zeichenfolge selbst kleiner als ist `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="b0599-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="b0599-105">Dadurch wird das Schreiben von Tools erleichtert, die PE-Dateien unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="b0599-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0599-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0599-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0599-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="b0599-107">Parameters</span></span>  
  
|<span data-ttu-id="b0599-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="b0599-108">Parameter</span></span>|<span data-ttu-id="b0599-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b0599-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="b0599-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b0599-110">Return Value</span></span>  

 <span data-ttu-id="b0599-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="b0599-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0599-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b0599-112">Requirements</span></span>  

 <span data-ttu-id="b0599-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="b0599-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0599-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0599-114">See also</span></span>

- [<span data-ttu-id="b0599-115">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b0599-115">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)
