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
ms.openlocfilehash: 9165a4db7e65fb0f409a902b06d32e9c2988aa69
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446554"
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
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`riid`|Der physische Name einer der Assembly Linker-Schnittstellen.|  
|`ppInterface`|Der Speicherort nach erfolgreichem Abschluss enthält einen Zeiger auf die `riid`-Schnittstelle.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Bibliothek**: Alink. dll  
  
## <a name="see-also"></a>Siehe auch

- [Al.exe (Assembly Linker-Tool)](../../tools/al-exe-assembly-linker.md)
