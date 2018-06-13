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
ms.openlocfilehash: e5c95423a6918da7cc043f8d46de13d166b8d895
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426184"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="ac554-102">IDebugAutoAttach::AutoAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="ac554-102">IDebugAutoAttach::AutoAttach Method</span></span>
<span data-ttu-id="ac554-103">AutoAttach Debuggers führt anfügen.</span><span class="sxs-lookup"><span data-stu-id="ac554-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac554-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac554-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="ac554-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac554-105">Parameters</span></span>  
 `guidPort`  
 <span data-ttu-id="ac554-106">[in] Legen Sie immer auf `GUID_NULL`.</span><span class="sxs-lookup"><span data-stu-id="ac554-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="ac554-107">[in] Prozess-ID, die normalerweise abgerufen, mit der `GetCurrentProcessId` Funktion.</span><span class="sxs-lookup"><span data-stu-id="ac554-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="ac554-108">[in] Programmtyp: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, oder `AUTOATTACH_PROGRAM_UNKNOWN`.</span><span class="sxs-lookup"><span data-stu-id="ac554-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="ac554-109">[in] Programm-ID an.</span><span class="sxs-lookup"><span data-stu-id="ac554-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="ac554-110">[in] Von der Debug-Verbs übergebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ac554-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac554-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ac554-111">Return Value</span></span>  
 <span data-ttu-id="ac554-112">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="ac554-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac554-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac554-113">Requirements</span></span>  
 <span data-ttu-id="ac554-114">**Header:** DbgAutoAttach.h</span><span class="sxs-lookup"><span data-stu-id="ac554-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac554-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac554-115">See Also</span></span>  
 [<span data-ttu-id="ac554-116">IDebugAutoAttach-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac554-116">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
