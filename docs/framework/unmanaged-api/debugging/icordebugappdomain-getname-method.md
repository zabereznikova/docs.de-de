---
title: ICorDebugAppDomain::GetName-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 62defcb4b7a2f143269c7f617b762e3419d55426
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="01f07-102">ICorDebugAppDomain::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="01f07-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="01f07-103">Ruft den Namen der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="01f07-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01f07-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01f07-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01f07-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="01f07-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="01f07-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="01f07-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="01f07-107">Legen Sie diesen Wert auf 0 (null), um diese Methode in den Abfragemodus zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="01f07-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="01f07-108">[out] Ein Zeiger auf die Größe des Namens oder die Anzahl der Zeichen, die tatsächlich im zurückgegebenen `szName`.</span><span class="sxs-lookup"><span data-stu-id="01f07-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="01f07-109">Im Abfragemodus kann diesen Wert den Aufrufer wissen, wie großen einen Puffer für den Namen reservieren.</span><span class="sxs-lookup"><span data-stu-id="01f07-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="01f07-110">[out] Ein Array, das den Namen der Anwendungsdomäne speichert.</span><span class="sxs-lookup"><span data-stu-id="01f07-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01f07-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="01f07-111">Remarks</span></span>  
 <span data-ttu-id="01f07-112">Ein Debugger Ruft die `GetName` -Methode einmal zum Abrufen der Größe eines Puffers für den Namen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="01f07-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="01f07-113">Der Debugger die Puffer und ruft dann die Methode ein zweites Mal auf um den Puffer zu füllen.</span><span class="sxs-lookup"><span data-stu-id="01f07-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="01f07-114">Der erste Aufruf, zum Abrufen der Größe des Namens wird als bezeichnet *Abfragemodus*.</span><span class="sxs-lookup"><span data-stu-id="01f07-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01f07-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01f07-115">Requirements</span></span>  
 <span data-ttu-id="01f07-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01f07-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01f07-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01f07-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01f07-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01f07-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01f07-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01f07-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
