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
ms.openlocfilehash: 2cac4a3120e842bde9ad708a251682421fd4ca93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696075"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a>ICorDebugFunction2::EnumerateNativeCode-Methode

Ruft einen Schnittstellen Zeiger auf ein ICorDebugCodeEnum-Objekt ab, das die systemeigenen Code Anweisungen in der Funktion enthält, auf die von diesem ICorDebugFunction2-Objekt verwiesen wird.  
  
> [!NOTE]
> `EnumerateNativeCode` ist in der aktuellen Version des .NET Framework nicht implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** CorDebug.idl, CorDebug.h
