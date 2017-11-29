---
title: ISymUnmanagedMethod-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod
helpviewer_keywords: ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 030ea4b472f6a6aead307e0c5cc94dfb34c19992
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="7e8f8-102">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e8f8-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="7e8f8-103">Stellt eine Methode in den Symbolspeicher dar.</span><span class="sxs-lookup"><span data-stu-id="7e8f8-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="7e8f8-104">Diese Schnittstelle bietet Zugriff auf nur die symbolbezogenen Attribute einer Methode, statt die Typ-bezogene Attribute.</span><span class="sxs-lookup"><span data-stu-id="7e8f8-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e8f8-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7e8f8-105">Methods</span></span>  
  
|<span data-ttu-id="7e8f8-106">Methode</span><span class="sxs-lookup"><span data-stu-id="7e8f8-106">Method</span></span>|<span data-ttu-id="7e8f8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e8f8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e8f8-108">GetNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="7e8f8-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="7e8f8-109">Ruft den Namespace, in dem diese Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7e8f8-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="7e8f8-110">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="7e8f8-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="7e8f8-111">Gibt den Offset innerhalb dieser Methode, die entspricht einer bestimmten Position in einem Dokument.</span><span class="sxs-lookup"><span data-stu-id="7e8f8-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="7e8f8-112">GetParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="7e8f8-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="7e8f8-113">Ruft die Parameter für diese Methode ab.</span><span class="sxs-lookup"><span data-stu-id="7e8f8-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="7e8f8-114">GetRanges-Methode</span><span class="sxs-lookup"><span data-stu-id="7e8f8-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="7e8f8-115">Gibt bei Angabe einer Position in einem Dokument ein Array von Start- / Endoffsetpaaren, die entsprechen, die den Bereichen der Microsoft intermediate Language (MSIL), die die Position innerhalb dieser Methode abgedeckt werden.</span><span class="sxs-lookup"><span data-stu-id="7e8f8-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="7e8f8-116">GetRootScope-Methode</span><span class="sxs-lookup"><span data-stu-id="7e8f8-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="7e8f8-117">Ruft den lexikalischen Stammgültigkeitsbereich innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="7e8f8-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="7e8f8-118">Dieser Gültigkeitsbereich umfasst die gesamte Methode.</span><span class="sxs-lookup"><span data-stu-id="7e8f8-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="7e8f8-119">GetScopeFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="7e8f8-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="7e8f8-120">Ruft den umfassendsten lexikalischen Gültigkeitsbereich innerhalb dieser Methode, die den angegebenen Offset einschließt.</span><span class="sxs-lookup"><span data-stu-id="7e8f8-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="7e8f8-121">GetSequencePointCount-Methode</span><span class="sxs-lookup"><span data-stu-id="7e8f8-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="7e8f8-122">Ruft die Anzahl der Sequenzpunkte innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="7e8f8-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="7e8f8-123">GetSequencePoints-Methode</span><span class="sxs-lookup"><span data-stu-id="7e8f8-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="7e8f8-124">Ruft die Sequenzpunkte innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="7e8f8-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="7e8f8-125">GetSourceStartEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="7e8f8-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="7e8f8-126">Ruft die Anfangs- und Enddatum Dokumentpositionen für die Quelle dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="7e8f8-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="7e8f8-127">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="7e8f8-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="7e8f8-128">Gibt das Metadatentoken für diese Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="7e8f8-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e8f8-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7e8f8-129">Requirements</span></span>  
 <span data-ttu-id="7e8f8-130">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7e8f8-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e8f8-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e8f8-131">See Also</span></span>  
 [<span data-ttu-id="7e8f8-132">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7e8f8-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
