---
title: ICorDebugAssembly::GetCodeBase-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetCodeBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetCodeBase
helpviewer_keywords:
- GetCodeBase method [.NET Framework debugging]
- ICorDebugAssembly::GetCodeBase method [.NET Framework debugging]
ms.assetid: 48adc154-9058-4fef-9c43-e9aad80e4dbf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6236d6b5349a9c2a528a85559c0cbc02c8da381
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645486"
---
# <a name="icordebugassemblygetcodebase-method"></a><span data-ttu-id="11442-102">ICorDebugAssembly::GetCodeBase-Methode</span><span class="sxs-lookup"><span data-stu-id="11442-102">ICorDebugAssembly::GetCodeBase Method</span></span>
<span data-ttu-id="11442-103">Diese Methode ist nicht in der aktuellen Version von .NET Framework implementiert.</span><span class="sxs-lookup"><span data-stu-id="11442-103">This method is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11442-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="11442-104">Syntax</span></span>  
  
```  
HRESULT GetCodeBase (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR szName[]  
);  
```
