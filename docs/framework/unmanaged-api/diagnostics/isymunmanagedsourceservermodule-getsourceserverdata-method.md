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
ms.openlocfilehash: 71251af116fc8d634b822e1daa49d90e91fec6f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648822"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="67c1d-102">ISymUnmanagedSourceServerModule::GetSourceServerData-Methode</span><span class="sxs-lookup"><span data-stu-id="67c1d-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="67c1d-103">Gibt die Quelldaten für die Server für das Modul zurück.</span><span class="sxs-lookup"><span data-stu-id="67c1d-103">Returns the source server data for the module.</span></span> <span data-ttu-id="67c1d-104">Der Aufrufer muss Ressourcen freigeben, mithilfe von `CoTaskMemFree`.</span><span class="sxs-lookup"><span data-stu-id="67c1d-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c1d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="67c1d-105">Syntax</span></span>  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67c1d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="67c1d-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="67c1d-107">[out] Ein Zeiger auf eine `ULONG32` , der die Größe in Bytes der Source Server-Daten empfängt.</span><span class="sxs-lookup"><span data-stu-id="67c1d-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="67c1d-108">[out] Ein Zeiger auf das zurückgegebene `pDataByteCount` Wert.</span><span class="sxs-lookup"><span data-stu-id="67c1d-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67c1d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="67c1d-109">Return Value</span></span>  
 <span data-ttu-id="67c1d-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="67c1d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67c1d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67c1d-111">Requirements</span></span>  
 <span data-ttu-id="67c1d-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="67c1d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c1d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67c1d-113">See also</span></span>
- [<span data-ttu-id="67c1d-114">ISymUnmanagedSourceServerModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67c1d-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
