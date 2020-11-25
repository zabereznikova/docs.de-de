---
title: InitDbgTransportManager-Funktion
ms.date: 03/30/2017
api_name:
- InitDbgTransportManager
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- InitDbgTransportManager
helpviewer_keywords:
- remote debugging API [Silverlight]
- InitDbgTransportManager function
- Silverlight, remote debugging
ms.assetid: a30102ff-c52e-48c9-b3a9-aa14286a42b2
topic_type:
- apiref
ms.openlocfilehash: a5b4783eadb8045733b9ebd6d10c4e31f7829498
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716680"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="238dd-102">InitDbgTransportManager-Funktion</span><span class="sxs-lookup"><span data-stu-id="238dd-102">InitDbgTransportManager Function</span></span>

<span data-ttu-id="238dd-103">Initialisiert den Transport-Manager, um eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration herzustellen.</span><span class="sxs-lookup"><span data-stu-id="238dd-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="238dd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="238dd-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="238dd-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="238dd-105">Return Value</span></span>  

 <span data-ttu-id="238dd-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="238dd-106">S_OK</span></span>  
 <span data-ttu-id="238dd-107">Erfolg.</span><span class="sxs-lookup"><span data-stu-id="238dd-107">Success.</span></span>  
  
 <span data-ttu-id="238dd-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="238dd-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="238dd-109">Die Funktion konnte keinen Arbeitsspeicher für einen Transport-Manager zuweisen.</span><span class="sxs-lookup"><span data-stu-id="238dd-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="238dd-110">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="238dd-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="238dd-111">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="238dd-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="238dd-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="238dd-112">Requirements</span></span>  

 <span data-ttu-id="238dd-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="238dd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="238dd-114">**Header:** Coreclrremotedebugginginterfaces. h</span><span class="sxs-lookup"><span data-stu-id="238dd-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="238dd-115">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="238dd-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="238dd-116">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="238dd-116">**.NET Framework Versions:** 3.5 SP1</span></span>
