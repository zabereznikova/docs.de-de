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
ms.openlocfilehash: 6904271ed90cf733b9221178927bc680d76b58a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176577"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="2f398-102">ISymUnmanagedSourceServerModule::GetSourceServerData-Methode</span><span class="sxs-lookup"><span data-stu-id="2f398-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="2f398-103">Gibt die Quellserverdaten für das Modul zurück.</span><span class="sxs-lookup"><span data-stu-id="2f398-103">Returns the source server data for the module.</span></span> <span data-ttu-id="2f398-104">Der Aufrufer muss Ressourcen `CoTaskMemFree`mithilfe von freimachen.</span><span class="sxs-lookup"><span data-stu-id="2f398-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f398-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f398-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f398-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2f398-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="2f398-107">[out] Ein Zeiger auf `ULONG32` eine, der die Größe der Quellserverdaten in Bytes empfängt.</span><span class="sxs-lookup"><span data-stu-id="2f398-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="2f398-108">[out] Ein Zeiger auf `pDataByteCount` den zurückgegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="2f398-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f398-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2f398-109">Return Value</span></span>  
 <span data-ttu-id="2f398-110">S_OK, ob die Methode erfolgreich ist. andernfalls E_FAIL oder einem anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="2f398-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f398-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2f398-111">Requirements</span></span>  
 <span data-ttu-id="2f398-112">**Kopfzeile:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2f398-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f398-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f398-113">See also</span></span>

- [<span data-ttu-id="2f398-114">ISymUnmanagedSourceServerModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f398-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
