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
ms.openlocfilehash: 8f0bbd26bde562df5482d167c9d2775e01426f55
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610053"
---
# <a name="isymunmanagedwriter-interface"></a>ISymUnmanagedWriter-Schnittstelle
Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenz Punkten, lexikalischen Bereichen und Variablen bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Abort-Methode](isymunmanagedwriter-abort-method.md)|Schließt den Symbolwriter, ohne die Symbole an den Symbol Speicher zu übergeben.|  
|[Close-Methode](isymunmanagedwriter-close-method.md)|Schließt den Symbolwriter nach dem Commit der Symbole an den Symbol Speicher.|  
|[CloseMethod-Methode](isymunmanagedwriter-closemethod-method.md)|Schließt die aktuelle Methode. Nachdem eine Methode geschlossen wurde, können darin keine weiteren Symbole definiert werden.|  
|[CloseNamespace-Methode](isymunmanagedwriter-closenamespace-method.md)|Schließt den zuletzt geöffneten Namespace.|  
|[CloseScope-Methode](isymunmanagedwriter-closescope-method.md)|Schließt den aktuellen lexikalischen Gültigkeitsbereich.|  
|[DefineConstant-Methode](isymunmanagedwriter-defineconstant-method.md)|Definiert einen Namen für einen konstanten Wert.|  
|[DefineDocument-Methode](isymunmanagedwriter-definedocument-method.md)|Definiert ein Quelldokument.|  
|[DefineField-Methode](isymunmanagedwriter-definefield-method.md)|Definiert eine einzelne Variable, die sich nicht innerhalb einer Methode befindet.|  
|[DefineGlobalVariable-Methode](isymunmanagedwriter-defineglobalvariable-method.md)|Definiert eine einzelne globale Variable.|  
|[DefineLocalVariable-Methode](isymunmanagedwriter-definelocalvariable-method.md)|Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.|  
|[DefineParameter-Methode](isymunmanagedwriter-defineparameter-method.md)|Definiert einen einzelnen Parameter in der aktuellen Methode.|  
|[DefineSequencePoints-Methode](isymunmanagedwriter-definesequencepoints-method.md)|Definiert eine Gruppe von Sequenzpunkten in der aktuellen Methode.|  
|[GetDebugInfo-Methode](isymunmanagedwriter-getdebuginfo-method.md)|Gibt die erforderlichen Informationen zurück, damit ein Compiler den Debugverzeichniseintrag im PE-Dateiheader schreiben muss.|  
|[Initialize-Methode](isymunmanagedwriter-initialize-method.md)|Legt die Metadatenemitter-Schnittstelle fest, der dieser Writer zugeordnet wird, und legt den Namen der Ausgabedatei fest, in die die Debugsymbole geschrieben werden.|  
|[Initialize2-Methode](isymunmanagedwriter-initialize2-method.md)|Legt die Metadatenemitter-Schnittstelle fest, mit der dieser Writer verknüpft wird, legt den Namen der Ausgabedatei fest, in die die Debugsymbole geschrieben werden, und legt den endgültigen Speicherort der Programm Datenbankdatei (PDB-Datei) fest.|  
|[OpenMethod-Methode](isymunmanagedwriter-openmethod-method.md)|Öffnet eine Methode, in die Symbol Informationen ausgegeben werden.|  
|[OpenNamespace-Methode](isymunmanagedwriter-opennamespace-method.md)|Öffnet einen neuen Namespace.|  
|[OpenScope-Methode](isymunmanagedwriter-openscope-method.md)|Öffnet einen neuen lexikalischen Gültigkeitsbereich in der aktuellen Methode.|  
|[RemapToken-Methode](isymunmanagedwriter-remaptoken-method.md)|Benachrichtigt den Symbolwriter, dass ein Metadatentoken neu zugeordnet wurde, während die Metadaten ausgegeben wurden.|  
|[SetMethodSourceRange-Methode](isymunmanagedwriter-setmethodsourcerange-method.md)|Gibt den tatsächlichen Anfang und das tatsächliche Ende einer Methode in einer Quelldatei an.|  
|[SetScopeRange-Methode](isymunmanagedwriter-setscoperange-method.md)|Definiert den Offsetbereich für den angegebenen lexikalischen Gültigkeitsbereich.|  
|[SetSymAttribute-Methode](isymunmanagedwriter-setsymattribute-method.md)|Definiert ein benutzerdefiniertes Attribut basierend auf seinem Namen.|  
|[SetUserEntryPoint-Methode](isymunmanagedwriter-setuserentrypoint-method.md)|Gibt die benutzerdefinierte Methode an, die der Einstiegspunkt für dieses Modul ist.|  
|[UsingNamespace-Methode](isymunmanagedwriter-usingnamespace-method.md)|Gibt an, dass der angegebene voll qualifizierte Namespace Name innerhalb des derzeit geöffneten lexikalischen Gültigkeits Bereichs verwendet wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter2-Schnittstelle](isymunmanagedwriter2-interface.md)
- [ISymUnmanagedWriter3-Schnittstelle](isymunmanagedwriter3-interface.md)
