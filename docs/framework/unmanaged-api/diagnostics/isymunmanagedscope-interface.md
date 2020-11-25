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
ms.openlocfilehash: 9256342ad3a91e6770d6fd19d9d2f94fab267d3e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725884"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="647cd-102">ISymUnmanagedScope-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="647cd-102">ISymUnmanagedScope Interface</span></span>

<span data-ttu-id="647cd-103">Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.</span><span class="sxs-lookup"><span data-stu-id="647cd-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="647cd-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="647cd-104">Methods</span></span>  
  
|<span data-ttu-id="647cd-105">Methode</span><span class="sxs-lookup"><span data-stu-id="647cd-105">Method</span></span>|<span data-ttu-id="647cd-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="647cd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="647cd-107">GetChildren-Methode</span><span class="sxs-lookup"><span data-stu-id="647cd-107">GetChildren Method</span></span>](isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="647cd-108">Ruft die untergeordneten Elemente dieses Gültigkeits Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="647cd-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="647cd-109">GetEndOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="647cd-109">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="647cd-110">Ruft den Endoffset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="647cd-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="647cd-111">GetLocalCount-Methode</span><span class="sxs-lookup"><span data-stu-id="647cd-111">GetLocalCount Method</span></span>](isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="647cd-112">Ruft die Anzahl der in diesem Bereich definierten lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="647cd-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="647cd-113">GetLocals-Methode</span><span class="sxs-lookup"><span data-stu-id="647cd-113">GetLocals Method</span></span>](isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="647cd-114">Ruft die in diesem Bereich definierten lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="647cd-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="647cd-115">GetMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="647cd-115">GetMethod Method</span></span>](isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="647cd-116">Ruft die Methode ab, die diesen Bereich enthält.</span><span class="sxs-lookup"><span data-stu-id="647cd-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="647cd-117">GetNamespaces-Methode</span><span class="sxs-lookup"><span data-stu-id="647cd-117">GetNamespaces Method</span></span>](isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="647cd-118">Ruft die Namespaces ab, die in diesem Bereich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="647cd-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="647cd-119">GetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="647cd-119">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)|<span data-ttu-id="647cd-120">Ruft den übergeordneten Gültigkeitsbereich dieses Bereichs ab.</span><span class="sxs-lookup"><span data-stu-id="647cd-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="647cd-121">GetStartOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="647cd-121">GetStartOffset Method</span></span>](isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="647cd-122">Ruft den Start Offset für diesen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="647cd-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="647cd-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="647cd-123">Requirements</span></span>  

 <span data-ttu-id="647cd-124">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="647cd-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="647cd-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="647cd-125">See also</span></span>

- [<span data-ttu-id="647cd-126">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="647cd-126">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="647cd-127">ISymUnmanagedScope2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="647cd-127">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)
