---
title: CoUninitializeCor-Funktion
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
ms.openlocfilehash: 7d39c6fda6f159bfc937f62dc45d0d7ce37657f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687880"
---
# <a name="couninitializecor-function"></a>CoUninitializeCor-Funktion

`CoUninitializeCor` ist veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a>Hinweise  

 Der Common Language Runtime kann nicht aus einem Prozess entladen werden. Wenn Sie die Laufzeit vollständig aus einem laufenden Prozess entfernen möchten, müssen Sie diesen Prozess beenden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Globale statische Metadatenfunktionen](../metadata/metadata-global-static-functions.md)
