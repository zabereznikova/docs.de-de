---
title: ISymUnmanagedScope2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope2
helpviewer_keywords: ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5eed6061c8108fcf91f8ac1ac9ff139da426f0e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="f3bc0-102">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3bc0-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="f3bc0-103">Stellt einen lexikalischen Gültigkeitsbereich in einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="f3bc0-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="f3bc0-104">Diese Schnittstelle erweitert die [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) -Schnittstelle um Methoden, die Informationen über definierte Konstanten innerhalb des Bereichs zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f3bc0-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3bc0-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f3bc0-105">Methods</span></span>  
  
|<span data-ttu-id="f3bc0-106">Methode</span><span class="sxs-lookup"><span data-stu-id="f3bc0-106">Method</span></span>|<span data-ttu-id="f3bc0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3bc0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3bc0-108">GetConstantCount-Methode</span><span class="sxs-lookup"><span data-stu-id="f3bc0-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="f3bc0-109">Ruft die Anzahl der in diesem Bereich definierten Konstanten ab.</span><span class="sxs-lookup"><span data-stu-id="f3bc0-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="f3bc0-110">GetConstants-Methode</span><span class="sxs-lookup"><span data-stu-id="f3bc0-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="f3bc0-111">Ruft die lokalen Konstanten, die in diesem Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="f3bc0-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3bc0-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3bc0-112">Requirements</span></span>  
 <span data-ttu-id="f3bc0-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f3bc0-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3bc0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3bc0-114">See Also</span></span>  
 [<span data-ttu-id="f3bc0-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f3bc0-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="f3bc0-116">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3bc0-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
