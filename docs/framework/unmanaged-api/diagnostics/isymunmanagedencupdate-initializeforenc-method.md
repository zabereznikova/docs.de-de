---
title: ISymUnmanagedENCUpdate::InitializeForEnc-Methode
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
- ISymUnmanagedENCUpdate.InitializeForEnc
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc
helpviewer_keywords:
- ISymUnmanagedENCUpdate::InitializeForEnc method [.NET Framework debugging]
- InitializeForEnc method [.NET Framework debugging]
ms.assetid: 796b2154-b53c-4d07-9e67-80fd6064725a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 47f9038a339ede575235d36e3225b7e948384b53
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="90ebc-102">ISymUnmanagedENCUpdate::InitializeForEnc-Methode</span><span class="sxs-lookup"><span data-stu-id="90ebc-102">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>
<span data-ttu-id="90ebc-103">Ermöglicht das Methodengrenzen vor dem ersten Aufruf berechnet werden soll die [ISymUnmanagedENCUpdate:: Updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="90ebc-103">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90ebc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90ebc-104">Syntax</span></span>  
  
```  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="90ebc-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="90ebc-105">Return Value</span></span>  
 <span data-ttu-id="90ebc-106">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="90ebc-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90ebc-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90ebc-107">Requirements</span></span>  
 <span data-ttu-id="90ebc-108">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="90ebc-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90ebc-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90ebc-109">See Also</span></span>  
 [<span data-ttu-id="90ebc-110">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90ebc-110">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
