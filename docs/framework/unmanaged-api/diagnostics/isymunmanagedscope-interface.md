---
title: ISymUnmanagedScope-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: 8da4da38d23ed65a0fdc44a0f919ee8cad2fe18e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446266"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="afa75-102">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="afa75-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="afa75-103">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="afa75-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="afa75-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="afa75-104">Methods</span></span>  
  
|<span data-ttu-id="afa75-105">Methode</span><span class="sxs-lookup"><span data-stu-id="afa75-105">Method</span></span>|<span data-ttu-id="afa75-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afa75-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="afa75-107">GetChildren-Methode</span><span class="sxs-lookup"><span data-stu-id="afa75-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="afa75-108">Ruft die untergeordneten Elemente dieses Gültigkeits Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="afa75-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="afa75-109">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="afa75-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="afa75-110">Ruft den Endoffset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="afa75-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="afa75-111">GetLocalCount-Methode</span><span class="sxs-lookup"><span data-stu-id="afa75-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="afa75-112">Ruft die Anzahl der in diesem Bereich definierten lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="afa75-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="afa75-113">GetLocals-Methode</span><span class="sxs-lookup"><span data-stu-id="afa75-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="afa75-114">Ruft die in diesem Bereich definierten lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="afa75-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="afa75-115">GetMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="afa75-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="afa75-116">Ruft die Methode ab, die diesen Bereich enthält.</span><span class="sxs-lookup"><span data-stu-id="afa75-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="afa75-117">GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="afa75-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="afa75-118">Ruft die Namespaces ab, die in diesem Bereich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="afa75-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="afa75-119">GetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="afa75-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="afa75-120">Ruft den übergeordneten Gültigkeitsbereich dieses Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="afa75-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="afa75-121">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="afa75-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="afa75-122">Ruft den Start Offset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="afa75-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="afa75-123">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="afa75-123">Requirements</span></span>  
 <span data-ttu-id="afa75-124">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="afa75-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa75-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afa75-125">See also</span></span>

- [<span data-ttu-id="afa75-126">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="afa75-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="afa75-127">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="afa75-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
