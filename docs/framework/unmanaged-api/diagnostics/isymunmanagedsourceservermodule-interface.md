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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ba81c208c4b49342c6a055e09ba898871db1851
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157604"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="7ccde-102">ISymUnmanagedSourceServerModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ccde-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="7ccde-103">Quelldaten für die Server bereitstellt für ein Modul.</span><span class="sxs-lookup"><span data-stu-id="7ccde-103">Provides source server data for a module.</span></span> <span data-ttu-id="7ccde-104">Rufen Sie diese Schnittstelle durch den Aufruf `QueryInterface` auf ein Objekt, implementiert die [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7ccde-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ccde-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7ccde-105">Methods</span></span>  
  
|<span data-ttu-id="7ccde-106">Methode</span><span class="sxs-lookup"><span data-stu-id="7ccde-106">Method</span></span>|<span data-ttu-id="7ccde-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ccde-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ccde-108">GetSourceServerData-Methode</span><span class="sxs-lookup"><span data-stu-id="7ccde-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="7ccde-109">Gibt die Quelldaten für die Server für das Modul zurück.</span><span class="sxs-lookup"><span data-stu-id="7ccde-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ccde-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ccde-110">Requirements</span></span>  
 <span data-ttu-id="7ccde-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7ccde-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ccde-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ccde-112">See also</span></span>

- [<span data-ttu-id="7ccde-113">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7ccde-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
