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
ms.openlocfilehash: bc30f9fb120db92ccfc1e7dd0560b3fe18c54b29
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432732"
---
# <a name="imetadatadispenserexsetoption-method"></a>IMetaDataDispenserEx::SetOption-Methode
Legt die angegebene Option auf einen angegebenen Wert für den aktuellen Metadatenbereich fest. Mit der-Option wird gesteuert, wie Aufrufe des aktuellen Metadatenbereichs behandelt werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `optionId`  
 in Ein Zeiger auf eine GUID, die die festzulegende Option angibt.  
  
 `pValue`  
 in Der Wert, der zum Festlegen der Option verwendet werden soll. Der Typ dieses Werts muss eine Variante des Typs der angegebenen Option sein.  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle sind die verfügbaren GUIDs aufgelistet, auf die der `optionId`-Parameter verweisen kann, sowie die entsprechenden gültigen Werte für den `pValue`-Parameter.  
  
|GUID|Beschreibung|`pValue`-Parameter|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Steuert, welche Elemente auf Duplikate geprüft werden. Jedes Mal, wenn Sie eine [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) -Methode aufzurufen, die ein neues Element erstellt, können Sie die Methode bitten, zu überprüfen, ob das Element bereits im aktuellen Gültigkeitsbereich vorhanden ist. Beispielsweise können Sie überprüfen, ob `mdMethodDef` Elemente vorhanden sind. Wenn Sie in diesem Fall [IMetaDataEmit::D efinemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)aufgerufen haben, wird überprüft, ob die Methode nicht bereits im aktuellen Gültigkeitsbereich vorhanden ist. Bei dieser Überprüfung wird der Schlüssel verwendet, der eine bestimmte Methode eindeutig identifiziert: Übergeordneter Typ, Name und Signatur.|Muss eine Variante vom Typ UI4 sein und muss eine Kombination der Werte der [corcheckdupli-](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) Enumeration enthalten.|  
|MetaDataRefToDefCheck|Steuert, welche referenzierten Elemente in Definitionen konvertiert werden. Standardmäßig optimiert die metadatenengine den Code, indem ein referenziertes Element in seine Definition umgerechnet wird, wenn das Element, auf das verwiesen wird, tatsächlich im aktuellen Gültigkeitsbereich definiert ist.|Muss eine Variante vom Typ "UI4" sein und muss eine Kombination der Werte der [corref/defcheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) -Enumeration enthalten.|  
|MetaDataNotificationForTokenMovement|Steuert, welche tokenumwandlung während einer Metadatenzusammenführung die Rückrufe generieren. Verwenden Sie die [IMetaDataEmit:: Setter](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) -Methode, um die [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) -Schnittstelle einzurichten.|Muss eine Variante vom Typ UI4 sein und muss eine Kombination der Werte der [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) -Enumeration enthalten.|  
|MetaDataSetENC|Steuert das Verhalten von "Bearbeiten und Fortfahren" (ENC). Es kann jeweils nur ein Modus von Verhalten festgelegt werden.|Muss eine Variante vom Typ UI4 sein und muss einen Wert der [corsegtenc](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) -Enumeration enthalten. Der Wert ist keine Bitmaske.|  
|MetaDataErrorIfEmitOutOfOrder|Steuert, welche ausgegebene fehl Reihenfolge Fehler Rückrufe generieren. Das Ausgeben von Metadaten außerhalb der Reihenfolge ist nicht schwerwiegend. Wenn Sie jedoch Metadaten in einer von der metadatenengine bevorzugten Reihenfolge ausgeben, sind die Metadaten kompakter und können daher effizienter durchsucht werden. Verwenden Sie die `IMetaDataEmit::SetHandler`-Methode zum Einrichten der [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) -Schnittstelle.|Muss eine Variante vom Typ UI4 sein und muss eine Kombination der Werte der [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) -Enumeration enthalten.|  
|MetaDataImportOption|Steuert, welche Arten von Elementen, die während einer Enumeration gelöscht wurden, von einem Enumerator abgerufen werden.|Muss eine Variante vom Typ "UI4" sein und muss eine Kombination der Werte der Enumeration " [CorImportOptions Enumeration](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) " enthalten.|  
|MetaDataThreadSafetyOptions|Steuert, ob die metadatenengine Lese-/Schreibsperren erhält, wodurch die Thread Sicherheit sichergestellt wird. Standardmäßig geht die Engine davon aus, dass der Zugriff vom Aufrufer mit einem einzigen Thread erfolgt, sodass keine Sperren abgerufen werden. Clients sind für die Beibehaltung der ordnungsgemäßen Thread Synchronisierung bei Verwendung der Metadaten-API verantwortlich.|Muss eine Variante vom Typ UI4 sein und muss einen Wert der [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) -Enumeration enthalten. Der Wert ist keine Bitmaske.|  
|MetaDataGenerateTCEAdapters|Steuert, ob das Typbibliothek-Import Programm die eng verknüpften Ereignis Adapter (TCE) für com-Verbindungspunkt Container generieren soll.|Muss eine Variante vom Typ "bool" sein. Wenn `pValue` auf `true`festgelegt ist, generiert das Typbibliothek-Import Programm die TCE-Adapter.|  
|MetaDataTypeLibImportNamespace|Gibt einen nicht standardmäßigen Namespace für die Typbibliothek an, die importiert wird.|Muss entweder ein NULL-Wert oder eine Variante vom Typ BSTR sein. Wenn `pValue` ein NULL-Wert ist, wird der aktuelle Namespace auf NULL festgelegt. Andernfalls wird der aktuelle Namespace auf die Zeichenfolge festgelegt, die im BSTR-Typ der Variante enthalten ist.|  
|MetaDataLinkerOptions|Steuert, ob der Linker eine Assembly oder eine .NET Framework Modul Datei generieren soll.|Muss eine Variante vom Typ UI4 sein und muss eine Kombination der Werte der [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) -Enumeration enthalten.|  
|MetaDataRuntimeVersion|Gibt die Version der Common Language Runtime an, für die das Image erstellt wurde. Die Version wird als Zeichenfolge gespeichert, z. b. "v 1.0.3705".|Muss ein NULL-Wert, ein VT_EMPTY Wert oder eine Variante vom Typ BSTR sein. Wenn `pValue` NULL ist, wird die Laufzeitversion auf NULL festgelegt. Wenn `pValue` VT_EMPTY ist, wird die Version auf einen Standardwert festgelegt, der aus der Version von mscorwert. dll gezeichnet wird, in der der metadatencode ausgeführt wird. Andernfalls wird die Laufzeitversion auf die Zeichenfolge festgelegt, die im BSTR-Typ der Variante enthalten ist.|  
|MetaDataMergerOptions|Gibt Optionen zum Zusammenführen von Metadaten an.|Muss eine Variante vom Typ "UI4" sein und muss eine Kombination der Werte der `MergeFlags` Enumeration enthalten, die in der Datei "corhdr. h" beschrieben wird.|  
|MetaDataPreserveLocalRefs|Deaktiviert die Optimierung lokaler Verweise in Definitionen.|Muss eine Kombination der Werte der [corlocalref Preservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) -Enumeration enthalten.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
