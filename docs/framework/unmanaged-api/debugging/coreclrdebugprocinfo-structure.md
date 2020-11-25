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
ms.openlocfilehash: 5996393fd1a0504f9c3d3f9f07aa0e3d886a0787
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719696"
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`m_dwPID`|Vom Betriebssystem zugewiesene Prozess-ID.|  
|`m_dwInternalID`|Die Prozess-ID, der durch den auf dem Zielcomputer ausgeführten Remotedebuggingproxy zugewiesen wird. Diese ID wird seltener wiederverwendet als die Betriebssystem-ID.|  
|`m_wszName`|Die Befehlszeile des Prozesses. Dieser Member wird möglicherweise abgeschnitten.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Coreclrremotedebugginginterfaces. h  
  
 **Bibliothek:** mscordbi_macx86.dll  
  
 **.NET Framework Versionen:** 3,5 SP1
