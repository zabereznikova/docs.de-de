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
ms.openlocfilehash: 83c683e1f60f13f7cee4ddc6fe5af5a94e36eb93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692175"
---
# <a name="isymunmanageddocument-interface"></a>ISymUnmanagedDocument-Schnittstelle

Stellt ein Dokument dar, auf das von einem Symbolspeicher verwiesen wird. Ein Dokument wird durch eine URL (Uniform Resource Serverlocatorpunkt) und eine Dokumenttyp-GUID definiert. Sie können das Dokument unabhängig davon, wie es gespeichert wird, mithilfe der URL-und Dokumenttyp-GUID suchen. Sie können die Dokument Quelle im Symbol Speicher speichern und über diese Schnittstelle abrufen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[FindClosestLine-Methode](isymunmanageddocument-findclosestline-method.md)|Gibt die nächste Zeile zurück, bei der es sich um einen Sequenz Punkt handelt, bei dem eine Zeile in diesem Dokument angegeben ist, die ein Sequenz Punkt sein kann.|  
|[GetCheckSum-Methode](isymunmanageddocument-getchecksum-method.md)|Ruft die Prüfsumme ab.|  
|[GetCheckSumAlgorithmId-Methode](isymunmanageddocument-getchecksumalgorithmid-method.md)|Ruft den Prüfsummen Algorithmus-Bezeichner ab oder gibt eine GUID aller Nullen zurück, wenn keine Prüfsumme vorhanden ist.|  
|[GetDocumentType-Methode](isymunmanageddocument-getdocumenttype-method.md)|Ruft den Dokumenttyp dieses Dokuments ab.|  
|[GetLanguage-Methode](isymunmanageddocument-getlanguage-method.md)|Ruft den sprach Bezeichner für dieses Dokument ab.|  
|[GetLanguageVendor-Methode](isymunmanageddocument-getlanguagevendor-method.md)|Ruft den Hersteller der Sprache dieses Dokuments ab.|  
|[GetSourceLength-Methode](isymunmanageddocument-getsourcelength-method.md)|Ruft die Länge der eingebetteten Quelle in Bytes ab.|  
|[GetSourceRange-Methode](isymunmanageddocument-getsourcerange-method.md)|Gibt den angegebenen Bereich der eingebetteten Quelle in den angegebenen Puffer zurück.|  
|[GetURL-Methode](isymunmanageddocument-geturl-method.md)|Gibt die URL für dieses Dokument zurück.|  
|[HasEmbeddedSource-Methode](isymunmanageddocument-hasembeddedsource-method.md)|Gibt zurück, `true` Wenn das Dokument in die Debugsymbole eingebettet ist; andernfalls wird zurückgegeben `false` .|  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
