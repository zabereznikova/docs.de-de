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
ms.openlocfilehash: a4d15d9ae63e63f98ab73e250df558dfa16002a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61959964"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="3cc19-102">ICorDebugFunction2::EnumerateNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="3cc19-102">ICorDebugFunction2::EnumerateNativeCode Method</span></span>
<span data-ttu-id="3cc19-103">Ruft einen Schnittstellenzeiger auf ein ICorDebugCodeEnum-Objekt, das den nativen Code-in der Funktion, die von diesem ICorDebugFunction2-Objekt verwiesen wird Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="3cc19-103">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cc19-104">`EnumerateNativeCode` in der aktuellen Version von .NET Framework ist nicht implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="3cc19-104">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc19-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3cc19-105">Syntax</span></span>  
  
```  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3cc19-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3cc19-106">Requirements</span></span>  
 <span data-ttu-id="3cc19-107">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cc19-107">**Header:** CorDebug.idl, CorDebug.h</span></span>
