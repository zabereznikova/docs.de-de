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
ms.openlocfilehash: c0bdd9e59f5794dbb0d447dc2cc6cb682bfdf09f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008481"
---
# <a name="lpoverlapped_completion_routine-function-pointer"></a><span data-ttu-id="12806-102">LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="12806-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="12806-103">Zeigt auf eine Funktion, die den Host benachrichtigt, wenn eine überlappende (d. h. asynchrone) E/A auf einem Gerät abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="12806-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="12806-104">Dieser Funktionszeiger wurde in der .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="12806-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12806-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="12806-105">Syntax</span></span>  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12806-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="12806-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="12806-107">in Ein-Wert, bei dem es sich um einen Fehlercode handelt, wenn das Gerät geschlossen wurde. Andernfalls ist dieser Wert 0 (null).</span><span class="sxs-lookup"><span data-stu-id="12806-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="12806-108">Das Schließen eines Geräts bewirkt, dass alle ausstehenden e/a-Vorgänge auf dem Gerät sofort abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="12806-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="12806-109">in Die Anzahl von Bytes, die vom e/a-Vorgang übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="12806-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="12806-110">in Ein Zeiger auf eine-Struktur, die Informationen enthält, die verwendet werden, um die e/a-Anforderung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="12806-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12806-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="12806-111">Remarks</span></span>  
 <span data-ttu-id="12806-112">Die Funktion, auf die `LPOVERLAPPED_COMPLETION_ROUTINE` verweist, ist eine Rückruffunktion und muss vom Writer der Hostinganwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="12806-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="12806-113">Die Rückruffunktion ermöglicht es dem Host, die abgeschlossene e/a-Anforderung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="12806-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12806-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="12806-114">Requirements</span></span>  
 <span data-ttu-id="12806-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12806-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12806-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="12806-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="12806-117">**Bibliothek:** Mscorwert. dll</span><span class="sxs-lookup"><span data-stu-id="12806-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="12806-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12806-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12806-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12806-119">See also</span></span>

- [<span data-ttu-id="12806-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="12806-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
