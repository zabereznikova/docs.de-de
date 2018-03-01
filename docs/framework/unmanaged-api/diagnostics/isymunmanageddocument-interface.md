---
title: ISymUnmanagedDocument-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e176679b4fdb4d0a2c5c4fbcbc09403e45f1ad1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocument-interface"></a>ISymUnmanagedDocument-Schnittstelle
Stellt ein Dokument dar, auf das von einem Symbolspeicher verwiesen wird. Ein Dokument wird durch eine URL (uniform Resource Locator) und einen Dokumenttyp GUID definiert. Sie können das Dokument unabhängig davon, wie sie mithilfe der URL gespeichert werden und Dokumenttyp-GUID. Sie können die Quelle des Dokuments im Symbolspeicher gespeichert und über diese Schnittstelle abrufen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[FindClosestLine-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|Gibt die nächste Zeile, die ein Sequenzpunkt ist, wobei eine angegebene Zeile in diesem Dokument, das nicht unbedingt ein Sequenzpunkt zurück.|  
|[GetCheckSum-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|Ruft die Prüfsumme ab.|  
|[GetCheckSumAlgorithmId-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|Ruft den Bezeichner des Prüfsummenalgorithmus ab oder gibt eine GUID mit Nullen zurück, wenn keine Prüfsumme vorhanden ist.|  
|[GetDocumentType-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|Ruft den Dokumenttyp dieses Dokuments ab.|  
|[GetLanguage-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|Ruft die Sprachen-ID dieses Dokuments ab.|  
|[GetLanguageVendor-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|Ruft den Compilerhersteller dieses Dokuments ab.|  
|[GetSourceLength-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|Ruft die Länge der eingebetteten Quelle in Byte ab.|  
|[GetSourceRange-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|Gibt den angegebenen Bereich der eingebetteten Quelle in den angegebenen Puffer zurück.|  
|[GetURL-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|Gibt die URL für dieses Dokument zurück.|  
|[HasEmbeddedSource-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|Gibt `true` , wenn das Dokument die Quelle in den Debugsymbolen; eingebettet ist, andernfalls `false`.|  
  
## <a name="see-also"></a>Siehe auch  
 [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
