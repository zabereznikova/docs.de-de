---
title: ICorDebugFunction2::EnumerateNativeCode-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.EnumerateNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::EnumerateNativeCode
helpviewer_keywords:
- ICorDebugFunction2::EnumerateNativeCode method [.NET Framework debugging]
- EnumerateNativeCode method [.NET Framework debugging]
ms.assetid: d383f5cc-1144-4b6d-b57a-db34d9134ab2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb7e2ed7b076cfa20064902b3592c8f958efc0ee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917053"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="f8480-102">ICorDebugFunction2::EnumerateNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="f8480-102">ICorDebugFunction2::EnumerateNativeCode Method</span></span>
<span data-ttu-id="f8480-103">Ruft einen Schnittstellen Zeiger auf ein ICorDebugCodeEnum-Objekt ab, das die systemeigenen Code Anweisungen in der Funktion enthält, auf die von diesem ICorDebugFunction2-Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f8480-103">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8480-104">`EnumerateNativeCode`ist in der aktuellen Version des .NET Framework nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="f8480-104">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8480-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8480-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f8480-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8480-106">Requirements</span></span>  
 <span data-ttu-id="f8480-107">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="f8480-107">**Header:** CorDebug.idl, CorDebug.h</span></span>
