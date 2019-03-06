---
title: ISymUnmanagedSourceServerModule::GetSourceServerData-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69e83a5ff489881938c1e8410f765fd63f3b5d84
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479440"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="65db0-102">ISymUnmanagedSourceServerModule::GetSourceServerData-Methode</span><span class="sxs-lookup"><span data-stu-id="65db0-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="65db0-103">Gibt die Quelldaten für die Server für das Modul zurück.</span><span class="sxs-lookup"><span data-stu-id="65db0-103">Returns the source server data for the module.</span></span> <span data-ttu-id="65db0-104">Der Aufrufer muss Ressourcen freigeben, mithilfe von `CoTaskMemFree`.</span><span class="sxs-lookup"><span data-stu-id="65db0-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65db0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="65db0-105">Syntax</span></span>  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65db0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="65db0-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="65db0-107">[out] Ein Zeiger auf eine `ULONG32` , der die Größe in Bytes der Source Server-Daten empfängt.</span><span class="sxs-lookup"><span data-stu-id="65db0-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="65db0-108">[out] Ein Zeiger auf das zurückgegebene `pDataByteCount` Wert.</span><span class="sxs-lookup"><span data-stu-id="65db0-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65db0-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="65db0-109">Return Value</span></span>  
 <span data-ttu-id="65db0-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="65db0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65db0-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="65db0-111">Requirements</span></span>  
 <span data-ttu-id="65db0-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="65db0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65db0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65db0-113">See also</span></span>
- [<span data-ttu-id="65db0-114">ISymUnmanagedSourceServerModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65db0-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
