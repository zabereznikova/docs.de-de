---
title: ISymUnmanagedWriter3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e26d79a5b597b8585f2fffd7f3945f00832ca134
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138450"
---
# <a name="isymunmanagedwriter3-interface"></a><span data-ttu-id="d45bb-102">ISymUnmanagedWriter3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d45bb-102">ISymUnmanagedWriter3 Interface</span></span>
<span data-ttu-id="d45bb-103">Stellt einen Symbolwriter dar und bietet Methoden, um Dokumente, Sequenzpunkte, lexikalischen Gültigkeitsbereiche und Variablen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d45bb-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="d45bb-104">Diese Schnittstelle erweitert die [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d45bb-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d45bb-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="d45bb-105">Methods</span></span>  
  
|<span data-ttu-id="d45bb-106">Methode</span><span class="sxs-lookup"><span data-stu-id="d45bb-106">Method</span></span>|<span data-ttu-id="d45bb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d45bb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d45bb-108">Commit-Methode</span><span class="sxs-lookup"><span data-stu-id="d45bb-108">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-commit-method.md)|<span data-ttu-id="d45bb-109">Übernimmt die Änderungen, die bisher in den Stream geschrieben.</span><span class="sxs-lookup"><span data-stu-id="d45bb-109">Commits the changes written so far to the stream.</span></span>|  
|[<span data-ttu-id="d45bb-110">OpenMethod2-Methode</span><span class="sxs-lookup"><span data-stu-id="d45bb-110">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)|<span data-ttu-id="d45bb-111">Öffnet eine Methode, und bietet die echten Abschnittoffset im Bild.</span><span class="sxs-lookup"><span data-stu-id="d45bb-111">Opens a method and provides its real section offset in the image.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d45bb-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d45bb-112">Requirements</span></span>  
 <span data-ttu-id="d45bb-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d45bb-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d45bb-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d45bb-114">See also</span></span>

- [<span data-ttu-id="d45bb-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d45bb-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="d45bb-116">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d45bb-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="d45bb-117">ISymUnmanagedWriter2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d45bb-117">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
