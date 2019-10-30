---
title: CoreClrDebugProcInfo-Struktur
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
ms.openlocfilehash: e12882e53d1aa2120ab5c4b6793d7f2e34be76eb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132162"
---
# <a name="coreclrdebugprocinfo-structure"></a>CoreClrDebugProcInfo-Struktur
Entspricht einem Prozess, der auf einem Remotecomputer ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`m_dwPID`|Vom Betriebssystem zugewiesene Prozess-ID.|  
|`m_dwInternalID`|Die Prozess-ID, der durch den auf dem Zielcomputer ausgeführten Remotedebuggingproxy zugewiesen wird. Diese ID wird seltener wiederverwendet als die Betriebssystem-ID.|  
|`m_wszName`|Die Befehlszeile des Prozesses. Dieser Member wird möglicherweise abgeschnitten.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Coreclrremotedebugginginterfaces. h  
  
 **Bibliothek:** mscordbi_macx86. dll  
  
 **.NET Framework Versionen:** 3,5 SP1
