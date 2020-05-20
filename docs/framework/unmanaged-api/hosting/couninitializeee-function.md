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
ms.openlocfilehash: fa6297e926d53c02bb0d1af7b59b45b8ee152399
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616462"
---
# <a name="couninitializeee-function"></a>CoUninitializeEE-Funktion
`CoUninitializeEE`ist veraltet und bietet keine Funktionalität.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Common Language Runtime Ausführungs-Engine kann nicht aus einem Prozess entladen werden. Zum Herunterfahren der Ausführungs-Engine wird [CorExitProcess](corexitprocess-function.md)aufgerufen.  
  
## <a name="see-also"></a>Siehe auch

- [CoInitializeEE-Funktion](coinitializeee-function.md)
- [Globale statische Metadatenfunktionen](../metadata/metadata-global-static-functions.md)
