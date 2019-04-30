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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60b6d9c302cd3af9f41e5a8dce62d7eb268c4198
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961173"
---
# <a name="closeclrenumeration-function"></a>CloseCLREnumeration-Funktion
Schließt alle gültigen common Language Runtime (CLR) weiterhin-Starts Ereignisse befindet sich in einem Array von Handles, die vom der [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), und den Speicher für den Pfad von Handle- und Zeichenfolgenarrays freigegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pHandleArray`  
 [in] Zeiger auf das Array von Ereignishandles zurückgegeben wird, aus der [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).  
  
 `pStringArray`  
 [in] Zeiger auf das Array von CLR-Zeichenfolgenpfaden, die zurückgegeben werden, aus der [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).  
  
 `dwArrayLength`  
 [in] DWORD, das die Größe (Länge) von `pHandleArray` oder `pStringArray` enthält (diese sind identisch).  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Handles geöffnet wird, indem die [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) geschlossen werden, und für die Handle- und Zeichenfolgenarrays zugewiesenen Arbeitsspeicher wird freigegeben.  
  
 E_INVALIDARG  
 Die Länge von `pHandleArray` stimmt nicht mit der Länge überein, die in `dwArrayLength` übergeben wurde.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Die Funktion kann den Arbeitsspeicher für `pHandleArray` und `pStringArray` nicht freigeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** dbgshim.h  
  
 **Bibliothek:** dbgshim.dll  
  
 **.NET Framework-Versionen:** 3.5 SP1
