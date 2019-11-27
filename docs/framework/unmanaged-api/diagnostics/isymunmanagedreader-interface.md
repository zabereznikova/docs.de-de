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
ms.openlocfilehash: 7ae978f5d2c9f7e90f4549c15a3935b441eabf04
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434012"
---
# <a name="isymunmanagedreader-interface"></a>ISymUnmanagedReader-Schnittstelle
Stellt einen Symbol Reader dar, der den Zugriff auf Dokumente, Methoden und Variablen in einem Symbol Speicher ermöglicht.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetDocument-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|Sucht ein Dokument.|  
|[GetDocuments-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|Gibt ein Array aller im Symbol Speicher definierten Dokumente zurück.|  
|[GetDocumentVersion-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|Ruft die angegebene Version des angegebenen Dokuments ab.|  
|[GetGlobalVariables-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|Gibt alle globalen Variablen zurück.|  
|[GetMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token angegeben wird.|  
|[GetMethodByVersion-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|Ruft eine Symbol Lesemethode ab, wenn ein Methoden Token und eine Bearbeitungs-und Kopier Versionsnummer angegeben ist.|  
|[GetMethodFromDocumentPosition-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|Gibt die Methode zurück, die den Breakpoint an der angegebenen Position in einem Dokument enthält.|  
|[GetMethodsFromDocumentPosition-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|Gibt ein Array von-Methoden zurück, von denen jede den Haltepunkt an der angegebenen Position in einem Dokument enthält.|  
|[GetMethodVersion-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|Ruft die Methoden Version ab.|  
|[GetNamespaces-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|Ruft die Namespaces ab, die im globalen Gültigkeitsbereich innerhalb dieses Symbol Speicher definiert sind.|  
|[GetSymAttribute-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|Ruft ein benutzerdefiniertes Attribut basierend auf seinem Namen ab.|  
|[GetSymbolStoreFileName-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|Gibt den Dateinamen des Symbol Speicher auf dem Datenträger an.|  
|[GetUserEntryPoint-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|Gibt die Methode zurück, die ggf. als Benutzer Einstiegspunkt für das Modul angegeben wurde.|  
|[GetVariables-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|Gibt eine nicht lokale Variable zurück, wenn Ihr übergeordnetes Element und der Name angegeben sind.|  
|[Initialize-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|Initialisiert den Symbol Reader mit der metadatenimporterschnittstelle, der dieser Reader zugeordnet ist, zusammen mit dem Dateinamen des Moduls.|  
|[ReplaceSymbolStore-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|Ersetzt den vorhandenen Symbolspeicher durch einen Deltasymbolspeicher.|  
|[UpdateSymbolStore-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|Aktualisiert den vorhandenen Symbolspeicher mit einem Deltasymbolspeicher.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedReader2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
