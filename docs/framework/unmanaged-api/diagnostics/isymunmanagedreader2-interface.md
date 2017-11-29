---
title: ISymUnmanagedReader2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2
helpviewer_keywords: ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b23e166249659b94d454070c01c003495d1018a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedreader2-interface"></a><span data-ttu-id="7b603-102">ISymUnmanagedReader2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b603-102">ISymUnmanagedReader2 Interface</span></span>
<span data-ttu-id="7b603-103">Stellt einen Symbolreader den Zugriff auf Dokumente, Methoden und Variablen in einem Symbolspeicher dar.</span><span class="sxs-lookup"><span data-stu-id="7b603-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span> <span data-ttu-id="7b603-104">Diese Schnittstelle erweitert die [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7b603-104">This interface extends the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b603-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7b603-105">Methods</span></span>  
  
|<span data-ttu-id="7b603-106">Methode</span><span class="sxs-lookup"><span data-stu-id="7b603-106">Method</span></span>|<span data-ttu-id="7b603-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b603-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b603-108">GetMethodByVersionPreRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="7b603-108">GetMethodByVersionPreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodbyversionpreremap-method.md)|<span data-ttu-id="7b603-109">Erhalten Sie ein Methodenobjekt des Symbolreaders, erhält ein Methodentoken und eine Versionsnummer mit bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="7b603-109">Get a symbol reader method, given a method token and an edit-and-continue version number.</span></span>|  
|[<span data-ttu-id="7b603-110">GetMethodsInDocument-Methode</span><span class="sxs-lookup"><span data-stu-id="7b603-110">GetMethodsInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getmethodsindocument-method.md)|<span data-ttu-id="7b603-111">Ruft jede Methode, die Zeileninformationen in das angegebene Dokument ab.</span><span class="sxs-lookup"><span data-stu-id="7b603-111">Gets every method that has line information in the provided document.</span></span>|  
|[<span data-ttu-id="7b603-112">GetSymAttributePreRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="7b603-112">GetSymAttributePreRemap Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-getsymattributepreremap-method.md)|<span data-ttu-id="7b603-113">Ruft ein benutzerdefiniertes Attribut anhand seines Namens ab.</span><span class="sxs-lookup"><span data-stu-id="7b603-113">Gets a custom attribute based upon its name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7b603-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b603-114">Requirements</span></span>  
 <span data-ttu-id="7b603-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7b603-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b603-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b603-116">See Also</span></span>  
 [<span data-ttu-id="7b603-117">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7b603-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="7b603-118">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b603-118">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
