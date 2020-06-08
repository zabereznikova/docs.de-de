---
title: CoInitializeCor-Funktion
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
ms.openlocfilehash: 1263467fc5db92d4dd21c4f09a98af309e2c4d55
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504419"
---
# <a name="coinitializecor-function"></a>CoInitializeCor-Funktion
`CoInitializeCor` ist veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a>Bemerkungen  
 Um die Common Language Runtime zu initialisieren, verwenden Sie entweder [corbindtoriuntimeex](corbindtoruntimeex-function.md) oder [corbindtoken currentruntime](corbindtocurrentruntime-function.md).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Header:** Cor. h  
  
## <a name="see-also"></a>Weitere Informationen:

- [Globale statische Metadatenfunktionen](../metadata/metadata-global-static-functions.md)
