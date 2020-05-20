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
ms.openlocfilehash: 7a98a0c40f68cef9bab1ea2de0850208aaef77a0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615123"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="2061b-102">ISymUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2061b-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="2061b-103">Stellt eine Methode im Symbol Speicher dar.</span><span class="sxs-lookup"><span data-stu-id="2061b-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="2061b-104">Diese Schnittstelle bietet Zugriff auf die Symbol bezogenen Attribute einer Methode anstelle der typbezogenen Attribute.</span><span class="sxs-lookup"><span data-stu-id="2061b-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2061b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="2061b-105">Methods</span></span>  
  
|<span data-ttu-id="2061b-106">Methode</span><span class="sxs-lookup"><span data-stu-id="2061b-106">Method</span></span>|<span data-ttu-id="2061b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2061b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2061b-108">GetNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="2061b-108">GetNamespace Method</span></span>](isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="2061b-109">Ruft den Namespace ab, in dem diese Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="2061b-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="2061b-110">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="2061b-110">GetOffset Method</span></span>](isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="2061b-111">Gibt den Offset innerhalb dieser Methode zurück, der einer bestimmten Position in einem Dokument entspricht.</span><span class="sxs-lookup"><span data-stu-id="2061b-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="2061b-112">GetParameters-Methode</span><span class="sxs-lookup"><span data-stu-id="2061b-112">GetParameters Method</span></span>](isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="2061b-113">Ruft die Parameter für diese Methode ab.</span><span class="sxs-lookup"><span data-stu-id="2061b-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="2061b-114">GetRanges-Methode</span><span class="sxs-lookup"><span data-stu-id="2061b-114">GetRanges Method</span></span>](isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="2061b-115">Gibt ein Array von Start-und Endoffset Paaren zurück, die den Bereichen der Microsoft Intermediate Language (MSIL) entsprechen, die von der Position innerhalb dieser Methode abgedeckt werden, wenn eine Position in einem Dokument verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2061b-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="2061b-116">GetRootScope-Methode</span><span class="sxs-lookup"><span data-stu-id="2061b-116">GetRootScope Method</span></span>](isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="2061b-117">Ruft den lexikalischen Stamm Gültigkeitsbereich innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="2061b-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="2061b-118">Dieser Gültigkeitsbereich umfasst die gesamte Methode.</span><span class="sxs-lookup"><span data-stu-id="2061b-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="2061b-119">GetScopeFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="2061b-119">GetScopeFromOffset Method</span></span>](isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="2061b-120">Ruft den am weitesten schließenden lexikalischen Gültigkeitsbereich innerhalb dieser Methode ab, der den angegebenen Offset einschließt.</span><span class="sxs-lookup"><span data-stu-id="2061b-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="2061b-121">GetSequencePointCount-Methode</span><span class="sxs-lookup"><span data-stu-id="2061b-121">GetSequencePointCount Method</span></span>](isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="2061b-122">Ruft die Anzahl von Sequenz Punkten innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="2061b-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="2061b-123">GetSequencePoints-Methode</span><span class="sxs-lookup"><span data-stu-id="2061b-123">GetSequencePoints Method</span></span>](isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="2061b-124">Ruft alle Sequenz Punkte innerhalb dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="2061b-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="2061b-125">GetSourceStartEnd-Methode</span><span class="sxs-lookup"><span data-stu-id="2061b-125">GetSourceStartEnd Method</span></span>](isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="2061b-126">Ruft die Start-und Enddokument Positionen für die Quelle dieser Methode ab.</span><span class="sxs-lookup"><span data-stu-id="2061b-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="2061b-127">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="2061b-127">GetToken Method</span></span>](isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="2061b-128">Gibt das Metadatentoken für diese Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="2061b-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2061b-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2061b-129">Requirements</span></span>  
 <span data-ttu-id="2061b-130">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="2061b-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2061b-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2061b-131">See also</span></span>

- [<span data-ttu-id="2061b-132">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2061b-132">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
