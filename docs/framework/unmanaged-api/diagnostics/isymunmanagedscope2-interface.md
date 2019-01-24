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
ms.openlocfilehash: beb48835039f142ea1d9e18871f77ada1b6f4f3e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706312"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="1948d-102">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1948d-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="1948d-103">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="1948d-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="1948d-104">Diese Schnittstelle erweitert die [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) Schnittstelle mit Methoden, die Informationen zu definierten Konstanten innerhalb des Bereichs zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1948d-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1948d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1948d-105">Methods</span></span>  
  
|<span data-ttu-id="1948d-106">Methode</span><span class="sxs-lookup"><span data-stu-id="1948d-106">Method</span></span>|<span data-ttu-id="1948d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1948d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1948d-108">GetConstantCount-Methode</span><span class="sxs-lookup"><span data-stu-id="1948d-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="1948d-109">Ruft die Anzahl der in diesem Bereich definierten Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="1948d-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="1948d-110">GetConstants-Methode</span><span class="sxs-lookup"><span data-stu-id="1948d-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="1948d-111">Ruft ab, die lokalen Konstanten, die innerhalb dieses Bereichs definiert.</span><span class="sxs-lookup"><span data-stu-id="1948d-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1948d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1948d-112">Requirements</span></span>  
 <span data-ttu-id="1948d-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1948d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1948d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1948d-114">See also</span></span>
- [<span data-ttu-id="1948d-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1948d-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="1948d-116">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1948d-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
