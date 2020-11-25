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
ms.openlocfilehash: e376544a9d428ce5110a7e38b92a8e830f574664
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725182"
---
# <a name="diagnostics-symbol-store-interfaces"></a>Diagnosesymbolspeicher-Schnittstellen

In diesem Thema werden die nicht verwalteten Schnittstellen beschrieben, mit denen ein Compiler Symbol Informationen generieren kann, die von einem Debugger verwendet werden können.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [IBindingDisplay-Schnittstelle](ibindingdisplay-interface.md)  
 Stellt Methoden bereit, die aktuelle Bindungs Informationen zur ausgelaufenden Anwendung anzeigen.  
  
 [IDebugAutoAttach-Schnittstelle](idebugautoattach-interface.md)  
 Definiert die Schnittstelle für eine vom Server aufgerufene automatische Debugger-Anfügung.  
  
 [INotifyConnection2-Schnittstelle](inotifyconnection2-interface.md)  
 Deklariert Methoden zum Registrieren und Aufheben der Registrierung einer Verbindungs Benachrichtigungs Quelle.  
  
 [INotifySink2-Schnittstelle](inotifysink2-interface.md)  
 Deklariert Methoden für Senke Benachrichtigung.  
  
 [INotifySource2-Schnittstelle](inotifysource2-interface.md)  
 Deklariert eine Methode zum Festlegen von Benachrichtigungs filtern.  
  
 [ISymENCUnmanagedMethod-Schnittstelle](isymencunmanagedmethod-interface.md)  
 Enthält Informationen für das Feature "Bearbeiten und Fortfahren".  
  
 [ISymUnmanagedAsyncMethod-Schnittstelle](isymunmanagedasyncmethod-interface.md)  
 Diese Schnittstelle ist die Lese Ergänzung zur [isymunmanagedasyncmethodpropertieswriter-Schnittstelle](isymunmanagedasyncmethodpropertieswriter-interface.md).  
  
 [ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 Ermöglicht die Definition Optionaler Async-Methoden Informationen pro Methoden Symbol. Muss mit einer geöffneten Methode (d. h. zwischen Aufrufen der [OpenMethod-Methode](isymunmanagedwriter-openmethod-method.md)und der [CloseMethod-Methode](isymunmanagedwriter-closemethod-method.md)) verwenden.  
  
 [ISymUnmanagedBinder-Schnittstelle](isymunmanagedbinder-interface.md)  
 Stellt einen Symbolbinder für nicht verwalteten Code dar.  
  
 [ISymUnmanagedBinder2-Schnittstelle](isymunmanagedbinder2-interface.md)  
 Stellt einen Symbol Binder für nicht verwalteten Code dar und erweitert die- `ISymUnmanagedBinder` Schnittstelle.  
  
 [ISymUnmanagedBinder3-Schnittstelle](isymunmanagedbinder3-interface.md)  
 Stellt einen Symbol Binder für nicht verwalteten Code dar und erweitert die- `ISymUnmanagedBinder` Schnittstelle.  
  
 [ISymUnmanagedConstant-Schnittstelle](isymunmanagedconstant-interface.md)  
 Ermöglicht den Zugriff auf nicht verwaltete Konstanten.  
  
 [ISymUnmanagedDispose-Schnittstelle](isymunmanageddispose-interface.md)  
 Gibt nicht verwaltete Ressourcen frei.  
  
 [ISymUnmanagedDocument-Schnittstelle](isymunmanageddocument-interface.md)  
 Stellt ein Dokument dar, auf das von einem Symbolspeicher verwiesen wird.  
  
 [ISymUnmanagedDocumentWriter-Schnittstelle](isymunmanageddocumentwriter-interface.md)  
 Stellt Methoden zum Schreiben in ein Dokument bereit, auf das ein Symbolspeicher verweist.  
  
 [ISymUnmanagedENCUpdate-Schnittstelle](isymunmanagedencupdate-interface.md)  
 Stellt Methoden für die Funktion "Bearbeiten und Fortfahren" bereit.  
  
 [ISymUnmanagedMethod-Schnittstelle](isymunmanagedmethod-interface.md)  
 Stellt eine Methode im Symbolspeicher dar.  
  
 [ISymUnmanagedNamespace-Schnittstelle](isymunmanagednamespace-interface.md)  
 Stellt einen Namespace dar.  
  
 [ISymUnmanagedReader-Schnittstelle](isymunmanagedreader-interface.md)  
 Stellt einen Symbolreader dar, der Zugriff auf Dokumente, Methoden und Variablen innerhalb eines Symbolspeichers bietet.  
  
 [ISymUnmanagedReader2-Schnittstelle](isymunmanagedreader2-interface.md)  
 Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token und eine Bearbeitungs-und Kopier Versionsnummer angegeben ist.  
  
 [ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle](isymunmanagedreadersymbolsearchinfo-interface.md)  
 Stellt Methoden bereit, die Symbol Suchinformationen erhalten.  
  
 [ISymUnmanagedScope-Schnittstelle](isymunmanagedscope-interface.md)  
 Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.  
  
 [ISymUnmanagedScope2-Schnittstelle](isymunmanagedscope2-interface.md)  
 Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar und erweitert die- `ISymUnmanagedScope` Schnittstelle um Methoden, die Informationen zu Konstanten, die innerhalb des Bereichs definiert sind, erhalten.  
  
 [ISymUnmanagedSourceServerModule-Schnittstelle](isymunmanagedsourceservermodule-interface.md)  
 Stellt Quell Serverdaten für ein Modul bereit.  
  
 [ISymUnmanagedSymbolSearchInfo-Schnittstelle](isymunmanagedsymbolsearchinfo-interface.md)  
 Stellt Methoden bereit, die Informationen über den Suchpfad erhalten.  
  
 [ISymUnmanagedVariable-Schnittstelle](isymunmanagedvariable-interface.md)  
 Stellt eine Variable dar (z. B. einen Parameter, eine lokale Variable oder ein Feld).  
  
 [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)  
 Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenzpunkten, lexikalischen Bereichen und Variablen bereit.  
  
 [ISymUnmanagedWriter2-Schnittstelle](isymunmanagedwriter2-interface.md)  
 Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenzpunkten, lexikalischen Bereichen und Variablen bereit. Erweitert die- `ISymUnmanagedWriter` Schnittstelle.  
  
 [ISymUnmanagedWriter3-Schnittstelle](isymunmanagedwriter3-interface.md)  
 Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenzpunkten, lexikalischen Bereichen und Variablen bereit. Erweitert die- `ISymUnmanagedWriter` Schnittstelle.  
  
 [ISymUnmanagedWriter4-Schnittstelle](isymunmanagedwriter4-interface.md)  
 ISymUnmanagedWriter4-Schnittstelle.  
  
 [ISymUnmanagedWriter5-Schnittstelle](isymunmanagedwriter5-interface.md)  
 ISymUnmanagedWriter5-Schnittstelle.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Diagnosesymbolspeicher-Enumerationen](diagnostics-symbol-store-enumerations.md)  
  
 [Diagnosesymbolspeicher-Strukturen](diagnostics-symbol-store-structures.md)  
  
 [Debuggen](../debugging/index.md)
