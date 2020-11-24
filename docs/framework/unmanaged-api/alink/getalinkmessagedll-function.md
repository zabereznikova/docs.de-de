---
title: GetALinkMessageDll-Funktion
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
ms.openlocfilehash: 554bd32ae965b21a88a09577749bbd7975f5ec7e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684745"
---
# <a name="getalinkmessagedll-function"></a>GetALinkMessageDll-Funktion

Sucht und lädt die Nachrichten-dll. Gibt 0 zurück, wenn die Nachrichten-DLL nicht gefunden oder geladen werden konnte. Die Nachrichten-DLL muss sich entweder in einem Unterverzeichnis befinden, dessen Name eine Sprach-ID oder im aktuellen Verzeichnis ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Alink. h  
  
 **Bibliothek**: alink.dll  
  
## <a name="see-also"></a>Weitere Informationen

- [Al.exe (Assembly Linker-Tool)](../../tools/al-exe-assembly-linker.md)
