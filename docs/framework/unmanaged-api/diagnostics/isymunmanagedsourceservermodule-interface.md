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
ms.openlocfilehash: 4fed0fcd806bd410c8a6817447e6fd634237624d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743178"
---
# <a name="isymunmanagedsourceservermodule-interface"></a><span data-ttu-id="3745a-102">ISymUnmanagedSourceServerModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3745a-102">ISymUnmanagedSourceServerModule Interface</span></span>
<span data-ttu-id="3745a-103">Quelldaten für die Server bereitstellt für ein Modul.</span><span class="sxs-lookup"><span data-stu-id="3745a-103">Provides source server data for a module.</span></span> <span data-ttu-id="3745a-104">Rufen Sie diese Schnittstelle durch den Aufruf `QueryInterface` auf ein Objekt, implementiert die [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3745a-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3745a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3745a-105">Methods</span></span>  
  
|<span data-ttu-id="3745a-106">Methode</span><span class="sxs-lookup"><span data-stu-id="3745a-106">Method</span></span>|<span data-ttu-id="3745a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3745a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3745a-108">GetSourceServerData-Methode</span><span class="sxs-lookup"><span data-stu-id="3745a-108">GetSourceServerData Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-getsourceserverdata-method.md)|<span data-ttu-id="3745a-109">Gibt die Quelldaten für die Server für das Modul zurück.</span><span class="sxs-lookup"><span data-stu-id="3745a-109">Returns the source server data for the module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3745a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3745a-110">Requirements</span></span>  
 <span data-ttu-id="3745a-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3745a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3745a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3745a-112">See also</span></span>
- [<span data-ttu-id="3745a-113">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3745a-113">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
