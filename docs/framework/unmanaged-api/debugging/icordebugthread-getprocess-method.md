---
title: ICorDebugThread::GetProcess-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: be58714856b93a244248fb97d6cc1e1b4ec476c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="f101b-102">ICorDebugThread::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="f101b-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="f101b-103">Ruft einen Schnittstellenzeiger an den Prozess, von dem diese ICorDebugThread zwingend bildet.</span><span class="sxs-lookup"><span data-stu-id="f101b-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f101b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f101b-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f101b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f101b-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="f101b-106">[out] Ein Zeiger auf die Adresse eines ICorDebugProcess-Schnittstellenobjekts, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="f101b-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f101b-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f101b-107">Requirements</span></span>  
 <span data-ttu-id="f101b-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f101b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f101b-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f101b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f101b-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f101b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f101b-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f101b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
