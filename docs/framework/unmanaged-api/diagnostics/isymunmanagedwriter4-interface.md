---
title: ISymUnmanagedWriter4-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7ab7f06ba280675ca8349500e766364d30f9349
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="f0758-102">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0758-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="f0758-103">ISymUnmanagedWriter4-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f0758-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0758-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0758-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="f0758-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f0758-105">Methods</span></span>  
 <span data-ttu-id="f0758-106">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="f0758-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="f0758-107">Methode</span><span class="sxs-lookup"><span data-stu-id="f0758-107">Method</span></span>|<span data-ttu-id="f0758-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0758-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0758-109">GetDebugInfoWithPadding-Methode</span><span class="sxs-lookup"><span data-stu-id="f0758-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="f0758-110">Funktioniert genauso wie [GetDebugInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) mit dem Unterschied, dass die Pfadzeichenfolge mit Nullen nach dem das abschließende Nullzeichen, den Zeichenfolgendaten eine feste Größe von Stellen aufgefüllt wird `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="f0758-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="f0758-111">Auffüllung wird nur ausgegeben, wenn die Zeichenfolge Pfadlänge selbst ist kleiner als `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="f0758-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="f0758-112">Dies erleichtert es, Tools, Unterschied PE-Dateien zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="f0758-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0758-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0758-113">Requirements</span></span>  
 <span data-ttu-id="f0758-114">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f0758-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0758-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0758-115">See Also</span></span>  
 [<span data-ttu-id="f0758-116">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f0758-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="f0758-117">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0758-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
