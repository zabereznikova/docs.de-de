---
title: ISymUnmanagedSourceServerModule-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule
helpviewer_keywords:
- ISymUnmanagedSourceServerModule interface [.NET Framework debugging]
ms.assetid: a19b23bd-2061-476e-b67d-252f57404f8b
topic_type:
- apiref
ms.openlocfilehash: d90a55b53ba00540137e44fc190790c4710903e3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610794"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="9a841-102">ISymUnmanagedSourceServerModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a841-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="9a841-103">Stellt Quell Serverdaten für ein Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="9a841-103">Provides source server data for a module.</span></span> <span data-ttu-id="9a841-104">Rufen Sie diese Schnittstelle durch Aufrufen von `QueryInterface` für ein Objekt ab, das die [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="9a841-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a841-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9a841-105">Methods</span></span>  
  
|<span data-ttu-id="9a841-106">Methode</span><span class="sxs-lookup"><span data-stu-id="9a841-106">Method</span></span>|<span data-ttu-id="9a841-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9a841-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a841-108">GetSourceServerData-Methode</span><span class="sxs-lookup"><span data-stu-id="9a841-108">GetSourceServerData Method</span></span>](isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="9a841-109">Gibt die Quell Serverdaten für das Modul zurück.</span><span class="sxs-lookup"><span data-stu-id="9a841-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a841-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a841-110">Requirements</span></span>  
 <span data-ttu-id="9a841-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="9a841-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a841-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a841-112">See also</span></span>

- [<span data-ttu-id="9a841-113">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9a841-113">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
