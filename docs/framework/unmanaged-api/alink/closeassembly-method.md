---
title: CloseAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location: alink.dll
api_type: COM
f1_keywords: CloseAssembly
helpviewer_keywords: CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 160ec53440f4ecdb924537c732a367881e75acf9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="closeassembly-method"></a>CloseAssembly-Methode
Schließt die Vorgänge der Assembly ab. Rufen Sie diese Methode, bevor Sie beginnen, eine neue Assembly oder ein ungebundener Modul.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `AssemblyID`  
 Die ID der Assembly.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h.  
  
## <a name="see-also"></a>Siehe auch  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [Alink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
