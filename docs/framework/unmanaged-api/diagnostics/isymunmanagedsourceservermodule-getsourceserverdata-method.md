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
ms.openlocfilehash: c76c8b23e707b530cbf1c28d03fbf2f84d424482
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734009"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="536fa-102">ISymUnmanagedSourceServerModule::GetSourceServerData-Methode</span><span class="sxs-lookup"><span data-stu-id="536fa-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>

<span data-ttu-id="536fa-103">Gibt die Quell Serverdaten für das Modul zurück.</span><span class="sxs-lookup"><span data-stu-id="536fa-103">Returns the source server data for the module.</span></span> <span data-ttu-id="536fa-104">Der Aufrufer muss mithilfe von Ressourcen freigeben `CoTaskMemFree` .</span><span class="sxs-lookup"><span data-stu-id="536fa-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="536fa-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="536fa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="536fa-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="536fa-106">Parameters</span></span>  

 `pDataByteCount`  
 <span data-ttu-id="536fa-107">vorgenommen Ein Zeiger auf einen `ULONG32` , der die Größe der Quell Serverdaten in Bytes empfängt.</span><span class="sxs-lookup"><span data-stu-id="536fa-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="536fa-108">vorgenommen Ein Zeiger auf den zurückgegebenen `pDataByteCount` Wert.</span><span class="sxs-lookup"><span data-stu-id="536fa-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="536fa-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="536fa-109">Return Value</span></span>  

 <span data-ttu-id="536fa-110">S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="536fa-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="536fa-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="536fa-111">Requirements</span></span>  

 <span data-ttu-id="536fa-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="536fa-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="536fa-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="536fa-113">See also</span></span>

- [<span data-ttu-id="536fa-114">ISymUnmanagedSourceServerModule-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="536fa-114">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)
