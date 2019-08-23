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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4eefb7ec1e7d0d130ec64531a59d1d5bbce04963
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968919"
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember-Methode
Ruft einen Zeiger auf das mitgliedtendef-Token für das Feld oder die Methode ab, <xref:System.Type> das durch den angegebenen eingeschlossen ist und den angegebenen Namen und die angegebene Metadatensignatur aufweist.  
  
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
 in Das TypeDef-Token für die Klasse oder Schnittstelle, die den Member einschließt, nach dem gesucht werden soll. Wenn dieser Wert ist `mdTokenNil`, wird die Suche für eine globale Variable oder globale Funktion durchgeführt.  
  
 `szName`  
 in Der Name des zu suchenden Members.  
  
 `pvSigBlob`  
 in Ein Zeiger auf die binäre Metadatensignatur des Members.  
  
 `cbSigBlob`  
 in Die Größe von `pvSigBlob`in Bytes.  
  
 `pmb`  
 vorgenommen Ein Zeiger auf das übereinstimmende mitgliedtdef-Token.  
  
## <a name="remarks"></a>Hinweise  
 Sie geben den Member mit der einschließenden Klasse oder Schnitt`td`Stelle (), dem`szName`Namen () und optional der Signatur`pvSigBlob`() an. In einer Klasse oder Schnittstelle können mehrere Member mit demselben Namen vorhanden sein. Übergeben Sie in diesem Fall die Signatur des Members, um die eindeutige Entsprechung zu finden.  
  
 Die an über `FindMember` gegebene Signatur muss im aktuellen Gültigkeitsbereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind. Eine Signatur kann ein Token einbetten, das den einschließenden Klassen-oder Werttyp identifiziert. Das Token ist ein Index in der lokalen Tabelle "Typedef". Sie können keine Lauf Zeit Signatur außerhalb des Kontexts des aktuellen Gültigkeits Bereichs erstellen und diese Signatur als Eingabe für die Eingabe `FindMember`verwenden.  
  
 `FindMember`sucht nur Elemente, die direkt in der Klasse oder Schnittstelle definiert wurden. geerbte Member werden nicht gefunden.  
  
> [!NOTE]
> `FindMember`ist eine Hilfsmethode. Es wird [IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); aufgerufen. Wenn dieser Aufruf keine Entsprechung findet, `FindMember` ruft [IMetaDataImport:: FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)auf.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Fern** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
