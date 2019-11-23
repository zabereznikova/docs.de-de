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
Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetDocument-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|Finds a document.|  
|[GetDocuments-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|Returns an array of all the documents defined in the symbol store.|  
|[GetDocumentVersion-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|Gets the specified version of the specified document.|  
|[GetGlobalVariables-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|Returns all global variables.|  
|[GetMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|Gets a symbol reader method, given a method token.|  
|[GetMethodByVersion-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|Gets a symbol reader method, given a method token and an edit-and-copy version number.|  
|[GetMethodFromDocumentPosition-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|Returns the method that contains the breakpoint at the given position in a document.|  
|[GetMethodsFromDocumentPosition-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|Returns an array of methods, each of which contains the breakpoint at the given position in a document.|  
|[GetMethodVersion-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|Gets the method version.|  
|[GetNamespaces-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|Gets the namespaces defined at global scope within this symbol store.|  
|[GetSymAttribute-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|Gets a custom attribute based upon its name.|  
|[GetSymbolStoreFileName-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|Provides the on-disk file name of the symbol store.|  
|[GetUserEntryPoint-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|Returns the method that was specified as the user entry point for the module, if any.|  
|[GetVariables-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|Return a non-local variable, given its parent and name.|  
|[Initialize-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.|  
|[ReplaceSymbolStore-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|Ersetzt den vorhandenen Symbolspeicher durch einen Deltasymbolspeicher.|  
|[UpdateSymbolStore-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|Aktualisiert den vorhandenen Symbolspeicher mit einem Deltasymbolspeicher.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedReader2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
