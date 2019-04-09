---
title: ISymUnmanagedWriter2-Schnittstelle
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97df6d6ec9a446e89eef8a9f8a5e5e8ddc85c0f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127399"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="12118-102">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12118-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="12118-103">Stellt einen Symbolwriter dar und bietet Methoden, um Dokumente, Sequenzpunkte, lexikalischen Gültigkeitsbereiche und Variablen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="12118-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="12118-104">Diese Schnittstelle erweitert die [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="12118-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="12118-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="12118-105">Methods</span></span>  
  
|<span data-ttu-id="12118-106">Methode</span><span class="sxs-lookup"><span data-stu-id="12118-106">Method</span></span>|<span data-ttu-id="12118-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12118-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12118-108">DefineConstant2-Methode</span><span class="sxs-lookup"><span data-stu-id="12118-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="12118-109">Definiert einen Namen für einen konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="12118-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="12118-110">DefineGlobalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="12118-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="12118-111">Definiert eine einzelne globale Variable.</span><span class="sxs-lookup"><span data-stu-id="12118-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="12118-112">DefineLocalVariable2-Methode</span><span class="sxs-lookup"><span data-stu-id="12118-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="12118-113">Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="12118-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12118-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="12118-114">Requirements</span></span>  
 <span data-ttu-id="12118-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="12118-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12118-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12118-116">See also</span></span>

- [<span data-ttu-id="12118-117">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="12118-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="12118-118">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12118-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="12118-119">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12118-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
