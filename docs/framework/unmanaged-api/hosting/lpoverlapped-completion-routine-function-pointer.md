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
ms.openlocfilehash: dcf63000de549b42d92ba157a7e550ac605bbfcd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768378"
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a><span data-ttu-id="74aba-102">LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="74aba-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="74aba-103">Zeigt auf eine Funktion, die den Host benachrichtigt, wenn eine überlappende (d. h. asynchrone) E/A auf einem Gerät abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="74aba-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="74aba-104">Dieser Funktionszeiger wurde in .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="74aba-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74aba-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="74aba-105">Syntax</span></span>  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74aba-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="74aba-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="74aba-107">[in] Ein Wert, der einen Fehlercode ist, wenn das Gerät geschlossen wurde. Andernfalls ist dieser Wert 0 (null).</span><span class="sxs-lookup"><span data-stu-id="74aba-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="74aba-108">Schließen eines Geräts bewirkt, dass alle ausstehenden e/a an das Gerät nicht sofort abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="74aba-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="74aba-109">[in] Die Anzahl der Bytes der e/a-Vorgang übertragen.</span><span class="sxs-lookup"><span data-stu-id="74aba-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="74aba-110">[in] Ein Zeiger auf eine Struktur, die Informationen enthält, die verwendet werden, um die e/a-Anforderung abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="74aba-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74aba-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74aba-111">Remarks</span></span>  
 <span data-ttu-id="74aba-112">Die Funktion, die die `LPOVERLAPPED_COMPLETION_ROUTINE` ist eine Callback-Funktion und muss vom Writer der hostanwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="74aba-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="74aba-113">Die Callback-Funktion kann der Host die abgeschlossene e/a-Anforderung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="74aba-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74aba-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74aba-114">Requirements</span></span>  
 <span data-ttu-id="74aba-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74aba-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74aba-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="74aba-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74aba-117">**Bibliothek:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="74aba-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="74aba-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74aba-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74aba-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74aba-119">See also</span></span>

- [<span data-ttu-id="74aba-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="74aba-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
