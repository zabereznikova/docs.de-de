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
ms.openlocfilehash: a33d8b489551dc69542e1b12bcf83602ec5a2008
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427247"
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="3db9b-102">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3db9b-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="3db9b-103">Stellt einen lexikalischen Gültigkeitsbereich in einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="3db9b-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="3db9b-104">Diese Schnittstelle erweitert die [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) -Schnittstelle um Methoden, die Informationen über definierte Konstanten innerhalb des Bereichs zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3db9b-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3db9b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3db9b-105">Methods</span></span>  
  
|<span data-ttu-id="3db9b-106">Methode</span><span class="sxs-lookup"><span data-stu-id="3db9b-106">Method</span></span>|<span data-ttu-id="3db9b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3db9b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3db9b-108">GetConstantCount-Methode</span><span class="sxs-lookup"><span data-stu-id="3db9b-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="3db9b-109">Ruft die Anzahl der in diesem Bereich definierten Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="3db9b-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="3db9b-110">GetConstants-Methode</span><span class="sxs-lookup"><span data-stu-id="3db9b-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="3db9b-111">Ruft die lokalen Konstanten, die in diesem Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="3db9b-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3db9b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3db9b-112">Requirements</span></span>  
 <span data-ttu-id="3db9b-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3db9b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db9b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3db9b-114">See Also</span></span>  
 [<span data-ttu-id="3db9b-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3db9b-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="3db9b-116">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3db9b-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
