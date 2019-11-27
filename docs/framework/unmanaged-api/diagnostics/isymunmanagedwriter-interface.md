---
title: ISymUnmanagedWriter-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter
helpviewer_keywords:
- ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 7d6733ec-f081-4166-bc17-de09e16dc304
topic_type:
- apiref
ms.openlocfilehash: fc19ee25e903046daef376e4297c8feb3d01ad47
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427939"
---
# <a name="isymunmanagedwriter-interface"></a>ISymUnmanagedWriter-Schnittstelle
Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenz Punkten, lexikalischen Bereichen und Variablen bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Abort-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)|Schließt den Symbolwriter, ohne die Symbole an den Symbol Speicher zu übergeben.|  
|[Close-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)|Schließt den Symbolwriter nach dem Commit der Symbole an den Symbol Speicher.|  
|[CloseMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)|Schließt die aktuelle Methode. Nachdem eine Methode geschlossen wurde, können darin keine weiteren Symbole definiert werden.|  
|[CloseNamespace-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)|Schließt den zuletzt geöffneten Namespace.|  
|[CloseScope-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)|Schließt den aktuellen lexikalischen Gültigkeitsbereich.|  
|[DefineConstant-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)|Definiert einen Namen für einen konstanten Wert.|  
|[DefineDocument-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definedocument-method.md)|Definiert ein Quelldokument.|  
|[DefineField-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definefield-method.md)|Definiert eine einzelne Variable, die sich nicht innerhalb einer Methode befindet.|  
|[DefineGlobalVariable-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)|Definiert eine einzelne globale Variable.|  
|[DefineLocalVariable-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)|Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.|  
|[DefineParameter-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineparameter-method.md)|Definiert einen einzelnen Parameter in der aktuellen Methode.|  
|[DefineSequencePoints-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definesequencepoints-method.md)|Definiert eine Gruppe von Sequenzpunkten in der aktuellen Methode.|  
|[GetDebugInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)|Gibt die erforderlichen Informationen zurück, damit ein Compiler den Debugverzeichniseintrag im PE-Dateiheader schreiben muss.|  
|[Initialize-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)|Legt die Metadatenemitter-Schnittstelle fest, der dieser Writer zugeordnet wird, und legt den Namen der Ausgabedatei fest, in die die Debugsymbole geschrieben werden.|  
|[Initialize2-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)|Legt die Metadatenemitter-Schnittstelle fest, mit der dieser Writer verknüpft wird, legt den Namen der Ausgabedatei fest, in die die Debugsymbole geschrieben werden, und legt den endgültigen Speicherort der Programm Datenbankdatei (PDB-Datei) fest.|  
|[OpenMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)|Öffnet eine Methode, in die Symbol Informationen ausgegeben werden.|  
|[OpenNamespace-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)|Öffnet einen neuen Namespace.|  
|[OpenScope-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)|Öffnet einen neuen lexikalischen Gültigkeitsbereich in der aktuellen Methode.|  
|[RemapToken-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-remaptoken-method.md)|Benachrichtigt den Symbolwriter, dass ein Metadatentoken neu zugeordnet wurde, während die Metadaten ausgegeben wurden.|  
|[SetMethodSourceRange-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setmethodsourcerange-method.md)|Gibt den tatsächlichen Start und das Ende einer Methode in einer Quelldatei an.|  
|[SetScopeRange-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)|Definiert den Offsetbereich für den angegebenen lexikalischen Gültigkeitsbereich.|  
|[SetSymAttribute-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setsymattribute-method.md)|Definiert ein benutzerdefiniertes Attribut basierend auf seinem Namen.|  
|[SetUserEntryPoint-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setuserentrypoint-method.md)|Gibt die benutzerdefinierte Methode an, die der Einstiegspunkt für dieses Modul ist.|  
|[UsingNamespace-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-usingnamespace-method.md)|Gibt an, dass der angegebene voll qualifizierte Namespace Name innerhalb des derzeit geöffneten lexikalischen Gültigkeits Bereichs verwendet wird.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [ISymUnmanagedWriter3-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
