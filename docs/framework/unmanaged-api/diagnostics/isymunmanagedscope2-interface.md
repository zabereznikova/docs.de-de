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
ms.openlocfilehash: 3374097c8d343fed6badf046742ca556d2a92f3e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446231"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="9586a-102">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9586a-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="9586a-103">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="9586a-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="9586a-104">Diese Schnittstelle erweitert die [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) -Schnittstelle um Methoden, die Informationen zu konstanten erhalten, die innerhalb des Bereichs definiert sind.</span><span class="sxs-lookup"><span data-stu-id="9586a-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9586a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9586a-105">Methods</span></span>  
  
|<span data-ttu-id="9586a-106">Methode</span><span class="sxs-lookup"><span data-stu-id="9586a-106">Method</span></span>|<span data-ttu-id="9586a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9586a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9586a-108">GetConstantCount-Methode</span><span class="sxs-lookup"><span data-stu-id="9586a-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="9586a-109">Ruft die Anzahl der in diesem Bereich definierten Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="9586a-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="9586a-110">GetConstants-Methode</span><span class="sxs-lookup"><span data-stu-id="9586a-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="9586a-111">Ruft die in diesem Bereich definierten lokalen Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="9586a-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9586a-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9586a-112">Requirements</span></span>  
 <span data-ttu-id="9586a-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="9586a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9586a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9586a-114">See also</span></span>

- [<span data-ttu-id="9586a-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9586a-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="9586a-116">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9586a-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
