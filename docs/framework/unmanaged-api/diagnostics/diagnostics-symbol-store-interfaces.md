---
title: Diagnosesymbolspeicher-Schnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
ms.openlocfilehash: bdb691570a9a2bf7bd2bb21af500b06c10b0bc53
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448526"
---
# <a name="diagnostics-symbol-store-interfaces"></a>Diagnosesymbolspeicher-Schnittstellen
In diesem Thema werden die nicht verwalteten Schnittstellen beschrieben, mit denen ein Compiler Symbol Informationen generieren kann, die von einem Debugger verwendet werden können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [IBindingDisplay-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 Stellt Methoden bereit, die aktuelle Bindungs Informationen zur ausgelaufenden Anwendung anzeigen.  
  
 [IDebugAutoAttach-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 Definiert die Schnittstelle für eine vom Server aufgerufene automatische Debugger-Anfügung.  
  
 [INotifyConnection2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 Deklariert Methoden zum Registrieren und Aufheben der Registrierung einer Verbindungs Benachrichtigungs Quelle.  
  
 [INotifySink2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 Deklariert Methoden für Senke Benachrichtigung.  
  
 [INotifySource2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 Deklariert eine Methode zum Festlegen von Benachrichtigungs filtern.  
  
 [ISymENCUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 Enthält Informationen für das Feature "Bearbeiten und Fortfahren".  
  
 [ISymUnmanagedAsyncMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 Diese Schnittstelle ist die Lese Ergänzung zur [isymunmanagedasyncmethodpropertieswriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).  
  
 [ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 Ermöglicht die Definition Optionaler Async-Methoden Informationen pro Methoden Symbol. Muss mit einer geöffneten Methode (d. h. zwischen Aufrufen der [OpenMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)und der [CloseMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)) verwenden.  
  
 [ISymUnmanagedBinder-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 Stellt einen Symbol Binder für nicht verwalteten Code dar.  
  
 [ISymUnmanagedBinder2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 Stellt einen Symbol Binder für nicht verwalteten Code dar und erweitert die `ISymUnmanagedBinder`-Schnittstelle.  
  
 [ISymUnmanagedBinder3-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 Stellt einen Symbol Binder für nicht verwalteten Code dar und erweitert die `ISymUnmanagedBinder`-Schnittstelle.  
  
 [ISymUnmanagedConstant-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 Ermöglicht den Zugriff auf nicht verwaltete Konstanten.  
  
 [ISymUnmanagedDispose-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 Gibt nicht verwaltete Ressourcen frei.  
  
 [ISymUnmanagedDocument-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 Stellt ein Dokument dar, auf das von einem Symbolspeicher verwiesen wird.  
  
 [ISymUnmanagedDocumentWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 Stellt Methoden zum Schreiben in ein Dokument bereit, auf das ein Symbolspeicher verweist.  
  
 [ISymUnmanagedENCUpdate-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 Stellt Methoden für die Funktion "Bearbeiten und Fortfahren" bereit.  
  
 [ISymUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 Stellt eine Methode im Symbol Speicher dar.  
  
 [ISymUnmanagedNamespace-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 Stellt einen Namespace dar.  
  
 [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 Stellt einen Symbol Reader dar, der den Zugriff auf Dokumente, Methoden und Variablen in einem Symbol Speicher ermöglicht.  
  
 [ISymUnmanagedReader2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token und eine Bearbeitungs-und Kopier Versionsnummer angegeben ist.  
  
 [ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 Stellt Methoden bereit, die Symbol Suchinformationen erhalten.  
  
 [ISymUnmanagedScope-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.  
  
 [ISymUnmanagedScope2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar und erweitert die `ISymUnmanagedScope`-Schnittstelle um Methoden, die Informationen zu konstanten erhalten, die innerhalb des Bereichs definiert sind.  
  
 [ISymUnmanagedSourceServerModule-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 Stellt Quell Serverdaten für ein Modul bereit.  
  
 [ISymUnmanagedSymbolSearchInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 Stellt Methoden bereit, die Informationen über den Suchpfad erhalten.  
  
 [ISymUnmanagedVariable-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 Stellt eine Variable dar, z. b. einen Parameter, eine lokale Variable oder ein Feld.  
  
 [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenz Punkten, lexikalischen Bereichen und Variablen bereit.  
  
 [ISymUnmanagedWriter2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenz Punkten, lexikalischen Bereichen und Variablen bereit. Erweitert die `ISymUnmanagedWriter`-Schnittstelle.  
  
 [ISymUnmanagedWriter3-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenz Punkten, lexikalischen Bereichen und Variablen bereit. Erweitert die `ISymUnmanagedWriter`-Schnittstelle.  
  
 [ISymUnmanagedWriter4-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 ISymUnmanagedWriter4-Schnittstelle.  
  
 [ISymUnmanagedWriter5-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 ISymUnmanagedWriter5-Schnittstelle.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Diagnosesymbolspeicher-Enumerationen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [Diagnosesymbolspeicher-Strukturen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
