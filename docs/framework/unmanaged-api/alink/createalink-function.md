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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b494b8b776f4cb0eb534233c5a03ab2d34a698ef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115621"
---
# <a name="createalink-function"></a>CreateALink-Funktion
Erstellt eine Instanz der Assembly Linker und setzt einen Zeiger auf die angegebene Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`riid`|Der physische Name einer Assemblylinker-Schnittstellen.|  
|`ppInterface`|Das Verzeichnis, bei erfolgreichem Abschluss einen Zeiger auf die `riid` Schnittstelle.|  
  
## <a name="requirements"></a>Anforderungen  
 **Bibliothek**: alink.dll  
  
## <a name="see-also"></a>Siehe auch

- [Al.exe (Assembly Linker-Tool)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
