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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 809368ea19528a7ce00d4fcada06ef5724eb79a6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228158"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="4030b-102">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4030b-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="4030b-103">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="4030b-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4030b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4030b-104">Methods</span></span>  
  
|<span data-ttu-id="4030b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4030b-105">Method</span></span>|<span data-ttu-id="4030b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4030b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4030b-107">GetChildren-Methode</span><span class="sxs-lookup"><span data-stu-id="4030b-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="4030b-108">Ruft die untergeordneten Elemente dieses Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="4030b-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="4030b-109">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="4030b-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="4030b-110">Ruft den Endoffset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="4030b-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="4030b-111">GetLocalCount-Methode</span><span class="sxs-lookup"><span data-stu-id="4030b-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="4030b-112">Ruft die Anzahl der in diesem Bereich definierten lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="4030b-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="4030b-113">GetLocals-Methode</span><span class="sxs-lookup"><span data-stu-id="4030b-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="4030b-114">Ruft ab, die lokalen Variablen, die innerhalb dieses Bereichs definiert.</span><span class="sxs-lookup"><span data-stu-id="4030b-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="4030b-115">GetMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="4030b-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="4030b-116">Ruft die Methode ab, die dieser Bereich enthält.</span><span class="sxs-lookup"><span data-stu-id="4030b-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="4030b-117">GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="4030b-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="4030b-118">Ruft die Namespaces, die innerhalb dieses Bereichs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4030b-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="4030b-119">GetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="4030b-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="4030b-120">Ruft den übergeordneten Bereich dieses Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="4030b-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="4030b-121">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="4030b-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="4030b-122">Ruft den Anfangsoffset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="4030b-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4030b-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4030b-123">Requirements</span></span>  
 <span data-ttu-id="4030b-124">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4030b-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4030b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4030b-125">See also</span></span>

- [<span data-ttu-id="4030b-126">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4030b-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="4030b-127">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4030b-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
