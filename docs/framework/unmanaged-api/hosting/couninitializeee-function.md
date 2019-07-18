---
title: CoUninitializeEE-Funktion
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d05bc472711838236ed18b00ce808d022d9581dc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758199"
---
# <a name="couninitializeee-function"></a>CoUninitializeEE-Funktion
`CoUninitializeEE` ist veraltet, und stellt keine Funktionalität bereit.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>Hinweise  
 Die common Language Runtime ausführungs-Engine kann nicht von einem Prozess entladen werden. Herunterfahren der Engine Ausführungsaufruf [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).  
  
## <a name="see-also"></a>Siehe auch

- [CoInitializeEE-Funktion](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [Globale statische Metadatenfunktionen](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
