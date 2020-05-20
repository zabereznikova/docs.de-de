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
ms.openlocfilehash: 9a3a6c07a9cace0ac9834cdb05925a301285204c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615318"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="83fca-102">ISymUnmanagedSourceServerModule::GetSourceServerData-Methode</span><span class="sxs-lookup"><span data-stu-id="83fca-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="83fca-103">Gibt die Quell Serverdaten für das Modul zurück.</span><span class="sxs-lookup"><span data-stu-id="83fca-103">Returns the source server data for the module.</span></span> <span data-ttu-id="83fca-104">Der Aufrufer muss mithilfe von Ressourcen freigeben `CoTaskMemFree` .</span><span class="sxs-lookup"><span data-stu-id="83fca-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83fca-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="83fca-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83fca-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="83fca-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="83fca-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe der Quell Serverdaten in Bytes empfängt.</span><span class="sxs-lookup"><span data-stu-id="83fca-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="83fca-108">vorgenommen Ein Zeiger auf den zurückgegebenen `pDataByteCount` Wert.</span><span class="sxs-lookup"><span data-stu-id="83fca-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83fca-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="83fca-109">Return Value</span></span>  
 <span data-ttu-id="83fca-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="83fca-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83fca-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83fca-111">Requirements</span></span>  
 <span data-ttu-id="83fca-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="83fca-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83fca-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83fca-113">See also</span></span>

- [<span data-ttu-id="83fca-114">ISymUnmanagedSourceServerModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83fca-114">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)
