---
title: ISymUnmanagedWriter2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 98461cd2c2bc26d78f3f3f747b95d46576ba01e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="e4c89-102">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4c89-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="e4c89-103">Stellt einen Symbolwriter dar und bietet Methoden zum Definieren von Dokumenten, Sequenzpunkte lexikalischen Gültigkeitsbereiche und Variablen.</span><span class="sxs-lookup"><span data-stu-id="e4c89-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="e4c89-104">Diese Schnittstelle erweitert die [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e4c89-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e4c89-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e4c89-105">Methods</span></span>  
  
|<span data-ttu-id="e4c89-106">Methode</span><span class="sxs-lookup"><span data-stu-id="e4c89-106">Method</span></span>|<span data-ttu-id="e4c89-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4c89-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e4c89-108">DefineConstant2-Methode</span><span class="sxs-lookup"><span data-stu-id="e4c89-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="e4c89-109">Definiert einen Namen für einen konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="e4c89-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="e4c89-110">DefineGlobalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="e4c89-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="e4c89-111">Definiert eine einzelne globale Variable.</span><span class="sxs-lookup"><span data-stu-id="e4c89-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="e4c89-112">DefineLocalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="e4c89-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="e4c89-113">Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="e4c89-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e4c89-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4c89-114">Requirements</span></span>  
 <span data-ttu-id="e4c89-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e4c89-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4c89-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4c89-116">See Also</span></span>  
 [<span data-ttu-id="e4c89-117">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e4c89-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="e4c89-118">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4c89-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="e4c89-119">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4c89-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
