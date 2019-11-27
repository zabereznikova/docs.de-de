---
title: ISymUnmanagedDocument-Schnittstelle
ms.date: 03/30/2017
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
ms.openlocfilehash: 3fa7b6b19d81e374cdb09b07ec181a7f4249a5eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449093"
---
# <a name="isymunmanageddocument-interface"></a>ISymUnmanagedDocument-Schnittstelle
Stellt ein Dokument dar, auf das von einem Symbolspeicher verwiesen wird. Ein Dokument wird durch eine URL (Uniform Resource Serverlocatorpunkt) und eine Dokumenttyp-GUID definiert. Sie können das Dokument unabhängig davon, wie es gespeichert wird, mithilfe der URL-und Dokumenttyp-GUID suchen. Sie können die Dokument Quelle im Symbol Speicher speichern und über diese Schnittstelle abrufen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[FindClosestLine-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|Gibt die nächste Zeile zurück, bei der es sich um einen Sequenz Punkt handelt, bei dem eine Zeile in diesem Dokument angegeben ist, die ein Sequenz Punkt sein kann.|  
|[GetCheckSum-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|Ruft die Prüfsumme ab.|  
|[GetCheckSumAlgorithmId-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|Ruft den Prüfsummen Algorithmus-Bezeichner ab oder gibt eine GUID aller Nullen zurück, wenn keine Prüfsumme vorhanden ist.|  
|[GetDocumentType-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|Ruft den Dokumenttyp dieses Dokuments ab.|  
|[GetLanguage-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|Ruft den sprach Bezeichner für dieses Dokument ab.|  
|[GetLanguageVendor-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|Ruft den Hersteller der Sprache dieses Dokuments ab.|  
|[GetSourceLength-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|Ruft die Länge der eingebetteten Quelle in Bytes ab.|  
|[GetSourceRange-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|Gibt den angegebenen Bereich der eingebetteten Quelle in den angegebenen Puffer zurück.|  
|[GetURL-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|Gibt die URL für dieses Dokument zurück.|  
|[HasEmbeddedSource-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|Gibt `true` zurück, wenn das Dokument über eine in den Debugsymbolen eingebettete Quelle verfügt. Andernfalls wird `false`zurückgegeben.|  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
