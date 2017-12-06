---
title: ICorDebugAssembly::GetProcess-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9250356bd1ab164ee293e6e86543108808d8d65a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="72a6a-102">ICorDebugAssembly::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="72a6a-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="72a6a-103">Ruft einen Schnittstellenzeiger an den Prozess, in dem diese ICorDebugAssembly-Instanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="72a6a-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72a6a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72a6a-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72a6a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="72a6a-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="72a6a-106">[out] Ein Zeiger auf eine ICorDebugProcess-Schnittstelle, die den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="72a6a-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72a6a-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="72a6a-107">Requirements</span></span>  
 <span data-ttu-id="72a6a-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72a6a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72a6a-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72a6a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72a6a-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72a6a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72a6a-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72a6a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
