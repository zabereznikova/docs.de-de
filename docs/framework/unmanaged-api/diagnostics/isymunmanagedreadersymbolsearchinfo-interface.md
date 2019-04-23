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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216807"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="ec726-102">ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec726-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="ec726-103">Bietet Methoden, die Symbolinformationen für die Suche zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ec726-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="ec726-104">Rufen Sie diese Schnittstelle durch den Aufruf `QueryInterface` auf ein Objekt, implementiert die [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ec726-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec726-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ec726-105">Methods</span></span>  
  
|<span data-ttu-id="ec726-106">Methode</span><span class="sxs-lookup"><span data-stu-id="ec726-106">Method</span></span>|<span data-ttu-id="ec726-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec726-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec726-108">GetSymbolSearchInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="ec726-108">GetSymbolSearchInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="ec726-109">Ruft die Symbolinformationen für die Suche ab.</span><span class="sxs-lookup"><span data-stu-id="ec726-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="ec726-110">GetSymbolSearchInfoCount-Methode</span><span class="sxs-lookup"><span data-stu-id="ec726-110">GetSymbolSearchInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="ec726-111">Ruft die Anzahl der Symbolinformationen für die Suche ab.</span><span class="sxs-lookup"><span data-stu-id="ec726-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec726-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec726-112">Requirements</span></span>  
 <span data-ttu-id="ec726-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ec726-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec726-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec726-114">See also</span></span>

- [<span data-ttu-id="ec726-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ec726-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
