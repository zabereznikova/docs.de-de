---
title: ISymENCUnmanagedMethod-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f7cc1cea74cc632c65c7e3c2aee408e2f9e864d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="33b5b-102">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33b5b-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="33b5b-103">Enthält Informationen für die Funktion bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="33b5b-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33b5b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="33b5b-104">Methods</span></span>  
  
|<span data-ttu-id="33b5b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="33b5b-105">Method</span></span>|<span data-ttu-id="33b5b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33b5b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33b5b-107">GetDocumentsForMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="33b5b-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="33b5b-108">Ruft die Dokumente, die diese Methode in Zeilen umfasst.</span><span class="sxs-lookup"><span data-stu-id="33b5b-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="33b5b-109">GetDocumentsForMethodCount-Methode</span><span class="sxs-lookup"><span data-stu-id="33b5b-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="33b5b-110">Ruft die Anzahl der Dokumente, die diese Methode in Zeilen umfasst.</span><span class="sxs-lookup"><span data-stu-id="33b5b-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="33b5b-111">GetFileNameFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="33b5b-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="33b5b-112">Ruft den Dateinamen für die Zeile mit einem Versatz verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="33b5b-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="33b5b-113">GetLineFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="33b5b-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="33b5b-114">Ruft die Zeileninformationen ein Offset zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="33b5b-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="33b5b-115">GetSourceExtentInDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="33b5b-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="33b5b-116">Ruft Starten des kleinsten und größten End Linie für die Methode in einem bestimmten Dokument.</span><span class="sxs-lookup"><span data-stu-id="33b5b-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33b5b-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33b5b-117">Requirements</span></span>  
 <span data-ttu-id="33b5b-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="33b5b-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b5b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33b5b-119">See Also</span></span>  
 [<span data-ttu-id="33b5b-120">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="33b5b-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
