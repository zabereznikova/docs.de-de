---
title: ISymUnmanagedMethod-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 728acc09f739fe567fca4a2571cbabf1ba8838a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427430"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="e81cb-102">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e81cb-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="e81cb-103">Stellt eine Methode in den Symbolspeicher dar.</span><span class="sxs-lookup"><span data-stu-id="e81cb-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="e81cb-104">Diese Schnittstelle bietet Zugriff auf nur die symbolbezogenen Attribute einer Methode, statt die Typ-bezogene Attribute.</span><span class="sxs-lookup"><span data-stu-id="e81cb-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e81cb-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e81cb-105">Methods</span></span>  
  
|<span data-ttu-id="e81cb-106">Methode</span><span class="sxs-lookup"><span data-stu-id="e81cb-106">Method</span></span>|<span data-ttu-id="e81cb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e81cb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e81cb-108">GetNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="e81cb-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="e81cb-109">Ruft den Namespace, in dem diese Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e81cb-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="e81cb-110">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="e81cb-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="e81cb-111">Gibt den Offset innerhalb dieser Methode, die entspricht einer bestimmten Position in einem Dokument.</span><span class="sxs-lookup"><span data-stu-id="e81cb-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="e81cb-112">GetParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="e81cb-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="e81cb-113">Ruft die Parameter für diese Methode ab.</span><span class="sxs-lookup"><span data-stu-id="e81cb-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="e81cb-114">GetRanges-Methode</span><span class="sxs-lookup"><span data-stu-id="e81cb-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="e81cb-115">Gibt bei Angabe einer Position in einem Dokument ein Array von Start- / Endoffsetpaaren, die entsprechen, die den Bereichen der Microsoft intermediate Language (MSIL), die die Position innerhalb dieser Methode abgedeckt werden.</span><span class="sxs-lookup"><span data-stu-id="e81cb-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="e81cb-116">GetRootScope-Methode</span><span class="sxs-lookup"><span data-stu-id="e81cb-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="e81cb-117">Ruft den lexikalischen Stammgültigkeitsbereich innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="e81cb-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="e81cb-118">Dieser Gültigkeitsbereich umfasst die gesamte Methode.</span><span class="sxs-lookup"><span data-stu-id="e81cb-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="e81cb-119">GetScopeFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="e81cb-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="e81cb-120">Ruft den umfassendsten lexikalischen Gültigkeitsbereich innerhalb dieser Methode, die den angegebenen Offset einschließt.</span><span class="sxs-lookup"><span data-stu-id="e81cb-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="e81cb-121">GetSequencePointCount-Methode</span><span class="sxs-lookup"><span data-stu-id="e81cb-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="e81cb-122">Ruft die Anzahl der Sequenzpunkte innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="e81cb-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="e81cb-123">GetSequencePoints-Methode</span><span class="sxs-lookup"><span data-stu-id="e81cb-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="e81cb-124">Ruft die Sequenzpunkte innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="e81cb-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="e81cb-125">GetSourceStartEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="e81cb-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="e81cb-126">Ruft die Anfangs- und Enddatum Dokumentpositionen für die Quelle dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="e81cb-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="e81cb-127">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="e81cb-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="e81cb-128">Gibt das Metadatentoken für diese Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="e81cb-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e81cb-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e81cb-129">Requirements</span></span>  
 <span data-ttu-id="e81cb-130">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e81cb-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e81cb-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e81cb-131">See Also</span></span>  
 [<span data-ttu-id="e81cb-132">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e81cb-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
