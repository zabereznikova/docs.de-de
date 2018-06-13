---
title: ISymUnmanagedENCUpdate::InitializeForEnc-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 46daf47e8fd478926ff75fa695f277c692679fb6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424962"
---
# <a name="isymunmanagedencupdateinitializeforenc-method"></a><span data-ttu-id="a3a03-102">ISymUnmanagedENCUpdate::InitializeForEnc-Methode</span><span class="sxs-lookup"><span data-stu-id="a3a03-102">ISymUnmanagedENCUpdate::InitializeForEnc Method</span></span>
<span data-ttu-id="a3a03-103">Ermöglicht das Methodengrenzen vor dem ersten Aufruf berechnet werden soll die [ISymUnmanagedENCUpdate:: Updatesymbolstore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="a3a03-103">Allows method boundaries to be computed before the first call to the [ISymUnmanagedENCUpdate::UpdateSymbolStore2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-updatesymbolstore2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3a03-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3a03-104">Syntax</span></span>  
  
```  
HRESULT InitializeForEnc();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a3a03-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a3a03-105">Return Value</span></span>  
 <span data-ttu-id="a3a03-106">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="a3a03-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3a03-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3a03-107">Requirements</span></span>  
 <span data-ttu-id="a3a03-108">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a3a03-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a03-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3a03-109">See Also</span></span>  
 [<span data-ttu-id="a3a03-110">ISymUnmanagedENCUpdate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3a03-110">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
