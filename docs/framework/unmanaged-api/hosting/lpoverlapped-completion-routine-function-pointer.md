---
title: LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce2ce6dd1210eef94e77b5d6a2d58a35cf971e6d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138774"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a><span data-ttu-id="ecfaf-102">LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="ecfaf-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="ecfaf-103">Zeigt auf eine Funktion, die den Host benachrichtigt, wenn eine überlappende (d. h. asynchrone) E/A auf einem Gerät abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="ecfaf-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="ecfaf-104">Dieser Funktionszeiger ist veraltet, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecfaf-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecfaf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecfaf-105">Syntax</span></span>  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecfaf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ecfaf-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="ecfaf-107">[in] Ein Wert, der einen Fehlercode ist, wenn das Gerät geschlossen wurde. Andernfalls ist dieser Wert 0 (null).</span><span class="sxs-lookup"><span data-stu-id="ecfaf-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="ecfaf-108">Schließen eines Geräts bewirkt, dass alle ausstehenden e/a an das Gerät nicht sofort abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="ecfaf-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="ecfaf-109">[in] Die Anzahl der Bytes der e/a-Vorgang übertragen.</span><span class="sxs-lookup"><span data-stu-id="ecfaf-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="ecfaf-110">[in] Ein Zeiger auf eine Struktur, die Informationen enthält, die verwendet werden, um die e/a-Anforderung abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="ecfaf-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecfaf-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ecfaf-111">Remarks</span></span>  
 <span data-ttu-id="ecfaf-112">Die Funktion, die die `LPOVERLAPPED_COMPLETION_ROUTINE` ist eine Callback-Funktion und muss vom Writer der hostanwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="ecfaf-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="ecfaf-113">Die Callback-Funktion kann der Host die abgeschlossene e/a-Anforderung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ecfaf-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecfaf-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ecfaf-114">Requirements</span></span>  
 <span data-ttu-id="ecfaf-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecfaf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecfaf-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ecfaf-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ecfaf-117">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="ecfaf-117">**Library:** MSCorWks.dll</span></span>  
  
 **<span data-ttu-id="ecfaf-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ecfaf-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ecfaf-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecfaf-119">See also</span></span>

- [<span data-ttu-id="ecfaf-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="ecfaf-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
