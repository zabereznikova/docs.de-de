---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: cfc6c22558cee780823c8cca0c36b883147e9496
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614642"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a>ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode
Funktioniert genauso wie die [GetDebugInfo-Methode](isymunmanagedwriter-getdebuginfo-method.md) , mit der Ausnahme, dass die Pfad Zeichenfolge nach dem abschließenden NULL-Zeichen mit Nullen aufgefüllt wird, damit die Zeichen folgen Daten eine festgelegte Größe von haben `MAX_PATH` . Padding wird nur angegeben, wenn die Länge der Pfad Zeichenfolge selbst kleiner als ist `MAX_PATH` .  
  
 Dadurch wird das Schreiben von Tools erleichtert, die PE-Dateien unterscheiden.  
  
## <a name="syntax"></a>Syntax  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>Parameter  
  
|Parameter|BESCHREIBUNG|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt `HRESULT` zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter4-Schnittstelle](isymunmanagedwriter4-interface.md)
