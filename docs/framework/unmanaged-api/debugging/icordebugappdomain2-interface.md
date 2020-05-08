---
title: ICorDebugAppDomain2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
ms.openlocfilehash: 1643d91f373ff233540026440ee21aa4c146f3e3
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895134"
---
# <a name="icordebugappdomain2-interface"></a>ICorDebugAppDomain2-Schnittstelle

Stellt Methoden bereit, um mit Arrays, Zeigern, Funktions Zeigern und Verweis Typen zu arbeiten. Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetArrayOrPointerType-Methode](icordebugappdomain2-getarrayorpointertype-method.md)|Ruft ein Array vom angegebenen Typ oder einen Zeiger oder einen Verweis auf den angegebenen Typ ab.|  
|[GetFunctionPointerType](icordebugappdomain2-getfunctionpointertype-method.md)|Ruft einen Zeiger auf eine Funktion ab, die über eine angegebene Signatur verfügt.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
