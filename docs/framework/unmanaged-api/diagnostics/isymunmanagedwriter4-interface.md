---
title: ISymUnmanagedWriter4-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: c2b57897e4f0e8b23337302f344065d79677e0c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725806"
---
# <a name="isymunmanagedwriter4-interface"></a>ISymUnmanagedWriter4-Schnittstelle

ISymUnmanagedWriter4-Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a>Methoden  

 Diese Schnittstelle enthält die folgenden Methoden:  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetDebugInfoWithPadding-Methode](isymunmanagedwriter4-getdebuginfowithpadding-method.md)|Funktioniert genauso wie die [GetDebugInfo-Methode](isymunmanagedwriter-getdebuginfo-method.md) , mit der Ausnahme, dass die Pfad Zeichenfolge nach dem abschließenden NULL-Zeichen mit Nullen aufgefüllt wird, damit die Zeichen folgen Daten eine festgelegte Größe von haben `MAX_PATH` . Padding wird nur angegeben, wenn die Länge der Pfad Zeichenfolge selbst kleiner als ist `MAX_PATH` .<br /><br /> Dadurch wird das Schreiben von Tools erleichtert, die PE-Dateien unterscheiden.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter3-Schnittstelle](isymunmanagedwriter3-interface.md)
