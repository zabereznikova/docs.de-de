---
title: ISymUnmanagedWriter-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter
helpviewer_keywords: ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 7d6733ec-f081-4166-bc17-de09e16dc304
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f4996f0196df4c2bcf890df6ad972f313403e435
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter-interface"></a>ISymUnmanagedWriter-Schnittstelle
Stellt einen Symbolwriter dar und bietet Methoden zum Definieren von Dokumenten, Sequenzpunkte lexikalischen Gültigkeitsbereiche und Variablen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Abort-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)|Schließt den Symbolwriter ohne dass die Symbole an den Symbolspeicher.|  
|[Close-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)|Schließt den Symbolwriter nach dem Ausführen eines Commits für die Symbole an den Symbolspeicher.|  
|[CloseMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)|Schließt die aktuelle Methode. Nachdem eine Methode geschlossen wurde, können keine weitere Symbole darin definiert werden.|  
|[CloseNamespace-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)|Den zuletzt geöffneten schließt Namespace.|  
|[CloseScope-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)|Schließt den aktuellen lexikalischen Gültigkeitsbereich.|  
|[DefineConstant-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)|Definiert einen Namen für einen konstanten Wert.|  
|[DefineDocument-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definedocument-method.md)|Definiert ein Quelldokument.|  
|[DefineField-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definefield-method.md)|Definiert eine einzelne Variable, die nicht innerhalb einer Methode ist.|  
|[DefineGlobalVariable-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)|Definiert eine einzelne globale Variable.|  
|[DefineLocalVariable-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)|Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.|  
|[DefineParameter-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineparameter-method.md)|Definiert einen einzelnen Parameter in der aktuellen Methode.|  
|[DefineSequencePoints-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definesequencepoints-method.md)|Definiert eine Gruppe von Sequenzpunkten in der aktuellen Methode.|  
|[GetDebugInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)|Gibt die Informationen für einen Compiler den Debug-Verzeichniseintrag im portierbare ausführbare Datei (PE) Dateiheader schreiben erforderlich.|  
|[Initialize-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)|Legt die Metadatenemitter-Schnittstelle mit der dieser Writer zugewiesen werden soll, und den Namen der Ausgabedatei, den die Debugsymbole geschrieben werden.|  
|[Initialize2-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)|Legt die Metadatenemitter-Schnittstelle mit der dieser Writer zugewiesen werden soll, legt den Ausgabedateinamen an die die Debugsymbole geschrieben werden, und legt den endgültigen Speicherort der Programmdatenbankdatei (PDB).|  
|[OpenMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)|Öffnet eine Methode, die in der, die Symbolinformationen ausgegeben wird.|  
|[OpenNamespace-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)|Öffnet einen neuen Namespace.|  
|[OpenScope-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)|Öffnet einen neuen lexikalischen Gültigkeitsbereich in der aktuellen Methode.|  
|[RemapToken-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-remaptoken-method.md)|Benachrichtigt dem Symbolwriter über ein Metadatentoken neu zugeordnet wurde, als die Metadaten ausgegeben wurde.|  
|[SetMethodSourceRange-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setmethodsourcerange-method.md)|Gibt "true" Anfang und Ende einer Methode innerhalb einer Quelldatei.|  
|[SetScopeRange-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)|Definiert den Offsetbereich für den angegebenen lexikalischen Gültigkeitsbereich.|  
|[SetSymAttribute-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setsymattribute-method.md)|Definiert ein benutzerdefiniertes Attribut anhand seines Namens.|  
|[SetUserEntryPoint-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setuserentrypoint-method.md)|Gibt die benutzerdefinierte Methode, die den Einstiegspunkt für dieses Modul ist.|  
|[UsingNamespace-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-usingnamespace-method.md)|Gibt an, dass es sich bei der angegebenen Namen für den vollqualifizierten Namespace im geöffneten lexikalischen Gültigkeitsbereich verwendet wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedWriter2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [ISymUnmanagedWriter3-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
