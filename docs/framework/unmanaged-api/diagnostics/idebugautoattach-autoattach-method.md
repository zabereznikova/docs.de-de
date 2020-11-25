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
ms.openlocfilehash: 64dd653bb0d4e383075a999e0803e4acfd0fae3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720099"
---
# <a name="idebugautoattachautoattach-method"></a><span data-ttu-id="5119b-102">IDebugAutoAttach::AutoAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="5119b-102">IDebugAutoAttach::AutoAttach Method</span></span>

<span data-ttu-id="5119b-103">Führt eine vom Server aufgerufene automatische Debugger-Anfügung aus.</span><span class="sxs-lookup"><span data-stu-id="5119b-103">Performs server-invoked debugger auto attach.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5119b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5119b-104">Syntax</span></span>  
  
```cpp  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5119b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5119b-105">Parameters</span></span>  

 `guidPort`  
 <span data-ttu-id="5119b-106">in Immer auf festgelegt `GUID_NULL` .</span><span class="sxs-lookup"><span data-stu-id="5119b-106">[in] Always set to `GUID_NULL`.</span></span>  
  
 `dwPid`  
 <span data-ttu-id="5119b-107">in Prozess-ID, die normalerweise mit der-Funktion abgerufen wird `GetCurrentProcessId` .</span><span class="sxs-lookup"><span data-stu-id="5119b-107">[in] Process ID, normally retrieved with the `GetCurrentProcessId` function.</span></span>  
  
 `dwProgramType`  
 <span data-ttu-id="5119b-108">in Programmtyp: `AUTOATTACH_PROGRAM_WIN32` , `AUTOATTACH_PROGRAM_COMPLUS` oder `AUTOATTACH_PROGRAM_UNKNOWN` .</span><span class="sxs-lookup"><span data-stu-id="5119b-108">[in] Program type: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, or `AUTOATTACH_PROGRAM_UNKNOWN`.</span></span>  
  
 `dwProgramId`  
 <span data-ttu-id="5119b-109">in Programm-ID.</span><span class="sxs-lookup"><span data-stu-id="5119b-109">[in] Program ID.</span></span>  
  
 `pszSessionId`  
 <span data-ttu-id="5119b-110">in Zeichenfolge, die vom DEBUG-Verb übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="5119b-110">[in] String passed by the debug verb.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5119b-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5119b-111">Return Value</span></span>  

 <span data-ttu-id="5119b-112">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="5119b-112">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5119b-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5119b-113">Requirements</span></span>  

 <span data-ttu-id="5119b-114">**Header:** DbgAutoAttach. h</span><span class="sxs-lookup"><span data-stu-id="5119b-114">**Header:** DbgAutoAttach.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5119b-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5119b-115">See also</span></span>

- [<span data-ttu-id="5119b-116">IDebugAutoAttach-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5119b-116">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)
