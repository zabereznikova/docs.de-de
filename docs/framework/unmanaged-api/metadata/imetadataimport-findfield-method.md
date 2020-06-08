---
title: IMetaDataImport::FindField-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
ms.openlocfilehash: 11ea6e468909ea42e38bdc7b76c60c460c98025e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503665"
---
# <a name="imetadataimportfindfield-method"></a>IMetaDataImport::FindField-Methode
Ruft einen Zeiger auf das FieldDef-Token für das Feld ab, das durch den angegebenen eingeschlossen ist <xref:System.Type> und über den angegebenen Namen und die angegebene Metadatensignatur verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 in Das TypeDef-Token für die Klasse oder Schnittstelle, die das Feld einschließt, nach dem gesucht werden soll. Wenn dieser Wert ist `mdTokenNil` , wird die Suche für eine globale Variable durchgeführt.  
  
 `szName`  
 in Der Name des Felds, nach dem gesucht werden soll.  
  
 `pvSigBlob`  
 in Ein Zeiger auf die binäre Metadatensignatur des Felds.  
  
 `cbSigBlob`  
 in Die Größe von in Bytes `pvSigBlob` .  
  
 `pmb`  
 vorgenommen Ein Zeiger auf das übereinstimmende FieldDef-Token.  
  
## <a name="remarks"></a>Bemerkungen  
 Sie geben das Feld mit der einschließenden Klasse oder Schnittstelle ( `td` ), dem Namen ( `szName` ) und optional der Signatur ( `pvSigBlob` ) an.  
  
 Die an über gegebene Signatur `FindField` muss im aktuellen Gültigkeitsbereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind. Eine Signatur kann ein Token einbetten, das den einschließenden Klassen-oder Werttyp identifiziert. (Das Token ist ein Index in der lokalen Tabelle "Typedef"). Sie können keine Lauf Zeit Signatur außerhalb des Kontexts des aktuellen Bereichs erstellen und diese Signatur als Eingabe für verwenden `FindField` .  
  
 `FindField`sucht nur Felder, die direkt in der Klasse oder Schnittstelle definiert wurden. geerbte Felder werden nicht gefunden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
