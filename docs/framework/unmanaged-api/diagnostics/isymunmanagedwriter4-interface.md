---
title: ISymUnmanagedWriter4-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5732cc08512df25a14cc8ea9dcaa03c56207dde
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962331"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="3a8ed-102">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a8ed-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="3a8ed-103">ISymUnmanagedWriter4-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3a8ed-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a8ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a8ed-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="3a8ed-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3a8ed-105">Methods</span></span>  
 <span data-ttu-id="3a8ed-106">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="3a8ed-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="3a8ed-107">Methode</span><span class="sxs-lookup"><span data-stu-id="3a8ed-107">Method</span></span>|<span data-ttu-id="3a8ed-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a8ed-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3a8ed-109">GetDebugInfoWithPadding-Methode</span><span class="sxs-lookup"><span data-stu-id="3a8ed-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="3a8ed-110">Funktioniert genauso wie [GetDebugInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) mit dem Unterschied, dass die Path-Zeichenfolge mit Nullen nach dem das abschließende Nullzeichen, um den Zeichenfolgendaten eine feste Größe von machen aufgefüllt wird `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="3a8ed-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="3a8ed-111">Auffüllung wird nur ausgegeben, wenn die Länge der Zeichenfolge Pfad selbst ist kleiner als `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="3a8ed-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="3a8ed-112">Dies erleichtert es, Tools, Unterschied PE-Dateien zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="3a8ed-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3a8ed-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3a8ed-113">Requirements</span></span>  
 <span data-ttu-id="3a8ed-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3a8ed-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a8ed-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a8ed-115">See also</span></span>

- [<span data-ttu-id="3a8ed-116">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3a8ed-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="3a8ed-117">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a8ed-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
