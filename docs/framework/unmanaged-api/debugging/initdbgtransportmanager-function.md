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
ms.openlocfilehash: 74cb2c7d1f79d23e1331cc7192ba2d6acfd9835c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423662"
---
# <a name="initdbgtransportmanager-function"></a><span data-ttu-id="95fc7-102">InitDbgTransportManager-Funktion</span><span class="sxs-lookup"><span data-stu-id="95fc7-102">InitDbgTransportManager Function</span></span>
<span data-ttu-id="95fc7-103">Initialisiert den Transport-Manager, um eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration herzustellen.</span><span class="sxs-lookup"><span data-stu-id="95fc7-103">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95fc7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95fc7-104">Syntax</span></span>  
  
```  
HRESULT InitDbgTransportManager ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="95fc7-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="95fc7-105">Return Value</span></span>  
 <span data-ttu-id="95fc7-106">S_OK</span><span class="sxs-lookup"><span data-stu-id="95fc7-106">S_OK</span></span>  
 <span data-ttu-id="95fc7-107">Erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="95fc7-107">Success.</span></span>  
  
 <span data-ttu-id="95fc7-108">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="95fc7-108">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="95fc7-109">Die Funktion konnte keinen Arbeitsspeicher für einen Transport-Manager zuweisen.</span><span class="sxs-lookup"><span data-stu-id="95fc7-109">The function was unable to allocate memory for a transport manager.</span></span>  
  
 <span data-ttu-id="95fc7-110">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="95fc7-110">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="95fc7-111">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="95fc7-111">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95fc7-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95fc7-112">Requirements</span></span>  
 <span data-ttu-id="95fc7-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95fc7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95fc7-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="95fc7-114">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="95fc7-115">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="95fc7-115">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="95fc7-116">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="95fc7-116">**.NET Framework Versions:** 3.5 SP1</span></span>
