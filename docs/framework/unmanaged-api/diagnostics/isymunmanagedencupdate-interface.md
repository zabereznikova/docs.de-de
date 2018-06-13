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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05cbe098b73dd817546dd72f0fc98ad548f75386
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425417"
---
# <a name="isymunmanagedencupdate-interface"></a><span data-ttu-id="454c6-102">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="454c6-102">ISymUnmanagedENCUpdate Interface</span></span>
<span data-ttu-id="454c6-103">Bietet Funktionen für das Feature bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="454c6-103">Provides functions for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="454c6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="454c6-104">Methods</span></span>  
  
|<span data-ttu-id="454c6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="454c6-105">Method</span></span>|<span data-ttu-id="454c6-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="454c6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="454c6-107">GetLocalVariableCount-Methode</span><span class="sxs-lookup"><span data-stu-id="454c6-107">GetLocalVariableCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariablecount-method.md)|<span data-ttu-id="454c6-108">Ruft die Anzahl der lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="454c6-108">Gets the number of local variables.</span></span>|  
|[<span data-ttu-id="454c6-109">GetLocalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="454c6-109">GetLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-getlocalvariables-method.md)|<span data-ttu-id="454c6-110">Ruft die lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="454c6-110">Gets the local variables.</span></span>|  
|[<span data-ttu-id="454c6-111">InitializeForEnc-Methode</span><span class="sxs-lookup"><span data-stu-id="454c6-111">InitializeForEnc Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-initializeforenc-method.md)|<span data-ttu-id="454c6-112">Ermöglicht das Methodengrenzen vor dem ersten Aufruf berechnet werden soll die [ISymUnmanagedENCUpdate:: Updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="454c6-112">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>|  
|[<span data-ttu-id="454c6-113">UpdateMethodLines-Methode</span><span class="sxs-lookup"><span data-stu-id="454c6-113">UpdateMethodLines Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatemethodlines-method.md)|<span data-ttu-id="454c6-114">Ermöglicht das Aktualisieren der Zeile für eine Methode, die nicht kompiliert wurde, aber, deren Zeilen verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="454c6-114">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="454c6-115">Eine Delta für jede Anweisung ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="454c6-115">A delta for each statement is allowed.</span></span>|  
|[<span data-ttu-id="454c6-116">UpdateSymbolStore2-Methode</span><span class="sxs-lookup"><span data-stu-id="454c6-116">UpdateSymbolStore2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md)|<span data-ttu-id="454c6-117">Kann ein Compiler Auslassen von Funktionen, die aus dem Programm Programmdatenbankdatei (PDB)-Stream nicht geändert wurden, vorausgesetzt, dass die Zeileninformationen die Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="454c6-117">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided that the line information meets the requirements.</span></span> <span data-ttu-id="454c6-118">Die richtige Zeileninformationen kann mit den alten PDB-Zeileninformationen und einem Delta für alle Zeilen in der Funktion bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="454c6-118">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="454c6-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="454c6-119">Requirements</span></span>  
 <span data-ttu-id="454c6-120">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="454c6-120">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="454c6-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="454c6-121">See Also</span></span>  
 [<span data-ttu-id="454c6-122">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="454c6-122">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
