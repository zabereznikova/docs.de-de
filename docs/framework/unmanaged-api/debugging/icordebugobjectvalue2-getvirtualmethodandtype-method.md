---
title: ICorDebugObjectValue2::GetVirtualMethodAndType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue2.GetVirtualMethodAndType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue2::GetVirtualMethodAndType
helpviewer_keywords:
- GetVirtualMethodAndType method [.NET Framework debugging]
- ICorDebugObjectValue2::GetVirtualMethodAndType method
ms.assetid: 621b4543-a8f7-4117-98e4-930992cd688a
topic_type:
- apiref
ms.openlocfilehash: 2a74688b90fbce63c9107d9389ddfd7bf5cd717b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695178"
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a>ICorDebugObjectValue2::GetVirtualMethodAndType-Methode

Diese Methode ist noch nicht implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a>Hinweise  

 Ruft Schnittstellen Zeiger auf die "ICorDebugFunction"-und "ICorDebugType"-Instanzen ab, die die am häufigsten abgeleitete Methode und den Typ für den angegebenen Element Verweis darstellen.  
  
## <a name="see-also"></a>Weitere Informationen
