---
title: ISymENCUnmanagedMethod-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f46aeed0a303278fd67265e471bfa13b43cede12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680184"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="687af-102">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="687af-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="687af-103">Enthält Informationen für die Funktion bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="687af-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="687af-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="687af-104">Methods</span></span>  
  
|<span data-ttu-id="687af-105">Methode</span><span class="sxs-lookup"><span data-stu-id="687af-105">Method</span></span>|<span data-ttu-id="687af-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="687af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="687af-107">GetDocumentsForMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="687af-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="687af-108">Ruft ab, die Dokumente, die diese Methode in Zeilen umfasst.</span><span class="sxs-lookup"><span data-stu-id="687af-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="687af-109">GetDocumentsForMethodCount-Methode</span><span class="sxs-lookup"><span data-stu-id="687af-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="687af-110">Ruft die Anzahl der Dokumente, die diese Methode in Zeilen umfasst.</span><span class="sxs-lookup"><span data-stu-id="687af-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="687af-111">GetFileNameFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="687af-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="687af-112">Ruft den Dateinamen für die Zeile, die ein Offset zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="687af-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="687af-113">GetLineFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="687af-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="687af-114">Ruft die Zeileninformationen, die ein Offset zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="687af-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="687af-115">GetSourceExtentInDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="687af-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="687af-116">Ruft Starten des kleinsten und größten End Zeile für die Methode in einem bestimmten Dokument.</span><span class="sxs-lookup"><span data-stu-id="687af-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="687af-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="687af-117">Requirements</span></span>  
 <span data-ttu-id="687af-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="687af-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="687af-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="687af-119">See also</span></span>
- [<span data-ttu-id="687af-120">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="687af-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
