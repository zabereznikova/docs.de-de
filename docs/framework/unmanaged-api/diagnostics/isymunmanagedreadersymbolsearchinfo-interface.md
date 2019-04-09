---
title: ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedReaderSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: fde7e21d-1169-4bed-a34d-792e69652bf9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a872774b1c4510c8d0325c59ae7678c867c1aff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216807"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="e8d87-102">ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8d87-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="e8d87-103">Bietet Methoden, die Symbolinformationen für die Suche zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e8d87-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="e8d87-104">Rufen Sie diese Schnittstelle durch den Aufruf `QueryInterface` auf ein Objekt, implementiert die [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e8d87-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e8d87-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e8d87-105">Methods</span></span>  
  
|<span data-ttu-id="e8d87-106">Methode</span><span class="sxs-lookup"><span data-stu-id="e8d87-106">Method</span></span>|<span data-ttu-id="e8d87-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8d87-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e8d87-108">GetSymbolSearchInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="e8d87-108">GetSymbolSearchInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="e8d87-109">Ruft die Symbolinformationen für die Suche ab.</span><span class="sxs-lookup"><span data-stu-id="e8d87-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="e8d87-110">GetSymbolSearchInfoCount-Methode</span><span class="sxs-lookup"><span data-stu-id="e8d87-110">GetSymbolSearchInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="e8d87-111">Ruft die Anzahl der Symbolinformationen für die Suche ab.</span><span class="sxs-lookup"><span data-stu-id="e8d87-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8d87-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8d87-112">Requirements</span></span>  
 <span data-ttu-id="e8d87-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e8d87-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d87-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8d87-114">See also</span></span>

- [<span data-ttu-id="e8d87-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e8d87-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
