---
title: CloseCLREnumeration-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CloseCLREnumeration
api_location: dbgshim.dll
api_type: COM
f1_keywords: CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9f14b851795c92c3ce0c1e7536a4ff78fbdf927
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="closeclrenumeration-function"></a>CloseCLREnumeration-Funktion
Schließt alle gültigen common Language Runtime (CLR) weiterhin-Starts Ereignisse befindet sich in einem Array von Handles zurückgegebenes der [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), und der Speicher für die Handle- und Pfadarrays freigegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pHandleArray`  
 [in] Zeiger auf das Array von Ereignishandles zurückgegeben, aus der [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).  
  
 `pStringArray`  
 [in] Zeiger auf das Array von CLR-Zeichenfolgenpfaden, die zurückgegeben werden, aus der [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).  
  
 `dwArrayLength`  
 [in] DWORD, das die Größe (Länge) von `pHandleArray` oder `pStringArray` enthält (diese sind identisch).  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Handles geöffnet wird, indem Sie die [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) geschlossen sind, und für die Handle- und Pfadarrays zugewiesene Arbeitsspeicher freigegeben wird.  
  
 E_INVALIDARG  
 Die Länge von `pHandleArray` stimmt nicht mit der Länge überein, die in `dwArrayLength` übergeben wurde.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Die Funktion kann den Arbeitsspeicher für `pHandleArray` und `pStringArray` nicht freigeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** dbgshim.h  
  
 **Bibliothek:** dbgshim.dll  
  
 **.NET Framework-Versionen:** 3.5 SP1
