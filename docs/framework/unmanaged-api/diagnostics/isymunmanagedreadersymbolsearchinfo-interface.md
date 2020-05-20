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
ms.openlocfilehash: 3f6cea68a4379f8769ccbdbc6911cc5c425d3369
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614876"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a><span data-ttu-id="1398c-102">ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1398c-102">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>
<span data-ttu-id="1398c-103">Stellt Methoden bereit, die Symbol Suchinformationen erhalten.</span><span class="sxs-lookup"><span data-stu-id="1398c-103">Provides methods that get symbol search information.</span></span> <span data-ttu-id="1398c-104">Rufen Sie diese Schnittstelle durch Aufrufen von `QueryInterface` für ein Objekt ab, das die [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="1398c-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1398c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="1398c-105">Methods</span></span>  
  
|<span data-ttu-id="1398c-106">Methode</span><span class="sxs-lookup"><span data-stu-id="1398c-106">Method</span></span>|<span data-ttu-id="1398c-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1398c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1398c-108">GetSymbolSearchInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="1398c-108">GetSymbolSearchInfo Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|<span data-ttu-id="1398c-109">Ruft Symbol Suchinformationen ab.</span><span class="sxs-lookup"><span data-stu-id="1398c-109">Gets symbol search information.</span></span>|  
|[<span data-ttu-id="1398c-110">GetSymbolSearchInfoCount-Methode</span><span class="sxs-lookup"><span data-stu-id="1398c-110">GetSymbolSearchInfoCount Method</span></span>](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|<span data-ttu-id="1398c-111">Ruft die Anzahl der Symbol Suchinformationen ab.</span><span class="sxs-lookup"><span data-stu-id="1398c-111">Gets a count of symbol search information.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1398c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1398c-112">Requirements</span></span>  
 <span data-ttu-id="1398c-113">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="1398c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1398c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1398c-114">See also</span></span>

- [<span data-ttu-id="1398c-115">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1398c-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
