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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 323e53c45a26d5703548ebe9863978f6d3929f0b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787477"
---
# <a name="getalinkmessagedll-function"></a>GetALinkMessageDll-Funktion
Sucht und lädt die Nachrichten-dll. Gibt 0 zurück, wenn die Nachrichten-DLL nicht gefunden oder geladen werden konnte. Die Nachrichten-DLL muss sich entweder in einem Unterverzeichnis befinden, dessen Name eine Sprach-ID oder im aktuellen Verzeichnis ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Alink. h  
  
 **Bibliothek**: Alink. dll  
  
## <a name="see-also"></a>Siehe auch

- [Al.exe (Assembly Linker-Tool)](../../tools/al-exe-assembly-linker.md)
