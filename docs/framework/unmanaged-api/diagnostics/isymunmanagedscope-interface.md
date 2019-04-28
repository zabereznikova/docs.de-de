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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761636"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="47a8b-102">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47a8b-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="47a8b-103">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="47a8b-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="47a8b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="47a8b-104">Methods</span></span>  
  
|<span data-ttu-id="47a8b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="47a8b-105">Method</span></span>|<span data-ttu-id="47a8b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47a8b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="47a8b-107">GetChildren-Methode</span><span class="sxs-lookup"><span data-stu-id="47a8b-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="47a8b-108">Ruft die untergeordneten Elemente dieses Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="47a8b-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="47a8b-109">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="47a8b-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="47a8b-110">Ruft den Endoffset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="47a8b-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="47a8b-111">GetLocalCount-Methode</span><span class="sxs-lookup"><span data-stu-id="47a8b-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="47a8b-112">Ruft die Anzahl der in diesem Bereich definierten lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="47a8b-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="47a8b-113">GetLocals-Methode</span><span class="sxs-lookup"><span data-stu-id="47a8b-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="47a8b-114">Ruft ab, die lokalen Variablen, die innerhalb dieses Bereichs definiert.</span><span class="sxs-lookup"><span data-stu-id="47a8b-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="47a8b-115">GetMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="47a8b-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="47a8b-116">Ruft die Methode ab, die dieser Bereich enthält.</span><span class="sxs-lookup"><span data-stu-id="47a8b-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="47a8b-117">GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="47a8b-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="47a8b-118">Ruft die Namespaces, die innerhalb dieses Bereichs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47a8b-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="47a8b-119">GetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="47a8b-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="47a8b-120">Ruft den übergeordneten Bereich dieses Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="47a8b-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="47a8b-121">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="47a8b-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="47a8b-122">Ruft den Anfangsoffset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="47a8b-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47a8b-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47a8b-123">Requirements</span></span>  
 <span data-ttu-id="47a8b-124">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="47a8b-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a8b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47a8b-125">See also</span></span>

- [<span data-ttu-id="47a8b-126">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="47a8b-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="47a8b-127">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47a8b-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
