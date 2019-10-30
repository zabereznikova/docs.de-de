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
ms.openlocfilehash: d5b24ee02a682b38dcf0cb3449f0dff197e91bf9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137828"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a>ICorDebugFunction2::EnumerateNativeCode-Methode
Ruft einen Schnittstellen Zeiger auf ein ICorDebugCodeEnum-Objekt ab, das die systemeigenen Code Anweisungen in der Funktion enthält, auf die von diesem ICorDebugFunction2-Objekt verwiesen wird.  
  
> [!NOTE]
> `EnumerateNativeCode` ist nicht in der aktuellen Version des .NET Framework implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorDebug.idl, CorDebug.h
