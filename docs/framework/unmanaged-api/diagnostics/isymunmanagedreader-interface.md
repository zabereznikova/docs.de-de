---
title: ISymUnmanagedReader-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
ms.openlocfilehash: b372021fcda39d9973d96a9c39e93e38617887a6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615461"
---
# <a name="isymunmanagedreader-interface"></a>ISymUnmanagedReader-Schnittstelle
Stellt einen Symbol Reader dar, der den Zugriff auf Dokumente, Methoden und Variablen in einem Symbol Speicher ermöglicht.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetDocument-Methode](isymunmanagedreader-getdocument-method.md)|Sucht ein Dokument.|  
|[GetDocuments-Methode](isymunmanagedreader-getdocuments-method.md)|Gibt ein Array aller im Symbol Speicher definierten Dokumente zurück.|  
|[GetDocumentVersion-Methode](isymunmanagedreader-getdocumentversion-method.md)|Ruft die angegebene Version des angegebenen Dokuments ab.|  
|[GetGlobalVariables-Methode](isymunmanagedreader-getglobalvariables-method.md)|Gibt alle globalen Variablen zurück.|  
|[GetMethod-Methode](isymunmanagedreader-getmethod-method.md)|Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token angegeben wird.|  
|[GetMethodByVersion-Methode](isymunmanagedreader-getmethodbyversion-method.md)|Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token und eine Bearbeitungs-und Kopier Versionsnummer angegeben ist.|  
|[GetMethodFromDocumentPosition-Methode](isymunmanagedreader-getmethodfromdocumentposition-method.md)|Gibt die Methode zurück, die den Breakpoint an der angegebenen Position in einem Dokument enthält.|  
|[GetMethodsFromDocumentPosition-Methode](isymunmanagedreader-getmethodsfromdocumentposition-method.md)|Gibt ein Array von-Methoden zurück, von denen jede den Haltepunkt an der angegebenen Position in einem Dokument enthält.|  
|[GetMethodVersion-Methode](isymunmanagedreader-getmethodversion-method.md)|Ruft die Methoden Version ab.|  
|[GetNamespaces-Methode](isymunmanagedreader-getnamespaces-method.md)|Ruft die Namespaces ab, die im globalen Gültigkeitsbereich innerhalb dieses Symbol Speicher definiert sind.|  
|[GetSymAttribute-Methode](isymunmanagedreader-getsymattribute-method.md)|Ruft ein benutzerdefiniertes Attribut basierend auf seinem Namen ab.|  
|[GetSymbolStoreFileName-Methode](isymunmanagedreader-getsymbolstorefilename-method.md)|Gibt den Dateinamen des Symbol Speicher auf dem Datenträger an.|  
|[GetUserEntryPoint-Methode](isymunmanagedreader-getuserentrypoint-method.md)|Gibt die Methode zurück, die ggf. als Benutzer Einstiegspunkt für das Modul angegeben wurde.|  
|[GetVariables-Methode](isymunmanagedreader-getvariables-method.md)|Gibt eine nicht lokale Variable zurück, wenn Ihr übergeordnetes Element und der Name angegeben sind.|  
|[Initialize-Methode](isymunmanagedreader-initialize-method.md)|Initialisiert den Symbol Reader mit der metadatenimporterschnittstelle, der dieser Reader zugeordnet ist, zusammen mit dem Dateinamen des Moduls.|  
|[ReplaceSymbolStore-Methode](isymunmanagedreader-replacesymbolstore-method.md)|Ersetzt den vorhandenen Symbolspeicher durch einen Deltasymbolspeicher.|  
|[UpdateSymbolStore-Methode](isymunmanagedreader-updatesymbolstore-method.md)|Aktualisiert den vorhandenen Symbolspeicher mit einem Deltasymbolspeicher.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedReader2-Schnittstelle](isymunmanagedreader2-interface.md)
