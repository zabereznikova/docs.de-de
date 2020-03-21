---
title: IMetaDataImport::FindMethod-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: 53b3d94e8b1e273fcbc041d25a5bf586a12735c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177249"
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod-Methode
Ruft einen Zeiger auf das MethodDef-Token für die <xref:System.Type> Methode ab, die von der angegebenen Methode eingeschlossen wird und über den angegebenen Namen und die angegebene Metadatensignatur verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 [in] Das `mdTypeDef` Token für den Typ (eine Klasse oder Schnittstelle), das den zu suchenden Member einschließt. Wenn dieser `mdTokenNil`Wert ist , wird die Suche für eine globale Funktion durchgeführt.  
  
 `szName`  
 [in] Der Name der Methode, nach der gesucht werden soll.  
  
 `pvSigBlob`  
 [in] Ein Zeiger auf die binäre Metadatensignatur der Methode.  
  
 `cbSigBlob`  
 [in] Die Größe in `pvSigBlob`Bytes von .  
  
 `pmb`  
 [out] Ein Zeiger auf das übereinstimmende MethodDef-Token.  
  
## <a name="remarks"></a>Bemerkungen  
 Sie geben die Methode mit ihrer`td`einschließenden`szName`Klasse oder Schnittstelle (`pvSigBlob`), ihrem Namen ( ) und optional ihrer Signatur ( ) an. Es können mehrere Methoden mit demselben Namen in einer Klasse oder Schnittstelle vorhanden sein. Übergeben Sie in diesem Fall die Signatur der Methode, um die eindeutige Übereinstimmung zu finden.  
  
 Die übergebene `FindMethod` Signatur muss im aktuellen Bereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind. Eine Signatur kann ein Token einbetten, das die einschließende Klasse oder den Werttyp identifiziert. Das Token ist ein Index in der lokalen TypeDef-Tabelle. Sie können keine Laufzeitsignatur außerhalb des Kontexts des aktuellen Bereichs erstellen `FindMethod`und diese Signatur als Eingabe für die Eingabe für verwenden.  
  
 `FindMethod`findet nur Methoden, die direkt in der Klasse oder Schnittstelle definiert wurden; Es werden keine geerbten Methoden gefunden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Reflection.MethodInfo>
- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
