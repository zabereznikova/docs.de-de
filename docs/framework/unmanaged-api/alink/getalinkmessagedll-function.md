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
ms.openlocfilehash: 63719d0c6e13768e9dc7ed80e52e2a293e32a8a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449341"
---
# <a name="getalinkmessagedll-function"></a>GetALinkMessageDll-Funktion
Sucht und lädt die Nachrichten-dll. Gibt 0 zurück, wenn die Nachrichten-DLL nicht gefunden oder geladen werden konnte. Die Nachrichten-DLL muss sich entweder in einem Unterverzeichnis befinden, dessen Name eine Sprach-ID oder im aktuellen Verzeichnis ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Alink. h  
  
 **Bibliothek**: Alink. dll  
  
## <a name="see-also"></a>Siehe auch

- [Al.exe (Assembly Linker-Tool)](../../tools/al-exe-assembly-linker.md)
