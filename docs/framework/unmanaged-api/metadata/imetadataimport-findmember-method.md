---
title: IMetaDataImport::FindMember-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
ms.openlocfilehash: fce4f3875fbdb110134d6b7f684eff40821f6bdd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503678"
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember-Methode
Ruft einen Zeiger auf das mitgliedtendef-Token für das Feld oder die Methode ab, das durch den angegebenen eingeschlossen ist <xref:System.Type> und den angegebenen Namen und die angegebene Metadatensignatur aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 in Das TypeDef-Token für die Klasse oder Schnittstelle, die den Member einschließt, nach dem gesucht werden soll. Wenn dieser Wert ist `mdTokenNil` , wird die Suche für eine globale Variable oder globale Funktion durchgeführt.  
  
 `szName`  
 in Der Name des zu suchenden Members.  
  
 `pvSigBlob`  
 in Ein Zeiger auf die binäre Metadatensignatur des Members.  
  
 `cbSigBlob`  
 in Die Größe von in Bytes `pvSigBlob` .  
  
 `pmb`  
 vorgenommen Ein Zeiger auf das übereinstimmende mitgliedtdef-Token.  
  
## <a name="remarks"></a>Bemerkungen  
 Sie geben den Member mit der einschließenden Klasse oder Schnittstelle ( `td` ), dem Namen ( `szName` ) und optional der Signatur ( `pvSigBlob` ) an. In einer Klasse oder Schnittstelle können mehrere Member mit demselben Namen vorhanden sein. Übergeben Sie in diesem Fall die Signatur des Members, um die eindeutige Entsprechung zu finden.  
  
 Die an über gegebene Signatur `FindMember` muss im aktuellen Gültigkeitsbereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind. Eine Signatur kann ein Token einbetten, das den einschließenden Klassen-oder Werttyp identifiziert. Das Token ist ein Index in der lokalen Tabelle "Typedef". Sie können keine Lauf Zeit Signatur außerhalb des Kontexts des aktuellen Gültigkeits Bereichs erstellen und diese Signatur als Eingabe für die Eingabe verwenden `FindMember` .  
  
 `FindMember`sucht nur Elemente, die direkt in der Klasse oder Schnittstelle definiert wurden. geerbte Member werden nicht gefunden.  
  
> [!NOTE]
> `FindMember`ist eine Hilfsmethode. Es wird [IMetaDataImport:: FindMethod](imetadataimport-findmethod-method.md); aufgerufen. Wenn dieser Aufruf keine Entsprechung findet, `FindMember` ruft [IMetaDataImport:: FindField](imetadataimport-findfield-method.md)auf.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
