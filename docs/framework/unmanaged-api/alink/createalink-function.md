---
title: CreateALink-Funktion
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
ms.openlocfilehash: 98c6ed4657dc69554a9fcca27145f65c621492f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683730"
---
# <a name="createalink-function"></a>CreateALink-Funktion

Erstellt eine Instanz des Assemblylinkers und legt einen Zeiger auf die angegebene-Schnittstelle fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a>Parameter  
  
|Parameter|BESCHREIBUNG|  
|---------------|-----------------|  
|`riid`|Der physische Name einer der Assembly Linker-Schnittstellen.|  
|`ppInterface`|Der Speicherort nach erfolgreichem Abschluss enthält einen Zeiger auf die- `riid` Schnittstelle.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Bibliothek**: alink.dll  
  
## <a name="see-also"></a>Weitere Informationen

- [Al.exe (Assembly Linker-Tool)](../../tools/al-exe-assembly-linker.md)
