---
title: ISymUnmanagedENCUpdate-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate
helpviewer_keywords:
- ISymUnmanagedENCUpdate interface [.NET Framework debugging]
ms.assetid: 63a9ef45-01a6-46da-b958-5c6dc2dc232c
topic_type:
- apiref
ms.openlocfilehash: aa4fe2185ead7edfa47d4194799c930193e04076
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614525"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="76180-102">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="76180-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="76180-103">Stellt Funktionen für die Funktion "Bearbeiten und Fortfahren" bereit.</span><span class="sxs-lookup"><span data-stu-id="76180-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="76180-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="76180-104">Methods</span></span>  
  
|<span data-ttu-id="76180-105">Methode</span><span class="sxs-lookup"><span data-stu-id="76180-105">Method</span></span>|<span data-ttu-id="76180-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="76180-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="76180-107">GetLocalVariableCount-Methode</span><span class="sxs-lookup"><span data-stu-id="76180-107">GetLocalVariableCount Method</span></span>](isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="76180-108">Ruft die Anzahl der lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="76180-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="76180-109">GetLocalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="76180-109">GetLocalVariables Method</span></span>](isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="76180-110">Ruft die lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="76180-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="76180-111">InitializeForEnc-Methode</span><span class="sxs-lookup"><span data-stu-id="76180-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="76180-112">Ermöglicht das Berechnen von Methoden Begrenzungen vor dem ersten Aufrufen der [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="76180-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="76180-113">UpdateMethodLines-Methode</span><span class="sxs-lookup"><span data-stu-id="76180-113">UpdateMethodLines Method</span></span>](isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="76180-114">Ermöglicht das Aktualisieren der Zeilen Informationen für eine Methode, die nicht erneut kompiliert wurde, deren Zeilen jedoch unabhängig voneinander verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="76180-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="76180-115">Ein Delta für jede Anweisung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="76180-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="76180-116">UpdateSymbolStore2-Methode</span><span class="sxs-lookup"><span data-stu-id="76180-116">UpdateSymbolStore2 Method</span></span>](isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="76180-117">Ermöglicht einem Compiler das Weglassen von Funktionen, die nicht aus dem Datenstrom der Programmdatenbank (PDB) geändert wurden, vorausgesetzt, die Zeilen Informationen erfüllen die Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="76180-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="76180-118">Die richtigen Zeilen Informationen können mit den alten PDB-Zeilen Informationen und einem Delta für alle Zeilen in der Funktion bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="76180-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="76180-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="76180-119">Requirements</span></span>  
 <span data-ttu-id="76180-120">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="76180-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76180-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76180-121">See also</span></span>

- [<span data-ttu-id="76180-122">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="76180-122">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
