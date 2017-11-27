---
title: ISymUnmanagedScope-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope
helpviewer_keywords: ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d25d62dd42e3e93124c9a3bd8945be265f192663
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="10dd1-102">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10dd1-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="10dd1-103">Stellt einen lexikalischen Gültigkeitsbereich in einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="10dd1-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10dd1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="10dd1-104">Methods</span></span>  
  
|<span data-ttu-id="10dd1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="10dd1-105">Method</span></span>|<span data-ttu-id="10dd1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10dd1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10dd1-107">GetChildren-Methode</span><span class="sxs-lookup"><span data-stu-id="10dd1-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="10dd1-108">Ruft die untergeordneten Elemente dieses Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="10dd1-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="10dd1-109">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="10dd1-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="10dd1-110">Ruft den Endoffset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="10dd1-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="10dd1-111">GetLocalCount-Methode</span><span class="sxs-lookup"><span data-stu-id="10dd1-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="10dd1-112">Ruft die Anzahl der in diesem Bereich definierten lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="10dd1-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="10dd1-113">GetLocals-Methode</span><span class="sxs-lookup"><span data-stu-id="10dd1-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="10dd1-114">Ruft die lokalen Variablen in diesem Bereich definiert.</span><span class="sxs-lookup"><span data-stu-id="10dd1-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="10dd1-115">GetMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="10dd1-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="10dd1-116">Ruft die Methode ab, die dieser Bereich enthält.</span><span class="sxs-lookup"><span data-stu-id="10dd1-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="10dd1-117">GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="10dd1-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="10dd1-118">Ruft die Namespaces, die in diesem Bereich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10dd1-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="10dd1-119">GetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="10dd1-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="10dd1-120">Ruft den übergeordneten Bereich dieses Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="10dd1-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="10dd1-121">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="10dd1-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="10dd1-122">Ruft den Anfangsoffset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="10dd1-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10dd1-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10dd1-123">Requirements</span></span>  
 <span data-ttu-id="10dd1-124">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="10dd1-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10dd1-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10dd1-125">See Also</span></span>  
 [<span data-ttu-id="10dd1-126">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="10dd1-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="10dd1-127">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10dd1-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
