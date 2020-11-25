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
ms.openlocfilehash: 5e3c2ecd1bdd5c1181223c7500eb7473e20fa5d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731344"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="d05b1-102">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d05b1-102">ISymUnmanagedENCUpdate Interface</span></span>

<span data-ttu-id="d05b1-103">Stellt Funktionen für die Funktion "Bearbeiten und Fortfahren" bereit.</span><span class="sxs-lookup"><span data-stu-id="d05b1-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d05b1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d05b1-104">Methods</span></span>  
  
|<span data-ttu-id="d05b1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d05b1-105">Method</span></span>|<span data-ttu-id="d05b1-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d05b1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d05b1-107">GetLocalVariableCount-Methode</span><span class="sxs-lookup"><span data-stu-id="d05b1-107">GetLocalVariableCount Method</span></span>](isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="d05b1-108">Ruft die Anzahl der lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="d05b1-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="d05b1-109">GetLocalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="d05b1-109">GetLocalVariables Method</span></span>](isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="d05b1-110">Ruft die lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="d05b1-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="d05b1-111">InitializeForEnc-Methode</span><span class="sxs-lookup"><span data-stu-id="d05b1-111">InitializeForEnc Method</span></span>](isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="d05b1-112">Ermöglicht das Berechnen von Methoden Begrenzungen vor dem ersten Aufrufen der [ISymUnmanagedENCUpdate:: UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="d05b1-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="d05b1-113">UpdateMethodLines-Methode</span><span class="sxs-lookup"><span data-stu-id="d05b1-113">UpdateMethodLines Method</span></span>](isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="d05b1-114">Ermöglicht das Aktualisieren der Zeilen Informationen für eine Methode, die nicht erneut kompiliert wurde, deren Zeilen jedoch unabhängig voneinander verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="d05b1-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="d05b1-115">Ein Delta für jede Anweisung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="d05b1-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="d05b1-116">UpdateSymbolStore2-Methode</span><span class="sxs-lookup"><span data-stu-id="d05b1-116">UpdateSymbolStore2 Method</span></span>](isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="d05b1-117">Ermöglicht einem Compiler das Weglassen von Funktionen, die nicht aus dem Datenstrom der Programmdatenbank (PDB) geändert wurden, vorausgesetzt, die Zeilen Informationen erfüllen die Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="d05b1-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="d05b1-118">Die richtigen Zeilen Informationen können mit den alten PDB-Zeilen Informationen und einem Delta für alle Zeilen in der Funktion bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="d05b1-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d05b1-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d05b1-119">Requirements</span></span>  

 <span data-ttu-id="d05b1-120">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="d05b1-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d05b1-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d05b1-121">See also</span></span>

- [<span data-ttu-id="d05b1-122">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d05b1-122">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
