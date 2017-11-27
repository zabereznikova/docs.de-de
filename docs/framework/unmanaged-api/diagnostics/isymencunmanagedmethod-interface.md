---
title: ISymENCUnmanagedMethod-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod
helpviewer_keywords: ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 68929dc30b029133c73f18c3749f39f014359c0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="5bd7a-102">ISymENCUnmanagedMethod-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5bd7a-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="5bd7a-103">Enthält Informationen für die Funktion bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5bd7a-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5bd7a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5bd7a-104">Methods</span></span>  
  
|<span data-ttu-id="5bd7a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5bd7a-105">Method</span></span>|<span data-ttu-id="5bd7a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5bd7a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5bd7a-107">GetDocumentsForMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="5bd7a-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="5bd7a-108">Ruft die Dokumente, die diese Methode in Zeilen umfasst.</span><span class="sxs-lookup"><span data-stu-id="5bd7a-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="5bd7a-109">GetDocumentsForMethodCount-Methode</span><span class="sxs-lookup"><span data-stu-id="5bd7a-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="5bd7a-110">Ruft die Anzahl der Dokumente, die diese Methode in Zeilen umfasst.</span><span class="sxs-lookup"><span data-stu-id="5bd7a-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="5bd7a-111">GetFileNameFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="5bd7a-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="5bd7a-112">Ruft den Dateinamen für die Zeile mit einem Versatz verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="5bd7a-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="5bd7a-113">GetLineFromOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="5bd7a-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="5bd7a-114">Ruft die Zeileninformationen ein Offset zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5bd7a-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="5bd7a-115">GetSourceExtentInDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="5bd7a-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="5bd7a-116">Ruft Starten des kleinsten und größten End Linie für die Methode in einem bestimmten Dokument.</span><span class="sxs-lookup"><span data-stu-id="5bd7a-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5bd7a-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5bd7a-117">Requirements</span></span>  
 <span data-ttu-id="5bd7a-118">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5bd7a-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd7a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bd7a-119">See Also</span></span>  
 [<span data-ttu-id="5bd7a-120">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5bd7a-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
