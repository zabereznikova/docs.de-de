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
ms.openlocfilehash: 1d3ccb2265f056d5776199d997dc067c8d5513e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448788"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="d1184-102">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d1184-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="d1184-103">Stellt eine Methode im Symbol Speicher dar.</span><span class="sxs-lookup"><span data-stu-id="d1184-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="d1184-104">Diese Schnittstelle bietet Zugriff auf die Symbol bezogenen Attribute einer Methode anstelle der typbezogenen Attribute.</span><span class="sxs-lookup"><span data-stu-id="d1184-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1184-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="d1184-105">Methods</span></span>  
  
|<span data-ttu-id="d1184-106">Methode</span><span class="sxs-lookup"><span data-stu-id="d1184-106">Method</span></span>|<span data-ttu-id="d1184-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1184-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1184-108">GetNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="d1184-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="d1184-109">Ruft den Namespace ab, in dem diese Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d1184-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="d1184-110">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="d1184-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="d1184-111">Gibt den Offset innerhalb dieser Methode zurück, der einer bestimmten Position in einem Dokument entspricht.</span><span class="sxs-lookup"><span data-stu-id="d1184-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="d1184-112">GetParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="d1184-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="d1184-113">Ruft die Parameter für diese Methode ab.</span><span class="sxs-lookup"><span data-stu-id="d1184-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="d1184-114">GetRanges-Methode</span><span class="sxs-lookup"><span data-stu-id="d1184-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="d1184-115">Gibt ein Array von Start-und Endoffset Paaren zurück, die den Bereichen der Microsoft Intermediate Language (MSIL) entsprechen, die von der Position innerhalb dieser Methode abgedeckt werden, wenn eine Position in einem Dokument verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d1184-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="d1184-116">GetRootScope-Methode</span><span class="sxs-lookup"><span data-stu-id="d1184-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="d1184-117">Ruft den lexikalischen Stamm Gültigkeitsbereich innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="d1184-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="d1184-118">Dieser Gültigkeitsbereich umfasst die gesamte Methode.</span><span class="sxs-lookup"><span data-stu-id="d1184-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="d1184-119">GetScopeFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="d1184-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="d1184-120">Ruft den am weitesten schließenden lexikalischen Gültigkeitsbereich innerhalb dieser Methode ab, der den angegebenen Offset einschließt.</span><span class="sxs-lookup"><span data-stu-id="d1184-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="d1184-121">GetSequencePointCount-Methode</span><span class="sxs-lookup"><span data-stu-id="d1184-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="d1184-122">Ruft die Anzahl von Sequenz Punkten innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="d1184-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="d1184-123">GetSequencePoints-Methode</span><span class="sxs-lookup"><span data-stu-id="d1184-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="d1184-124">Ruft alle Sequenz Punkte innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="d1184-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="d1184-125">GetSourceStartEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="d1184-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="d1184-126">Ruft die Start-und Enddokument Positionen für die Quelle dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="d1184-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="d1184-127">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="d1184-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="d1184-128">Gibt das Metadatentoken für diese Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="d1184-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d1184-129">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d1184-129">Requirements</span></span>  
 <span data-ttu-id="d1184-130">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="d1184-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1184-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1184-131">See also</span></span>

- [<span data-ttu-id="d1184-132">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d1184-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
