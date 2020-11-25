---
title: _CorImageUnloading-Funktion
ms.date: 03/30/2017
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
ms.openlocfilehash: a8326f95286ef05dd370797a531417f81ed5c65b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723154"
---
# <a name="_corimageunloading-function"></a>_CorImageUnloading-Funktion

Benachrichtigt das Ladeprogramm, wenn die Images des verwalteten Moduls entladen werden.  
  
 Diese Funktion ist nicht implementiert. Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ImageBase`  
 in Ein Zeiger auf die Startposition des zu entladenden Bilds.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Globale statische Metadatenfunktionen](../metadata/metadata-global-static-functions.md)
