---
title: IDebugAutoAttach::AutoAttach-Methode
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16ccc56579a1ebe45ada61a9565cc8ade335333d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469677"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="a5b4d-102">IDebugAutoAttach::AutoAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="a5b4d-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="a5b4d-103">AutoAttach Debuggers führt anfügen.</span><span class="sxs-lookup"><span data-stu-id="a5b4d-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5b4d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5b4d-104">Syntax</span></span>  
  
```  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5b4d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a5b4d-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="a5b4d-106">[in] Legen Sie immer auf `GUID_NULL`.</span><span class="sxs-lookup"><span data-stu-id="a5b4d-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="a5b4d-107">[in] Prozess-ID, die normalerweise mit abgerufen. die `GetCurrentProcessId` Funktion.</span><span class="sxs-lookup"><span data-stu-id="a5b4d-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="a5b4d-108">[in] Programmtyp: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, oder `AUTOATTACH_PROGRAM_UNKNOWN`.</span><span class="sxs-lookup"><span data-stu-id="a5b4d-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="a5b4d-109">[in] Programm-ID an.</span><span class="sxs-lookup"><span data-stu-id="a5b4d-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="a5b4d-110">[in] Zeichenfolge, die durch das Debug-Verb übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a5b4d-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5b4d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a5b4d-111">Return Value</span></span>  
 <span data-ttu-id="a5b4d-112">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="a5b4d-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5b4d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a5b4d-113">Requirements</span></span>  
 <span data-ttu-id="a5b4d-114">**Header:** DbgAutoAttach.h</span><span class="sxs-lookup"><span data-stu-id="a5b4d-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b4d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5b4d-115">See also</span></span>
- [<span data-ttu-id="a5b4d-116">IDebugAutoAttach-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5b4d-116">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
