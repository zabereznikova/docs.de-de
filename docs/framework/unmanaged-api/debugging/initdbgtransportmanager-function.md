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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 948e97064d12dc5b2044faf35aa374e5ba5f2592
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764783"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="b2d67-102">InitDbgTransportManager-Funktion</span><span class="sxs-lookup"><span data-stu-id="b2d67-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="b2d67-103">Initialisiert den Transport-Manager, um eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration herzustellen.</span><span class="sxs-lookup"><span data-stu-id="b2d67-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2d67-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2d67-104">Syntax</span></span>  
  
```cpp  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b2d67-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b2d67-105">Return Value</span></span>  
 <span data-ttu-id="b2d67-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2d67-106">S_OK</span></span>  
 <span data-ttu-id="b2d67-107">Erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="b2d67-107">Success.</span></span>  
  
 <span data-ttu-id="b2d67-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b2d67-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="b2d67-109">Die Funktion konnte keinen Arbeitsspeicher für einen Transport-Manager zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b2d67-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="b2d67-110">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="b2d67-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="b2d67-111">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="b2d67-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2d67-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b2d67-112">Requirements</span></span>  
 <span data-ttu-id="b2d67-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2d67-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2d67-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="b2d67-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="b2d67-115">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="b2d67-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="b2d67-116">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="b2d67-116">**.NET Framework Versions:** 3.5 SP1</span></span>
