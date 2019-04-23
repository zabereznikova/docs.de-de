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
ms.openlocfilehash: c29656a4787c674886505a3be2508470460dfc10
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136525"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="9706d-102">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9706d-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="9706d-103">Stellt eine Methode in den Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="9706d-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="9706d-104">Diese Schnittstelle bietet Zugriff auf nur die Symbol-bezogene Attribute einer Methode, statt die Typ-bezogenen Attribute.</span><span class="sxs-lookup"><span data-stu-id="9706d-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9706d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9706d-105">Methods</span></span>  
  
|<span data-ttu-id="9706d-106">Methode</span><span class="sxs-lookup"><span data-stu-id="9706d-106">Method</span></span>|<span data-ttu-id="9706d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9706d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9706d-108">GetNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="9706d-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="9706d-109">Ruft den Namespace, in dem diese Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="9706d-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="9706d-110">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="9706d-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="9706d-111">Gibt den Offset innerhalb dieser Methode entspricht, die an einer bestimmten Position in einem Dokument zurück.</span><span class="sxs-lookup"><span data-stu-id="9706d-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="9706d-112">GetParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="9706d-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="9706d-113">Ruft die Parameter für diese Methode ab.</span><span class="sxs-lookup"><span data-stu-id="9706d-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="9706d-114">GetRanges-Methode</span><span class="sxs-lookup"><span data-stu-id="9706d-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="9706d-115">Gibt bei Angabe einer Position in einem Dokument ein Array von Start- / Endoffsetpaaren, die entsprechen, die den Bereichen Microsoft intermediate Language (MSIL), die die Position innerhalb dieser Methode abgedeckt werden.</span><span class="sxs-lookup"><span data-stu-id="9706d-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="9706d-116">GetRootScope-Methode</span><span class="sxs-lookup"><span data-stu-id="9706d-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="9706d-117">Ruft den lexikalischen Stammgültigkeitsbereich innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="9706d-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="9706d-118">Dieser Gültigkeitsbereich umfasst die gesamte Methode.</span><span class="sxs-lookup"><span data-stu-id="9706d-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="9706d-119">GetScopeFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="9706d-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="9706d-120">Ruft den umfassendsten lexikalischen Gültigkeitsbereich innerhalb dieser Methode, die den angegebenen Offset einschließt.</span><span class="sxs-lookup"><span data-stu-id="9706d-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="9706d-121">GetSequencePointCount-Methode</span><span class="sxs-lookup"><span data-stu-id="9706d-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="9706d-122">Ruft die Anzahl der Sequenzpunkte innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="9706d-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="9706d-123">GetSequencePoints-Methode</span><span class="sxs-lookup"><span data-stu-id="9706d-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="9706d-124">Ruft die Sequenzpunkte innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="9706d-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="9706d-125">GetSourceStartEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="9706d-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="9706d-126">Ruft die Dokumentpositionen für Start- und Endzeit für die Quelle dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="9706d-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="9706d-127">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="9706d-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="9706d-128">Gibt das Metadatentoken für diese Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="9706d-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9706d-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9706d-129">Requirements</span></span>  
 <span data-ttu-id="9706d-130">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9706d-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9706d-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9706d-131">See also</span></span>

- [<span data-ttu-id="9706d-132">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9706d-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
