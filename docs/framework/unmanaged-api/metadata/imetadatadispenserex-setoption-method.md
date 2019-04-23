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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9869efee18549c3d0c8b9ee9ca27cf31c1ccf452
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197112"
---
# <a name="imetadatadispenserexsetoption-method"></a>IMetaDataDispenserEx::SetOption-Methode
Legt die angegebene Option auf einen angegebenen Wert für den aktuellen Metadatenbereich fest. Die Option wird gesteuert, wie Aufrufe im aktuellen Metadatenbereich behandelt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `optionId`  
 [in] Ein Zeiger auf eine GUID, der angibt, die Option festgelegt werden.  
  
 `pValue`  
 [in] Der Wert, der zum Festlegen der Option verwenden. Der Typ der dieser Wert muss es sich um eine Variante des Typs für die angegebene Option sein.  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die verfügbaren GUIDs, die die `optionId` -Parameter zeigen kann, und die entsprechende gültige Werte für die `pValue` Parameter.  
  
|GUID|Beschreibung|`pValue` Parameter|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|Steuert, welche Elemente auf Duplikate überprüft werden. Bei jedem Aufruf ein [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) -Methode, ein neues Element erstellt, kannst du die Methode zum Überprüfen, ob das Element im aktuellen Bereich bereits vorhanden ist. Beispielsweise sehen Sie sich das Vorhandensein des `mdMethodDef` Elemente; in diesem Fall beim Aufruf [IMetaDataEmit:: DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), überprüft er, dass die Methode im aktuellen Bereich nicht bereits vorhanden ist. Diese Überprüfung wird der Schlüssel, die eindeutig eine bestimmte Methode verwendet: übergeordneter Typ, Name und Signatur.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte von der [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) Enumeration.|  
|MetaDataRefToDefCheck|Steuert, die welche Elemente auf die verwiesen wird, werden in Definitionen konvertiert. Standardmäßig werden die Metadaten-Engine den Code optimieren, indem Sie ein Elements auf die verwiesen wird, der Definition konvertieren, wenn das referenzierte Element tatsächlich im aktuellen Bereich definiert ist.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte von der [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) Enumeration.|  
|MetaDataNotificationForTokenMovement|Steuerelemente, die die Token zugeordnet, die während eines Merge Metadaten auftreten Rückrufe zu generieren. Verwenden der [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) Methode zum Einrichten Ihrer [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) Schnittstelle.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte von der [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) Enumeration.|  
|MetaDataSetENC|Steuert das Verhalten von bearbeiten und Fortfahren "(ENC). Nur einen Modus Verhalten kann zu einem Zeitpunkt festgelegt werden.|Eine Variante des Typs UI4 sein muss, und der Wert darf die [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) Enumeration. Der Wert ist eine Bitmaske.|  
|MetaDataErrorIfEmitOutOfOrder|Steuert, welche Fehler ausgegeben,-Out-of-Order Rückrufe generieren. Ausgeben von Metadaten, die außerhalb der Reihenfolge ist nicht schwerwiegend. Wenn Sie Metadaten in eine Bestellung, die vom Metadatenmodul bevorzugt wird auszugeben, die Metadaten ist kompakter und aus diesem Grund kann eine effizientere durchsucht. Verwenden der `IMetaDataEmit::SetHandler` Methode zum Einrichten Ihrer [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) Schnittstelle.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte von der [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) Enumeration.|  
|MetaDataImportOption|Steuert, welche Arten von Elementen, die während eines ENC gelöscht wurden, die von einem Enumerator abgerufen werden.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte von der [CorImportOptions-Enumeration](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) Enumeration.|  
|MetaDataThreadSafetyOptions|Steuert, ob die Metadaten-Engine Reader-/Writer-sperren, wodurch die Threadsicherheit sichergestellt erhält. Standardmäßig nimmt die Engine an, dass der Zugriff durch den Aufrufer Singlethread ist, damit keine Sperren abgerufen werden. Clients sind verantwortlich für die ordnungsgemäße Synchronisierung warten, wenn Sie die Metadaten-API verwenden.|Eine Variante des Typs UI4 sein muss, und der Wert darf die [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) Enumeration. Der Wert ist eine Bitmaske.|  
|MetaDataGenerateTCEAdapters|Steuert, ob die Verarbeitung eng gekoppelter Ereignis (vorverarbeitung des TCE)-Adapter für COM-Verbindungspunktcontainer Type Library Importer-Tool generiert werden sollen.|Eine Variante des Typs "bool" muss sein. Wenn `pValue` nastaven NA hodnotu `true`, Type Library Importer-Tool generiert die vorverarbeitung des TCE-Adapter.|  
|MetaDataTypeLibImportNamespace|Gibt einen nicht standardmäßigen Namespace für die Typbibliothek, die importiert wird.|Entweder einen null-Wert oder eine Variante des Typs BSTR muss sein. Wenn `pValue` ist ein null-Wert, der aktuelle Namespace ist auf null festgelegt; andernfalls ist der aktuelle Namespace festgelegt, die Zeichenfolge, die in den BSTR Typ Variante gespeichert wird.|  
|MetaDataLinkerOptions|Steuert, ob der Linker eine Assembly oder eine .NET Framework-Modul-Datei generieren soll.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte von der [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) Enumeration.|  
|MetaDataRuntimeVersion|Gibt die Version der common Language Runtime, die mit der dieses Image erstellt wurde. Die Version wird als eine Zeichenfolge, z. B. "Version"1.0.3705 gespeichert.|Hierbei muss es sich um einen null-Wert, den Wert VT_EMPTY oder eine Variante des Typs BSTR sein. Wenn `pValue` ist null, die Runtime-Version festgelegt ist auf Null. Wenn `pValue` VT_EMPTY ist, die Version wird festgelegt, um einen Standardwert, der von der Version von Mscorwks.dll gezogen wird, innerhalb dessen die Metadatencode ausgeführt wird. Andernfalls, ist die Runtime-Version auf die Zeichenfolge festgelegt, die in den BSTR Typ Variante gespeichert wird.|  
|MetaDataMergerOptions|Gibt Optionen für das Zusammenführen der Metadaten.|Muss eine Variante des Typs UI4 sein und darf eine Kombination der Werte von der `MergeFlags` -Enumeration, die in der Datei "CorHdr.h" beschrieben wird.|  
|MetaDataPreserveLocalRefs|Deaktiviert die Optimierung von lokalen Verweisen in Definitionen.|Muss enthalten eine Kombination der Werte von der [CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) Enumeration.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataDispenserEx-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
