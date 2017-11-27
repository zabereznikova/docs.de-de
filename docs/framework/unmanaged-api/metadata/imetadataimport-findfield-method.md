---
title: IMetaDataImport::FindField-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindField
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2178f8738ca510fb2163c1043dd94ebcb7043904
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindfield-method"></a>IMetaDataImport::FindField-Methode
Ruft einen Zeiger auf das FieldDef token für das Feld, das eingeschlossen ist durch das angegebene <xref:System.Type> und den angegebenen Namen und Metadaten aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `td`  
 [in] Das TypeDef-Token für die Klasse oder Schnittstelle, die Suche nach Feld einschließt. Wenn dieser Wert ist `mdTokenNil`, erfolgt die Suche für eine globale Variable.  
  
 `szName`  
 [in] Der Name des zu suchenden Felds.  
  
 `pvSigBlob`  
 [in] Ein Zeiger auf die binäre Metadatensignatur des Felds.  
  
 `cbSigBlob`  
 [in] Die Größe in Bytes des `pvSigBlob`.  
  
 `pmb`  
 [out] Ein Zeiger auf das übereinstimmende FieldDef-Token.  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie das Feld mit der einschließenden Klasse oder Schnittstelle (`td`), seinen Namen (`szName`), und optional die Signatur (`pvSigBlob`).  
  
 Die Signatur zu übergeben, um `FindField` muss wurden im aktuellen Bereich generiert wurde, da Signaturen an einen bestimmten Bereich gebunden sind. Eine Signatur kann ein Token einbetten, die die einschließende Klasse oder der angegebene Werttyp identifiziert. (Das Token ist ein Index in die lokale TypeDef-Tabelle). Sie können keine Laufzeit-Signatur im Kontext des aktuellen Gültigkeitsbereichs erstellen und verwenden Sie diese Signatur als Eingabe für `FindField`.  
  
 `FindField`Sucht nur Felder, die direkt in der Klasse oder Schnittstelle definiert wurden. Es werden geerbte Felder nicht gefunden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
