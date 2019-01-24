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
ms.openlocfilehash: 632f19e0ead57d5508265fece578bb22f18ba54a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722724"
---
# <a name="getalinkmessagedll-function"></a>GetALinkMessageDll-Funktion
Sucht und lädt die Meldungs-DLL. Gibt 0 zurück, wenn die Meldungs-DLL nicht gefunden oder geladen werden konnte. Die Meldungs-DLL muss in einem Unterverzeichnis, deren Name eine Sprachen-ID ist, oder im aktuellen Verzeichnis.  
  
## <a name="syntax"></a>Syntax  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** alink.h  
  
 **Bibliothek**: alink.dll  
  
## <a name="see-also"></a>Siehe auch
- [Al.exe (Assembly Linker-Tool)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
