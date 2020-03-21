---
title: IMetaDataDispenserEx::SetOption-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.SetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::SetOption
helpviewer_keywords:
- IMetaDataDispenserEx::SetOption method [.NET Framework metadata]
- SetOption method [.NET Framework metadata]
ms.assetid: 9f1c7ccd-7fb2-41d8-aa00-24b823376527
topic_type:
- apiref
ms.openlocfilehash: f8e85a670d04e5825653864484b7ccd9ce747949
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175901"
---
# <a name="imetadatadispenserexsetoption-method"></a>IMetaDataDispenserEx::SetOption-Methode
Legt die angegebene Option auf einen bestimmten Wert für den aktuellen Metadatenbereich fest. Die Option steuert, wie Aufrufe des aktuellen Metadatenbereichs verarbeitet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetOption (  
    [in] REFGUID optionId,
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `optionId`  
 [in] Ein Zeiger auf eine GUID, der die festzulegende Option angibt.  
  
 `pValue`  
 [in] Der Wert, der zum Festlegen der Option verwendet werden soll. Der Typ dieses Werts muss eine Variante des Typs der angegebenen Option sein.  
  
## <a name="remarks"></a>Bemerkungen  
 In der folgenden Tabelle sind die `optionId` verfügbaren GUIDs aufgeführt, auf `pValue` die der Parameter verweisen kann, sowie die entsprechenden gültigen Werte für den Parameter.  
  
|GUID|Beschreibung|`pValue`Parameter|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Steuert, welche Elemente auf Duplikate überprüft werden. Jedes Mal, wenn Sie eine [IMetaDataEmit-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) aufrufen, die ein neues Element erstellt, können Sie die Methode bitten, zu überprüfen, ob das Element bereits im aktuellen Bereich vorhanden ist. Sie können z. B. `mdMethodDef` überprüfen, ob Artikel vorhanden sind. In diesem Fall wird beim Aufrufen von [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)überprüft, ob die Methode im aktuellen Bereich noch nicht vorhanden ist. Bei dieser Prüfung wird der Schlüssel verwendet, der eine bestimmte Methode eindeutig identifiziert: übergeordneter Typ, Name und Signatur.|Es muss eine Variante des Typs UI4 sein und muss eine Kombination der Werte der [CorCheckDuplicatesFor-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) enthalten.|  
|MetaDataRefToDefCheck|Steuerelemente, auf die auf Elemente verwiesen wird, werden in Definitionen konvertiert. Standardmäßig optimiert das Metadatenmodul den Code, indem es ein referenziertes Element in seine Definition konvertiert, wenn das referenzierte Element tatsächlich im aktuellen Bereich definiert ist.|Es muss eine Variante des Typs UI4 sein und muss eine Kombination der Werte der [CorRefToDefCheck-Enumeration](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) enthalten.|  
|MetaDataNotificationForTokenMovement|Steuert, welche Tokenneuzuordnungen während einer Metadatenzusammenführung auftreten, generieren Rückrufe. Verwenden Sie die [IMetaDataEmit::SetHandler-Methode,](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) um Ihre [IMapToken-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) einzurichten.|Es muss eine Variante des Typs UI4 sein und muss eine Kombination der Werte der [CorNotificationForTokenMovement-Enumeration](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) enthalten.|  
|MetaDataSetENC|Steuert das Verhalten von edit-and-continue (ENC). Es kann jeweils nur ein Verhaltensmodus festgelegt werden.|Es muss eine Variante des Typs UI4 sein und einen Wert der [CorSetENC-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) enthalten. Der Wert ist keine Bitmaske.|  
|MetaDataErrorIfEmitOutOfOrder|Steuerelemente, die Fehler aus der Reihenfolge ausgesendet haben, generieren Rückrufe. Das Aussenden von Metadaten in der Reihenfolge ist nicht schwerwiegend. Wenn Sie jedoch Metadaten in einer Reihenfolge aussenden, die von der Metadaten-Engine bevorzugt wird, sind die Metadaten kompakter und können daher effizienter durchsucht werden. Verwenden `IMetaDataEmit::SetHandler` Sie die Methode, um Ihre [IMetaDataError-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) einzurichten.|Es muss eine Variante des Typs UI4 sein und muss eine Kombination der Werte der [CorErrorIfEmitOutOfOrder-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) enthalten.|  
|MetaDataImportOption|Steuert, welche Arten von Elementen, die während eines ENC gelöscht wurden, von einem Enumerator abgerufen werden.|Es muss eine Variante des Typs UI4 sein und muss eine Kombination der Werte der [CorImportOptions-Enumerationsenumeration](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) enthalten.|  
|MetaDataThreadSafetyOptionen|Steuert, ob das Metadatenmodul Reader-/Writer-Sperren erhält, wodurch die Threadsicherheit gewährleistet wird. Standardmäßig geht das Modul davon aus, dass der Zugriff vom Aufrufer mit einem Thread erfolgt, sodass keine Sperren erhalten werden. Clients sind für die Aufrechterhaltung der ordnungsgemäßen Threadsynchronisierung verantwortlich, wenn die Metadaten-API verwendet wird.|Es muss eine Variante des Typs UI4 sein und einen Wert der [CorThreadSafetyOptions-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) enthalten. Der Wert ist keine Bitmaske.|  
|MetaDataGenerateTCEAdapter|Steuert, ob der Typbibliotheksimporteur die eng gekoppelten TCE-Adapter (TCE) für COM-Verbindungspunktcontainer generieren soll.|Muss eine Variante des Typs BOOL sein. Wenn `pValue` auf `true`gesetzt ist, generiert der Typbibliotheksimporter die TCE-Adapter.|  
|MetaDataTypeLibImportNamespace|Gibt einen nicht standardmäßigen Namespace für die Typbibliothek an, die importiert wird.|Muss entweder ein Nullwert oder eine Variante vom Typ BSTR sein. Wenn `pValue` es sich um einen NULL-Wert handelt, wird der aktuelle Namespace auf null festgelegt. Andernfalls wird der aktuelle Namespace auf die Zeichenfolge festgelegt, die im BSTR-Typ der Variante gehalten wird.|  
|MetaDataLinkerOptionen|Steuert, ob der Linker eine Assembly oder eine .NET Framework-Moduldatei generieren soll.|Es muss eine Variante des Typs UI4 sein und muss eine Kombination der Werte der [CorLinkerOptions-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) enthalten.|  
|MetaDataRuntimeVersion|Gibt die Version der Common Language Runtime an, für die dieses Abbild erstellt wurde. Die Version wird als Zeichenfolge gespeichert, z. B. "v1.0.3705".|Muss ein NULL-Wert, ein VT_EMPTY Wert oder eine Variante vom Typ BSTR sein. Wenn `pValue` null ist, wird die Laufzeitversion auf null gesetzt. Wenn `pValue` VT_EMPTY ist, wird die Version auf einen Standardwert festgelegt, der aus der Version von Mscorwks.dll gezogen wird, in der der Metadatencode ausgeführt wird. Andernfalls wird die Laufzeitversion auf die Zeichenfolge festgelegt, die im BSTR-Typ der Variante gehalten wird.|  
|MetaDataMergerOptionen|Gibt Optionen zum Zusammenführen von Metadaten an.|Muss eine Variante des Typs UI4 sein und muss `MergeFlags` eine Kombination der Werte der Enumeration enthalten, die in der Datei CorHdr.h beschrieben wird.|  
|MetaDataPreserveLocalRefs|Deaktiviert die Optimierung lokaler Verweise in Definitionen.|Muss eine Kombination der Werte der [CorLocalRefPreservation-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) enthalten.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
