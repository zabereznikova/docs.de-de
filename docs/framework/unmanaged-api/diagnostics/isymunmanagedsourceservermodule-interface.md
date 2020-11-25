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
ms.openlocfilehash: 5e438c75a29984e9200dc240f389f079a4eecfd7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733953"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="2d1b0-102">ISymUnmanagedSourceServerModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d1b0-102">ISymUnmanagedSourceServerModule Interface</span></span>

<span data-ttu-id="2d1b0-103">Stellt Quell Serverdaten für ein Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="2d1b0-103">Provides source server data for a module.</span></span> <span data-ttu-id="2d1b0-104">Rufen Sie diese Schnittstelle durch Aufrufen von `QueryInterface` für ein Objekt ab, das die [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="2d1b0-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d1b0-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="2d1b0-105">Methods</span></span>  
  
|<span data-ttu-id="2d1b0-106">Methode</span><span class="sxs-lookup"><span data-stu-id="2d1b0-106">Method</span></span>|<span data-ttu-id="2d1b0-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2d1b0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2d1b0-108">GetSourceServerData-Methode</span><span class="sxs-lookup"><span data-stu-id="2d1b0-108">GetSourceServerData Method</span></span>](isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="2d1b0-109">Gibt die Quell Serverdaten für das Modul zurück.</span><span class="sxs-lookup"><span data-stu-id="2d1b0-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d1b0-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2d1b0-110">Requirements</span></span>  

 <span data-ttu-id="2d1b0-111">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="2d1b0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d1b0-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d1b0-112">See also</span></span>

- [<span data-ttu-id="2d1b0-113">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2d1b0-113">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
