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
ms.openlocfilehash: c2ec907759a25048444ebcc81bf5bb0fd23ced58
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503652"
---
# <a name="imetadataimportfindmethod-method"></a>IMetaDataImport::FindMethod-Methode
Ruft einen Zeiger auf das MethodDef-Token für die Methode ab, die durch den angegebenen eingeschlossen ist <xref:System.Type> und den angegebenen Namen und die angegebene Metadatensignatur aufweist.  
  
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
 in Das `mdTypeDef` Token für den Typ (eine Klasse oder Schnittstelle), der den Member einschließt, nach dem gesucht werden soll. Wenn dieser Wert ist `mdTokenNil` , wird die Suche für eine globale Funktion durchgeführt.  
  
 `szName`  
 in Der Name der Methode, nach der gesucht werden soll.  
  
 `pvSigBlob`  
 in Ein Zeiger auf die binäre Metadatensignatur der Methode.  
  
 `cbSigBlob`  
 in Die Größe von in Bytes `pvSigBlob` .  
  
 `pmb`  
 vorgenommen Ein Zeiger auf das übereinstimmende MethodDef-Token.  
  
## <a name="remarks"></a>Bemerkungen  
 Sie geben die Methode mithilfe der einschließenden Klasse oder Schnittstelle ( `td` ), des Namens ( `szName` ) und optional der Signatur ( `pvSigBlob` ) an. Möglicherweise gibt es mehrere Methoden mit dem gleichen Namen in einer Klasse oder Schnittstelle. Übergeben Sie in diesem Fall die Signatur der Methode, um die eindeutige Entsprechung zu finden.  
  
 Die an über gegebene Signatur `FindMethod` muss im aktuellen Gültigkeitsbereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind. Eine Signatur kann ein Token einbetten, das den einschließenden Klassen-oder Werttyp identifiziert. Das Token ist ein Index in der lokalen Tabelle "Typedef". Sie können keine Lauf Zeit Signatur außerhalb des Kontexts des aktuellen Gültigkeits Bereichs erstellen und diese Signatur als Eingabe für die Eingabe verwenden `FindMethod` .  
  
 `FindMethod`sucht nur Methoden, die direkt in der Klasse oder Schnittstelle definiert wurden. geerbte Methoden werden nicht gefunden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- <xref:System.Reflection.MethodInfo>
- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
