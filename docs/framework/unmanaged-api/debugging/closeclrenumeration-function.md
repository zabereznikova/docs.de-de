---
title: CloseCLREnumeration-Funktion
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
ms.openlocfilehash: 575e194cf952f02a3fe4fce9e955e45e1bc3653d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673912"
---
# <a name="closeclrenumeration-function"></a>CloseCLREnumeration-Funktion

Schließt alle gültigen Common Language Runtime (CLR) Continue-Startup-Ereignisse in einem Array von Handles, die von der [enumerateclrs-Funktion](enumerateclrs-function.md)zurückgegeben werden, und gibt den Arbeitsspeicher für das Handle und die Zeichen folgen Pfad Arrays frei.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pHandleArray`  
 in Ein Zeiger auf das Array von Ereignis Handles, die von der [enumerateclrs-Funktion](enumerateclrs-function.md)zurückgegeben werden.  
  
 `pStringArray`  
 in Ein Zeiger auf das Array von CLR-Zeichen folgen Pfaden, die von der [enumerateclrs-Funktion](enumerateclrs-function.md)zurückgegeben werden.  
  
 `dwArrayLength`  
 [in] DWORD, das die Größe (Länge) von `pHandleArray` oder `pStringArray` enthält (diese sind identisch).  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK  
 Handles, die von der [enumerateclrs-Funktion](enumerateclrs-function.md) geöffnet werden, werden geschlossen, und für das Handle-und Zeichen folgen Arrays zugeordnete Arbeitsspeicher wird freigegeben  
  
 E_INVALIDARG  
 Die Länge von `pHandleArray` stimmt nicht mit der Länge überein, die in `dwArrayLength` übergeben wurde.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Die Funktion kann den Arbeitsspeicher für `pHandleArray` und `pStringArray` nicht freigeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** dbgshim. h  
  
 **Bibliothek:** dbgshim.dll  
  
 **.NET Framework Versionen:** 3,5 SP1
