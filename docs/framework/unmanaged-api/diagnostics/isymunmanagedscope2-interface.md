---
title: ISymUnmanagedScope2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0109b25b1cdc42204fc4873577e495641c4ec4fd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131455"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="3c0c6-102">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c0c6-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="3c0c6-103">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="3c0c6-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="3c0c6-104">Diese Schnittstelle erweitert die [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) Schnittstelle mit Methoden, die Informationen zu definierten Konstanten innerhalb des Bereichs zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3c0c6-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3c0c6-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3c0c6-105">Methods</span></span>  
  
|<span data-ttu-id="3c0c6-106">Methode</span><span class="sxs-lookup"><span data-stu-id="3c0c6-106">Method</span></span>|<span data-ttu-id="3c0c6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c0c6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3c0c6-108">GetConstantCount-Methode</span><span class="sxs-lookup"><span data-stu-id="3c0c6-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="3c0c6-109">Ruft die Anzahl der in diesem Bereich definierten Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="3c0c6-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="3c0c6-110">GetConstants-Methode</span><span class="sxs-lookup"><span data-stu-id="3c0c6-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="3c0c6-111">Ruft ab, die lokalen Konstanten, die innerhalb dieses Bereichs definiert.</span><span class="sxs-lookup"><span data-stu-id="3c0c6-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c0c6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3c0c6-112">Requirements</span></span>  
 <span data-ttu-id="3c0c6-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3c0c6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c0c6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c0c6-114">See also</span></span>

- [<span data-ttu-id="3c0c6-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3c0c6-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="3c0c6-116">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c0c6-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
